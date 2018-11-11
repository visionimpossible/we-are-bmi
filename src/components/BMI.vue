<template>
    <div class="container">
        <header >
            <h1>BMI Calculator</h1>
            <h3>ระบุส่วนสูง และ น้ำหนักจากนั้นกดปุ่ม<em>คำนวณ</em></h3>
        </header>
        <br/>
        <div class="form-horizontal">
            <div class="col-xs-12 form-group">
                <label for="weight" class="col-xs-4 control-label">น้ำหนัก <em>(กิโลกรัม)</em></label>
                <div class="col-xs-8"><input v-model="weight" id="weight" type="text" class="form-control"></div>
            </div>
            <div class="col-xs-12 form-group">
                <label for="height" class="col-xs-4 control-label">ส่วนสูง <em>(เซนติเมตร)</em></label>
                <div class="col-xs-8"><input v-model="height" id="height" type="text" class="form-control"></div>
            </div>
            <div class="form-group">
                <button class="btn btn-success btn-block" @click="calculate">คำนวณ</button>
            </div>
        </div>
        <div class="result">
            <span>ผลลัพธ์ของคุณคือ...</span>
            <em>{{result}}</em>
            <!-- <em>{{formatResult(result)}}</em> -->
        </div>
            <div class="content-table">
            <table class="bmi-table">
					<tbody>
						<tr>
							<td><strong>ค่า BMI</strong></td>
							<td><strong>อยู่ในเกณท์</strong></td>
							<td><strong>ภาวะเสี่ยงต่อโรค</strong></td>
						</tr>
						<tr>
							<td>30.0 ขึ้นไป</td>	
							<td>อ้วนมาก</td>
							<td>เสี่ยงต่อการเกิดโรคร้ายแรงที่แฝงมากับความอ้วน</td>
						</tr>
						<tr class="">
							<td>25.0 - 29.9</td>
							<td>อ้วน</td>						
							<td>ถึงแม้จะไม่ถึงเกณฑ์ที่ถือว่าอ้วนมาก ๆ แต่ก็ยังมีความเสี่ยงต่อการเกิดโรคที่มากับความอ้วนได้</td>
						</tr>
						<tr class="">
							<td>23.0 - 24.9</td>
							<td>น้ำหนักเกิน</td>	
							<td>ยังถือว่าเป็นกลุ่มผู้ที่มีความอ้วนอยู่บ้าง แม้จะไม่ถือว่าอ้วน</td>					
						</tr>
						<tr>
							<td>18.6 - 22.9</td>
							<td>น้ำหนักที่เหมาะสม</td>
							<td>จัดอยู่ในเกณฑ์ปกติ ห่างไกลโรคที่เกิดจากความอ้วน และมีความเสี่ยงต่อการเกิดโรคต่าง ๆ น้อยที่สุด</td>
						</tr>
						<tr>
							<td>น้อยกว่า 18.5</td>
							<td>ผอมเกินไป</td>	
							<td>น้ำหนักน้อยกว่าปกติก็ไม่ค่อยดี อาจเสี่ยงต่อการได้รับสารอาหารไม่เพียงพอหรือได้รับพลังงานไม่เพียงพอ</td>					
						</tr>
					</tbody>
				</table>
                <br />
                <br />
                
            </div>
            
        
    </div>
</template>

<script>
export default {
  name: "BMI",
  props: {
    msg: String
  },
  data () {
    return {
      weight: '65',
      height: '177',
      result: 'กดปุ่มเพื่อ "คำนวณ"'
    }
  },
  methods: {
    calculate() {
      let weight = parseFloat(this.weight)
      let height = parseFloat(this.height) / 100
      this.result = (weight / (height * height)).toFixed(2)
    },
    // formatResult(value) {
    //     let val = (value/1).toFixed(2).replace('.', ',')
    //     return val.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".")
    // }
  }
};
</script>
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.content-table {
    font: 17px 'Roboto', Tahoma, sans-serif;
    color: #666;
    
}
.content-table table {
    width: 100%;
    margin: 0 0 20px 0;
    text-align: left;
}
table {
    border-collapse: collapse;
    border-spacing: 0;
}
.content-table tr {
        transition: all .2s ease-in-out;
}
.content-table tr {
    background: none;
}
.content-table td {
    border: 1px solid #efefef;
    padding: 10px;
    color: #555;
    vertical-align: middle;
}

.result {
      font-size: 16pt;
      text-align: center;
      margin: 60px;
      span, em {
        display: block;
      }
      em {
        font-size: 2em;
      }
    }
</style>