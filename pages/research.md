---
layout: default
title: 研究领域
permalink: /research/
---
{% assign research = site.data.page_content.research %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ research.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ research.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ research.masthead.intro }}</p>
    </header>

    <div class="research-grid research-grid--institutional">
      {% for area in research.areas %}
      <article class="research-card research-card--institutional research-card--linked">
        <a class="research-card__link" href="{{ area.link | relative_url }}">
          <img class="research-card__image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt }}">
          <div class="research-card__body">
            <p class="card-meta">{{ area.code }}</p>
            <h2 class="card-title">{{ area.title }}</h2>
            <p>{{ area.description }}</p>
          </div>
        </a>
      </article>
      {% endfor %}
    </div>

    <section id="lithic-technology" class="detail-section">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">Area 01</p>
          <h2 class="section-title section-title--left">石器技术研究</h2>
        </div>
        <p class="section-intro section-intro--narrow">揭示我国旧石器工业内部及工业之间的多样性，探索它们与世界其他地区石器工业的共性及差异性。</p>
      </div>
      <img class="detail-section__image" src="{{ '/assets/uploads/docx-tl-homepage-0326/figure-07.jpeg' | relative_url }}" alt="石器技术研究配图">

      <div class="detail-section__panel">
        <h3>期刊论文</h3>
        <ol class="detail-list">
          <li>李英华. 类型、技术与人: 考古学者基于技术逻辑的思考[J]. 南方文物, 2025, (01): 28-37.</li>
          <li>李英华, 余西云. 考古学对于“文化”和“传播”的思考[J]. 跨文化传播研究, 2023, (02): 51-62.</li>
          <li>李英华, 李桓. 陕西大荔人遗址石制品的新研究[J]. 边疆考古研究, 2015, (02): 121-134.</li>
          <li>李英华, 包爱丽, 侯亚梅. 石器研究的新视角: 技术-功能分析法: 以观音洞遗址为例[J]. 考古, 2011, (09): 58-70+113.</li>
          <li>李英华, 李英华, 侯亚梅, 等. 旧石器技术研究法之应用: 以观音洞石核为例[J]. 人类学学报, 2009, 28(04): 355-362.</li>
          <li>李英华, 侯亚梅, Boeda E. 观音洞遗址古人类剥坯模式与认知特征[J]. 科学通报, 2009, 54(19): 2864-2870.</li>
          <li>李英华, 侯亚梅, Erika Bodin. 法国旧石器技术研究概述[J]. 人类学学报, 2008, (01): 51-65.</li>
          <li>李英华, 余西云, 侯亚梅. 关于三峡地区石器工业中的锐棱砸击制品[C]//第十届中国古脊椎动物学学术年会论文集. 2006: 268-279.</li>
          <li>吴沄, 邱开卫, 罗伊, 等. 云南沧源汤不拉和平文化洞穴遗址石制品的初步研究[J]. 南方文物, 2024, (02): 219-230.</li>
          <li>周玉端, 李英华. 技术本体论视角下的旧石器技术研究[J]. 考古, 2024, (02): 66-77.</li>
          <li>周玉端, 李英华, 韦军, 等. 广西桂林市甑皮岩遗址砾石工具的技术-功能分析及相关问题[J]. 考古, 2023, (01): 65-78.</li>
          <li>韦璇, 李英华, 娄文台, 等. 中国考古的国际化分析: 从中外考古期刊论文数据出发[J]. 南方文物, 2022, (01): 30-40.</li>
          <li>贺成坡, 韦璇, 李英华. “新石器”研究方法概述[J]. 江汉考古, 2021, (06): 268-277.</li>
          <li>贺成坡, 李英华, 韦璇, 等. 湖北石首市走马岭遗址石器原料溯源分析[J]. 四川文物, 2021, (06): 43-51.</li>
          <li>周玉端, 李英华. 旧石器类型学与技术学的回顾与反思[J]. 考古, 2021, (02): 68-80+2.</li>
          <li>李锋, 李英华, 高星. 贵州观音洞遗址石制品剥片技术辨析[J]. 人类学学报, 2020, 39(01): 1-11.</li>
          <li>周玉端, 李英华. 从遗物展示到技术阐释: 法国旧石器绘图方式的变迁和启示[J]. 考古, 2019, (02): 63-73.</li>
          <li>周玉端, 李英华. 东南亚和平文化研究的新进展[J]. 考古, 2017, (01): 68-77.</li>
          <li>Li F, Li Y, Gao X, et al. A refutation of reported Levallois technology from Guanyindong Cave in south China[J]. National Science Review, 2019, 6(6): 1094-1096.</li>
          <li>Li Y, Boeda E, Forestier H, et al. Lithic Technology, typology and cross-regional comparison of Pleistocene lithic industries: Comment on the earliest evidence of Levallois in East Asia[J]. L'anthropologie, 2019, 123(4-5): 769-781.</li>
          <li>Li Y H, Hou Y M, Boeda E. Mode of debitage and technical cognition of hominids at the Guanyindong site[J]. Chinese Science Bulletin, 2009, 54(21): 3864-3871.</li>
        </ol>
      </div>

      <div class="detail-section__panel">
        <h3>书籍</h3>
        <ol class="detail-list">
          <li>李英华. 旧石器技术[M]. 社会科学文献出版社, 2017.</li>
        </ol>
      </div>
    </section>

    <section id="hanshui-middle-yangtze" class="detail-section">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">Area 02</p>
          <h2 class="section-title section-title--left">汉水流域与长江中游史前人类的石器技术与行为研究</h2>
        </div>
        <p class="section-intro section-intro--narrow">围绕汉水流域与长江中游材料，梳理技术演化、遗址序列与远古人类行为模式。</p>
      </div>
      <img class="detail-section__image" src="{{ '/assets/uploads/docx-tl-homepage-0326/figure-08.png' | relative_url }}" alt="汉水流域与长江中游研究配图">

      <div class="detail-section__panel">
        <h3>期刊论文</h3>
        <ol class="detail-list">
          <li>李英华, 周玉端, 孙雪峰. 湖北郧县后房遗址石器工业的年代、操作链及其意义[J]. 江汉考古, 2018, (02): 36-47.</li>
          <li>李英华. 大冶石龙头遗址石器的新研究[J]. 江汉考古, 2011, (02): 45-53.</li>
          <li>李英华, 孙雪峰. 湖北郧县后房旧石器遗址发掘简报[J]. 江汉考古, 2013, (01): 6-15.</li>
          <li>李英华, 周玉端. 试论古人对石器工业生产体系的管理模式: 以郧县后房旧石器遗址为例[J]. 江汉考古, 2015, (04): 71-78.</li>
          <li>贺成坡, 李英华, 韦璇, 等. 湖北石首市走马岭遗址石器原料溯源分析[J]. 四川文物, 2021, (06): 43-51.</li>
          <li>Lou W, Wang F, Wei X, et al. Identification and implications of lithic artifacts starch residues from Fenghuangzui Neolithic site in Central China[J]. npj Heritage Science, 2025, 13(1): 511.</li>
          <li>Li Y, Sun X, Bodin E. A macroscopic technological perspective on lithic production from the Early to Late Pleistocene in the Hanshui River Valley, central China[J]. Quaternary International, 2014, 347: 148-162.</li>
          <li>Li Y, Zhou Y, Sun X, et al. New evidence of a lithic assemblage containing in situ Late Pleistocene bifaces from the Houfang site in the Hanshui River Valley, Central China[J]. Comptes Rendus Palevol, 2018, 17(1-2): 131-142.</li>
          <li>Li Y, Bodin E. Variabilite et homogeneite des modes de debitage en Chine entre 300 000 et 50 000 ans[J]. L'Anthropologie, 2013, 117(5): 459-493.</li>
          <li>Ying-hua Li, Ya-mei Hou, Boeda E. Methodological application of the paleolithic technological research, a case study of a core from the Guanyindong Site[J]. Acta Anthropologica Sinica, 2009, 28(04): 355.</li>
          <li>Yang R, Xue L, Jin Y, et al. Combined approaches of techno-functional and use-wear analysis indicated diverse reuse behaviors of polished bevelled stone tools of Zoumaling site (5500-3900 cal BP), central China[J]. npj Heritage Science, 2026, 14(1): 68.</li>
        </ol>
      </div>

      <div class="detail-section__panel">
        <h3>硕博士论文</h3>
        <ol class="detail-list">
          <li>杨濡僖. 磨制带刃石制品的功能与再利用: 以走马岭遗址石器技术-功能和微痕分析为例[D]. 武汉大学, 2024.</li>
          <li>娄文台. 湖北襄阳凤凰咀遗址出土石制品的淀粉粒分析[D]. 武汉大学, 2023.</li>
          <li>贺成坡. 湖北石首走马岭遗址石器工业分析[D]. 武汉大学, 2022.</li>
        </ol>
      </div>
    </section>

    <section id="south-china-southeast-asia" class="detail-section">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">Area 03</p>
          <h2 class="section-title section-title--left">华南与东南亚古人类的技术与行为研究</h2>
        </div>
        <p class="section-intro section-intro--narrow">结合华南与东南亚的遗址和器物材料，讨论技术传统、区域联系与文化变迁。</p>
      </div>
      <img class="detail-section__image" src="{{ '/assets/uploads/docx-tl-homepage-0326/figure-09.jpeg' | relative_url }}" alt="华南与东南亚研究配图">

      <div class="detail-section__panel">
        <h3>期刊论文</h3>
        <ol class="detail-list">
          <li>李英华, 赵春光. 新世纪背景下的华南与东南亚早期文化关系的考古学研究[J]. 南方文物, 2020, (05): 51-59.</li>
          <li>李英华, 林美蓉, 邓鸿山, 等. 越南和平文化石器技术分析及对华南东南亚砾石石器工业研究的启示[J]. 南方文物, 2020, (05): 90-105.</li>
          <li>李英华, 周玉端, 郝思德, 等. 海南三亚落笔洞遗址石器工业新研究: 与东南亚和平文化遗址的比较[J]. 考古, 2020, (01): 68-81.</li>
          <li>韦璇, 李英华. 越南史前考古学研究历史、现状与趋势[J]. 江汉考古, 2025, (06): 165-176+185.</li>
          <li>韦璇, 梁婷婷, 苏吀端. 缅甸史前考古研究概述[J]. 南方文物, 2024, (01): 180-197.</li>
          <li>梁婷婷, 韦璇. 泰国史前考古学史[J]. 南方文物, 2024, (01): 198-211.</li>
          <li>韦璇. 马来西亚史前考古学史[J]. 南方文物, 2022, (03): 199-209.</li>
          <li>洪晓纯, 娄文台, 韦璇. 华南沿海、台湾和岛屿东南亚的早期航海与文化: 公元前6000年至公元前500年[J]. 南方文物, 2024, (01): 224-234.</li>
          <li>Li Y, Hao S, Huang W, et al. Luobi cave, south China: a comparative perspective on a novel cobble-tool industry associated with bone tool technology during the pleistocene-holocene transition[J]. Journal of World Prehistory, 2019, 32(2): 143-178.</li>
          <li>Wei X, Liang T, Soe M T, et al. The history of prehistoric archaeology in Myanmar: A brief review[J]. Asian Archaeology, 2023, 7(2): 203-219.</li>
          <li>Yinghua Li, Dung L T M, So'n D H, et al. A new technological analysis of Hoabinhian stone artifacts from Vietnam and its implications for cultural homogeneity and variability between mainland Southeast Asia and South China[J]. Asian Perspectives, 2021, 60(1): 71-96.</li>
          <li>Wu Y, Qiu K, Luo Y, et al. Dedan Cave: Extending the evidence of the Hoabinhian technocomplex in southwest China[J]. Journal of Archaeological Science: Reports, 2022, 44: 103524.</li>
          <li>Wu Y, Jiao Y, Ji X, et al. High-precision U-series dating of the late Pleistocene-early Holocene rock paintings at Tiger Leaping Gorge, Jinsha River valley, southwestern China[J]. Journal of Archaeological Science, 2022, 138: 105535.</li>
          <li>Wang X, Cen H, Zhang X, et al. New evidence for the terminal pleistocene funerary-associated ochre use in southwestern China[J]. npj Heritage Science, 2025, 13(1): 578.</li>
          <li>Chen X, He A, Sun X, et al. Guomo open-air site (15-12 ka) in Guangxi Zhuang Autonomous Region, southern China: A new cobble-based industry for rethinking the definition of “Hoabinhian”[J]. Journal of Archaeological Science: Reports, 2023, 49: 104033.</li>
          <li>Wu Y, Qiu K, Jin Q, et al. The Hoabinhian technocomplex in southwest China: Preliminary report on new discoveries in recent decades[J]. L'Anthropologie, 2024, 128(1): 103234.</li>
          <li>Zhou Y, Cai S, Liu X, et al. Cobbles during the final Pleistocene-early Holocene transition: An original lithic assemblage from Maomaodong rockshelter, Guizhou Province, southwest China[J]. Archaeological Research in Asia, 2022, 32: 100411.</li>
          <li>Wei G, Huang W, Boeda E, et al. Recent discovery of a unique Paleolithic industry from the Yumidong Cave site in the Three Gorges region of Yangtze River, southwest China[J]. Quaternary International, 2017, 434: 107-120.</li>
          <li>Zhou Y, Shen Z, Wu Y, et al. The knapping strategies in the Paleolithic on the Yunnan-Guizhou Plateau, southwest China: A regional particularity[J]. L'Anthropologie, 2023, 127(4): 103195.</li>
        </ol>
      </div>

      <div class="detail-section__panel">
        <h3>硕博士论文</h3>
        <ol class="detail-list">
          <li>梁婷婷. 泰国史前考古学史[D]. 武汉大学, 2022.</li>
          <li>李桓. 菲律宾史前考古研究概述[D]. 武汉大学, 2018.</li>
          <li>陈鹏. 越南旧石器文化概述[D]. 武汉大学, 2019.</li>
          <li>周玉端. 柳州白莲洞遗址石器工业的技术分析[D]. 武汉大学, 2017.</li>
        </ol>
      </div>
    </section>
  </div>
</section>
