<template>
  <div id="foot_main">
    <div class="foot_unit" style="width: 100%; white-space: normal">
      <el-card class="box-card">
        <el-collapse accordion>
          <el-collapse-item name="1" style="">
            <template #title>
                  <span style="font-size: large; display: flex; align-items: center">
                    <el-icon>
                      <Comment />
                    </el-icon><b style="margin-left: 4px">网站反馈</b>
                  </span>
            </template>
            <a href="https://docs.qq.com/form/page/DVVNyd2J5RmV2UndQ">点击此处</a>通过问卷反馈问题/提供建议。
          </el-collapse-item>
          <el-collapse-item name="2" style="">
            <template #title>
                  <span style="font-size: large; display: flex; align-items: center"><el-icon>
                      <TrendCharts />
                    </el-icon><b style="margin-left: 4px">动态平衡算法简述</b></span>
            </template>
            <b>算法核心思路为“掉率越高，则价值越低”且“物品价值仅受获取成本影响”</b>
            <hr />
            <ul style="padding-left: 2em">
              <li>第1步：取所有<b>常驻关卡</b>的掉率，以材料价格计算关卡效率</li>
              <li>第2步：以关卡效率修正材料价格</li>
              <li>第3步：重复操作(1)(2)，直至材料价格和关卡效率收敛于误差小于万分之一，实现动态平衡，此时得出<b>关卡效率</b>和<b>材料价值</b></li>
              <li>第4步：根据商店售价和物品价值，计算常驻商店和活动商店性价比</li>
            </ul>

            <b>FAQ</b>
            <hr />
            <ul style="padding-left: 2em">
              <li>Q：你怎么知道数列是收敛的？</li>
              <li><b>A：如果不收敛网站就崩了，你也看不到这句话了。</b></li>
              <li>Q：为什么不用线性规划进行计算？</li>
              <li>
                <b>A：人无法两次踏进同一条河流，线性规划的目标时刻都在变动，随活动UP起伏的价值你喜欢吗？</b>
              </li>
              <li>Q：你这结果有问题啊，XX关的x材料期望明显更低，为什么XX关不是效率最高？</li>
              <li>
                <b>A：大部分关卡都掉落多种材料，单一材料的期望只能说明短期最优，长期最优是要计算副产物的。</b>
              </li>
            </ul>
          </el-collapse-item>
          <el-collapse-item name="3" style="">
            <template #title>
                  <span style="font-size: large; display: flex; align-items: center"><el-icon>
                      <Opportunity />
                    </el-icon><b style="margin-left: 4px">图例与计算细节</b></span>
            </template>
            <b>刷图规划</b>
            <hr />

            <ul style="padding-left: 2em">
              <li>根据价值一览中的价格和企鹅物流的关卡掉落数据计算。</li>
              <li>只有多于300样本的关卡才会被收录。</li>
              <li>仅收录由自动刷图软件上报的掉落数据。</li>
              <li>活动关卡只在活动期间出现。</li>
              <li>插曲和别传常驻后重新计算效率，该效率与活动时无关。</li>
            </ul>

            <b>商店性价比</b>
            <hr />
            单位：理智/各货币
            <ul style="padding-left: 2em">
              <li>各商店之间货币不同，故<b>不可跨店对比数值</b>。</li>
              <li>根据<b>价值一览</b>中的价格和商店售价得到的性价比值。</li>
              <li>活动商店采用相同算法。</li>
              <li>信用商店计价单位为100信用点。</li>
              <li>若源岩系材料的主要来源是1-7以外的关卡，则源岩系材料价值<a class="popover_color">+6%</a>。</li>
            </ul>

            <b>材料价值</b>
            <hr />
            <ul style="padding-left: 2em">
              <li>绿票理智换算关系：<b>1理智=1.25绿票</b>。</li>
              <li>数据选择范围为<a href="https://penguin-stats.cn/">企鹅物流</a>中的<b>常驻关卡</b>以保证价值的稳定性。</li>
              <li>定价时考虑加工站副产物，副产物掉率假设为20%。</li>
              <li>考虑到实际情况，芯片的价值略作调整，分为强势芯片、均势芯片和弱势芯片。</li>
              <li>假设重装/医疗芯片和近卫/特种芯片需求比为2:1，狙击/术师和先锋/辅助需求比为1:1。</li>
              <li>模组数据块以红票商店售价进行定价。</li>
              <li>龙门币依据CE-6定价，经验书和无人机依据基建生产效率进行折算，折算系数为0.625</li>
              <li>技巧概要依据CA-5定价，且考虑加工站副产物。</li>
              <li>采购凭证依据AP-5定价。</li>
              <li>碳以九色鹿为基准进行定价。</li>
              <li>理论上寻访凭证=600合成玉=3.33石=450理智，但不碎石刷图的情况下该等式无意义，仅列出以供参考。</li>
              <li>招募凭证的价值由<a href="http://localhost:3000/survey/maarecruitdata/">公招tag统计</a>得出，仅供参考。</li>
              <li>物资箱价值取<a href="https://penguin-stats.cn/">企鹅物流</a>中的以往数据进行估算。</li>
              <li>若源岩系材料的主要来源是1-7以外的关卡，则源岩系材料价值<a class="popover_color">+6%</a>。</li>
            </ul>
          </el-collapse-item>
          <el-collapse-item name="4" style="">
            <template #title>
                  <span style="font-size: large; display: flex; align-items: center"><el-icon>
                      <Checked />
                    </el-icon><b style="margin-left: 4px">算法公示卡</b></span>
            </template>
            <table id="al_card">
              <tbody>
              <tr>
                <td>算法代号</td>
                <td>一图流_标准 v6.0</td>
                <td>更新时间</td>
                <td>
                  <!-- {{ updateTime }} -->
                </td>
              </tr>
              <tr>
                <td>数据源</td>
                <td>企鹅物流</td>
                <td>基准</td>
                <td>常驻关卡</td>
              </tr>
              <tr>
                <td>计算引擎</td>
                <td>yituliuBackEnd</td>
                <td>样本阈值</td>
                <td>300</td>
              </tr>
              <tr>
                <td>需求目标</td>
                <td>无限需求</td>
                <td>EXP系数</td>
                <td>0.625</td>
              </tr>
              </tbody>
            </table>
          </el-collapse-item>
          <el-collapse-item name="5" style="">
            <template #title>
                  <span style="font-size: large; display: flex; align-items: center">
                    <el-icon>
                      <Warning />
                    </el-icon><b style="margin-left: 4px">版权声明与许可协议</b>
                  </span>
            </template>
            网站所涉及的公司名称、商标、产品等均为其各自所有者的资产，仅供识别。网站内使用的游戏图片、动画、音频、文本原文，仅用于更好地表现游戏资料，其版权属于 Arknights/上海鹰角网络科技有限公司。<br>
            除非另有声明，网站其他内容采用<a href="https://creativecommons.org/licenses/by-nc/4.0/deed.zh">知识共享 署名-非商业性使用 4.0 国际
            许可协议</a>进行许可。转载、公开或以任何形式复制、发行、再传播本页任何内容时，必须注明从明日方舟一图流转载，并提供版权标识、许可协议标识、免责标识和作品链接，且链接需直接指向所引用的页面；且未经许可不得将本站内容或由其衍生作品用于商业目的。<br>
            本项目为无偿开源项目，致力于方便明日方舟玩家。如有开发/数据分析/设计/美工经验，欢迎来<a href="https://jq.qq.com/?_wv=1027&k=ZmORnr5F">开发群</a>一叙。
          </el-collapse-item>
        </el-collapse>
      </el-card>
    </div>
  </div>
</template>