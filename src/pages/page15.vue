<template>
  <div>
    <div>
      <el-input v-model="input" placeholder="请输入内容"></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input v-model="input1" :disabled="true" placeholder="请输入内容"></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input v-model="input2" clearable></el-input>
    </div>

    <div style="margin-top: 20px;">属性方式：
      <el-input v-model="input3" placeholder="请输入内容" suffix-icon="el-icon-date"></el-input>
      <el-input v-model="input4" placeholder="请输入内容" prefix-icon="el-icon-search"></el-input>
    </div>

    <div style="margin-top: 20px;">slot方式：
      <el-input v-model="input5" placeholder="请输入内容"><i slot="suffix" class="el-input__icon el-icon-date"></i></el-input>
      <div style="margin-top: 20px;"></div>
      <el-input v-model="input6" placeholder="请输入内容"><i slot="prefix" class="el-input__icon el-icon-search"></i></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input v-model="textarea1" type="textarea" :row="2" placeholder="请输入内容"></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input type="textarea" autosize placeholder="请输入内容" v-model="textarea2" style="width: 200px;"></el-input>
      <div style="margin-top: 20px;"></div>
      <el-input type="textarea" :autosize="{ minRows: 2, maxRows: 4 }" placeholder="请输入内容" v-model="textarea3" style="width: 200px;"></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input placeholder="请输入内容" v-model="input7">
        <template slot="prepend">Http://</template>
        <template slot="append">.com</template>
      </el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input placeholder="请输入内容" v-model="input8" class="input-with-select">
        <el-select v-model="input8" slot="prepend" placeholder="请选择">
          <el-option label="餐厅名" value="1"></el-option>
          <el-option label="订单号" value="2"></el-option>
          <el-option label="电话" value="3"></el-option>
        </el-select>
        <el-button slot="append" icon="el-icon-search"></el-button>
      </el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-input placeholder="请输入内容" suffix-icon="el-icon-date" v-model="input9"></el-input>
      <el-input placeholder="请输入内容" suffix-icon="el-icon-date" v-model="input9" size="medium"></el-input>
      <el-input placeholder="请输入内容" suffix-icon="el-icon-date" v-model="input9" size="small"></el-input>
      <el-input placeholder="请输入内容" suffix-icon="el-icon-date" v-model="input9" size="mini"></el-input>
    </div>

    <div style="margin-top: 20px;">
      <el-row class="demo-autocomplete">
        <el-col :span="12">
          <div class="sub-title">激活即列出所有输入建议</div>
          <el-autocomplete
            class="inline-input"
            v-model="state1"
            :fetch-suggestions="querySearch"
            placeholder="请输入内容"
            @select="handleSelect"></el-autocomplete>
        </el-col>
        <el-col :span="12">
          <div class="sub-title">输入后匹配输入建议</div>
          <el-autocomplete
            class="inline-input"
            v-model="state2"
            :fetch-suggestions="querySearch"
            placeholder="请输入内容"
            :trigger-on-focus="false"
            @select="handleSelect"></el-autocomplete>
        </el-col>
      </el-row>
    </div>

    <div style="margin-top: 20px;">
      <el-row class="demo-autocomplete">
        <el-col :span="12">
          <el-autocomplete
            popper-class="my-autocomplete"
            v-model="state3"
            :fetch-suggestions="querySearch"
            placeholder="请输入内容"
            @select="handleSelect">
            <i class="el-icon-edit el-input__icon" slot="suffix" @click="handleIconClick"></i>
            <template slot-scope="{ item }">
              <div class="name">{{ item.value }}</div>
              <div class="addr">{{ item.address }}</div>
            </template>
          </el-autocomplete>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      input: '',
      input1: '',
      input2: '',
      input3: '',
      input4: '',
      input5: '',
      input6: '',
      input7: '',
      input8: '',
      input9: '',
      textarea1: '',
      textarea2: '',
      textarea3: '',
      restaurants: [],
      state1: '',
      state2: '',
      state3: ''
    };
  },
  methods: {
    querySearch(queryString, cb) {
      var restaurants = this.restaurants;
      var results = queryString ? restaurants.filter(this.createFilter(queryString)) : restaurants;
      cb(results);
    },
    createFilter(queryString) {
      return (restaurant) => {
        return (restaurant.value.toLowerCase().indexOf(queryString.toLowerCase()) === 0);
      }
    },
    loadAll() {
      return [
        { "value": "三全鲜食（北新泾店）", "address": "长宁区新渔路144号" },
        { "value": "Hot honey 首尔炸鸡（仙霞路）", "address": "上海市长宁区淞虹路661号" },
        { "value": "新旺角茶餐厅", "address": "上海市普陀区真北路988号创邑金沙谷6号楼113" },
        { "value": "泷千家(天山西路店)", "address": "天山西路438号" },
        { "value": "胖仙女纸杯蛋糕（上海凌空店）", "address": "上海市长宁区金钟路968号1幢18号楼一层商铺18-101" },
        { "value": "贡茶", "address": "上海市长宁区金钟路633号" },
        { "value": "豪大大香鸡排超级奶爸", "address": "上海市嘉定区曹安公路曹安路1685号" },
        { "value": "茶芝兰（奶茶，手抓饼）", "address": "上海市普陀区同普路1435号" },
        { "value": "十二泷町", "address": "上海市北翟路1444弄81号B幢-107" },
        { "value": "星移浓缩咖啡", "address": "上海市嘉定区新郁路817号" },
        { "value": "阿姨奶茶/豪大大", "address": "嘉定区曹安路1611号" },
        { "value": "新麦甜四季甜品炸鸡", "address": "嘉定区曹安公路2383弄55号" },
        { "value": "Monica摩托主题咖啡店", "address": "嘉定区江桥镇曹安公路2409号1F，2383弄62号1F" },
        { "value": "浮生若茶（凌空soho店）", "address": "上海长宁区金钟路968号9号楼地下一层" },
        { "value": "NONO JUICE  鲜榨果汁", "address": "上海市长宁区天山西路119号" },
        { "value": "CoCo都可(北新泾店）", "address": "上海市长宁区仙霞西路" },
        { "value": "快乐柠檬（神州智慧店）", "address": "上海市长宁区天山西路567号1层R117号店铺" },
        { "value": "Merci Paul cafe", "address": "上海市普陀区光复西路丹巴路28弄6号楼819" },
        { "value": "猫山王（西郊百联店）", "address": "上海市长宁区仙霞西路88号第一层G05-F01-1-306" },
        { "value": "枪会山", "address": "上海市普陀区棕榈路" },
        { "value": "纵食", "address": "元丰天山花园(东门) 双流路267号" },
        { "value": "钱记", "address": "上海市长宁区天山西路" },
        { "value": "壹杯加", "address": "上海市长宁区通协路" },
        { "value": "唦哇嘀咖", "address": "上海市长宁区新泾镇金钟路999号2幢（B幢）第01层第1-02A单元" },
        { "value": "爱茜茜里(西郊百联)", "address": "长宁区仙霞西路88号1305室" },
        { "value": "爱茜茜里(近铁广场)", "address": "上海市普陀区真北路818号近铁城市广场北区地下二楼N-B2-O2-C商铺" },
        { "value": "鲜果榨汁（金沙江路和美广店）", "address": "普陀区金沙江路2239号金沙和美广场B1-10-6" },
        { "value": "开心丽果（缤谷店）", "address": "上海市长宁区威宁路天山路341号" },
        { "value": "超级鸡车（丰庄路店）", "address": "上海市嘉定区丰庄路240号" },
        { "value": "妙生活果园（北新泾店）", "address": "长宁区新渔路144号" },
        { "value": "香宜度麻辣香锅", "address": "长宁区淞虹路148号" },
        { "value": "凡仔汉堡（老真北路店）", "address": "上海市普陀区老真北路160号" },
        { "value": "港式小铺", "address": "上海市长宁区金钟路968号15楼15-105室" },
        { "value": "蜀香源麻辣香锅（剑河路店）", "address": "剑河路443-1" },
        { "value": "北京饺子馆", "address": "长宁区北新泾街道天山西路490-1号" },
        { "value": "饭典*新简餐（凌空SOHO店）", "address": "上海市长宁区金钟路968号9号楼地下一层9-83室" },
        { "value": "焦耳·川式快餐（金钟路店）", "address": "上海市金钟路633号地下一层甲部" },
        { "value": "动力鸡车", "address": "长宁区仙霞西路299弄3号101B" },
        { "value": "浏阳蒸菜", "address": "天山西路430号" },
        { "value": "四海游龙（天山西路店）", "address": "上海市长宁区天山西路" },
        { "value": "樱花食堂（凌空店）", "address": "上海市长宁区金钟路968号15楼15-105室" },
        { "value": "壹分米客家传统调制米粉(天山店)", "address": "天山西路428号" },
        { "value": "福荣祥烧腊（平溪路店）", "address": "上海市长宁区协和路福泉路255弄57-73号" },
        { "value": "速记黄焖鸡米饭", "address": "上海市长宁区北新泾街道金钟路180号1层01号摊位" },
        { "value": "红辣椒麻辣烫", "address": "上海市长宁区天山西路492号" },
        { "value": "(小杨生煎)西郊百联餐厅", "address": "长宁区仙霞西路88号百联2楼" },
        { "value": "阳阳麻辣烫", "address": "天山西路389号" },
        { "value": "南拳妈妈龙虾盖浇饭", "address": "普陀区金沙江路1699号鑫乐惠美食广场A13" }
      ];
    },
    handleSelect(item) {
      console.log(item);
    },
    handleIconClick(ev) {
      console.log(ev);
    }
  },
  mounted() {
    this.restaurants = this.loadAll();
  }
}
</script>
<style>
.el-select .el-input { width: 130px; }
.input-with-select .el-input-group__prepend { background-color: #fff; }
.my-autocomplete li { line-height: normal; padding: 7px; }
.my-autocomplete li .name { text-overflow: ellipsis; overflow: hidden; }
.my-autocomplete li .addr { font-size: 12px; color: #b4b4b4; }
.my-autocomplete li .highlighted .addr { color: #ddd; }
</style>
