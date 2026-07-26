<template>
  <section class="nomads-showcase-section">
    <div class="showcase-header">
      <div class="header-left">
        <h2 class="showcase-title">微短剧爆款剧本与爆点策划实战模板库</h2>
        <p class="showcase-subtitle">精选战神逆袭、真假千金、穿越科技、悬疑无限流等爆款方案，点击“一键套用”快速策划</p>
      </div>
      <span class="showcase-badge">已收录 {{ showcaseItems.length }} 个短剧爆款模板</span>
    </div>

    <div class="showcase-grid">
      <div 
        v-for="item in showcaseItems" 
        :key="item.id" 
        class="glass-card showcase-card"
      >
        <div class="card-header">
          <span class="scenario-tag">{{ item.tag }}</span>
          <span class="usage-count">{{ item.usageCount }} 次生成</span>
        </div>

        <div class="card-content">
          <h3 class="item-title">{{ item.title }}</h3>
          <p class="item-prompt">“{{ item.prompt }}”</p>
        </div>

        <div class="card-action">
          <button class="apply-btn" @click="applyTemplate(item)">
            <span>一键套用</span>
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <line x1="5" y1="12" x2="19" y2="12"></line>
              <polyline points="12 5 19 12 12 19"></polyline>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed } from 'vue';

const emit = defineEmits<{
  (e: 'apply-template', payload: { prompt: string; scriptType?: string; platform?: string; episodeLength?: string }): void;
}>();

export interface ShowcaseItem {
  id: string;
  tag: string;
  title: string;
  prompt: string;
  scriptType?: string;
  platform?: string;
  episodeLength?: string;
  usageCount: string;
}

const showcaseItems = computed<ShowcaseItem[]>(() => [
  {
    id: 'duanju-1',
    tag: '战神爽文',
    title: '战神隐姓埋名入赘豪门与极致打脸',
    prompt: '策划 80集战神归来题材微短剧，男主龙王隐姓埋名入赘豪门三载遭受冷眼，因女儿遭反派殴打暴怒亮出修罗战神身份，瞬间调集十万退役战警封锁全城，极致打脸反派与势利岳母。',
    scriptType: '战神战王与爽文逆袭剧本',
    platform: '抖音短剧',
    episodeLength: '80-100集长剧全案',
    usageCount: '98.5k'
  },
  {
    id: 'duanju-2',
    tag: '豪门逆袭',
    title: '真假千金血缘反转与黑客大佬回归',
    prompt: '策划 100集真假千金豪门爽剧，真千金从小被弃乡村，带着顶级神医与全球第一黑客身份空降豪门宴会，当场拆穿假千金伪造的顶级艺术画作与虚假身世，引爆家族震荡。',
    scriptType: '豪门恩怨与甜宠战术剧本',
    platform: '微信小程序短剧',
    episodeLength: '80-100集长剧全案',
    usageCount: '86.2k'
  },
  {
    id: 'duanju-3',
    tag: '穿越降维',
    title: '工科男穿越古代兵临城下硬核造枪炮',
    prompt: '策划 3-5分钟精致剧情穿越短剧，现代顶级机械工程师意外穿越至古代边关废柴皇子，面对敌军压境，利用现代化学与冶金技术连夜造出红衣大炮与黑火药，降维打击敌方大军。',
    scriptType: '悬疑脑洞与科幻反转剧本',
    platform: '快手短剧',
    episodeLength: '3-5分钟精致剧情',
    usageCount: '74.1k'
  },
  {
    id: 'duanju-4',
    tag: '悬疑脑洞',
    title: '同一天死亡轮回与限时真凶破局',
    prompt: '策划 悬疑无限流微短剧黄金前3秒，主角陷入每天晚上22点必被神秘黑衣人刺杀的死亡循环，每次复活保留记忆与伤痕，必须在有限的6次循环内找出藏在身边的连环凶手。',
    scriptType: '微短剧黄金前3秒与大纲策划',
    platform: '抖音短剧',
    episodeLength: '1-3分钟短小精悍',
    usageCount: '69.8k'
  },
  {
    id: 'duanju-5',
    tag: '甜宠契约',
    title: '替嫁残疾霸总与扮猪吃老虎反转',
    prompt: '策划 80集甜宠契约短剧，女主被迫替心机妹妹嫁给轮椅上的废柴霸总，婚后发现霸总竟是掌控全球金融命脉的神秘大鳄，二人假戏真做联手惩治家族恶毒继母。',
    scriptType: '豪门恩怨与甜宠战术剧本',
    platform: '微信小程序短剧',
    episodeLength: '80-100集长剧全案',
    usageCount: '63.4k'
  },
  {
    id: 'duanju-6',
    tag: '民俗惊悚',
    title: '深夜怪谈公寓与绝对不可违反的规则',
    prompt: '策划 悬疑怪谈短剧，主角入住租金极低的复古公寓，门缝下塞入张血色守则（1.半夜12点后不可回应镜中叩门声；2.看到穿红衣的女童必须闭眼倒退三步），通过规则破局绝地反杀。',
    scriptType: '悬疑脑洞与科幻反转剧本',
    platform: '海外Shorts',
    episodeLength: '1-3分钟短小精悍',
    usageCount: '52.7k'
  }
]);

function applyTemplate(item: ShowcaseItem) {
  emit('apply-template', {
    prompt: item.prompt,
    scriptType: item.scriptType,
    platform: item.platform,
    episodeLength: item.episodeLength
  });
}
</script>

<style scoped>
.nomads-showcase-section {
  margin-top: 2rem;
  width: 100%;
}

.showcase-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 1.25rem;
  padding-bottom: 0.75rem;
  border-bottom: 1px solid var(--card-border);
}

.showcase-title {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--text-primary);
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.showcase-subtitle {
  font-size: 0.825rem;
  color: var(--text-secondary);
  margin-top: 0.25rem;
}

.showcase-badge {
  font-size: 0.75rem;
  color: #a5b4fc;
  background: rgba(99, 102, 241, 0.12);
  border: 1px solid rgba(99, 102, 241, 0.25);
  padding: 4px 10px;
  border-radius: 20px;
}

.showcase-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 1.25rem;
}

@media (min-width: 640px) {
  .showcase-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .showcase-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.showcase-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  padding: 1.25rem;
  background: rgba(255, 255, 255, 0.02);
  border: 1px solid var(--card-border);
  border-radius: 14px;
  transition: all 0.25s ease;
}

.showcase-card:hover {
  background: rgba(255, 255, 255, 0.05);
  border-color: rgba(99, 102, 241, 0.4);
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.75rem;
}

.scenario-tag {
  font-size: 0.75rem;
  font-weight: 600;
  padding: 3px 8px;
  border-radius: 6px;
  background: rgba(168, 85, 247, 0.15);
  color: #c084fc;
  border: 1px solid rgba(168, 85, 247, 0.3);
}

.usage-count {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

.card-content {
  margin-bottom: 1rem;
  flex: 1;
}

.item-title {
  font-size: 0.95rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 0.4rem;
}

.item-prompt {
  font-size: 0.825rem;
  color: var(--text-secondary);
  line-height: 1.45;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  font-style: italic;
}

.card-action {
  padding-top: 0.75rem;
  border-top: 1px solid rgba(255, 255, 255, 0.04);
}

.apply-btn {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 0.5rem 1rem;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.3);
  border-radius: 8px;
  color: #a5b4fc;
  font-size: 0.825rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
}

.showcase-card:hover .apply-btn {
  background: var(--primary-gradient);
  border-color: transparent;
  color: white;
}

.arrow-icon {
  width: 14px;
  height: 14px;
  transition: transform 0.2s ease;
}

.apply-btn:hover .arrow-icon {
  transform: translateX(3px);
}
</style>
