<template>
  <div class="w-full text-center flex-col justify-center h-fit">
    <!-- <label for=""></label> -->

    <el-form
      ref="ruleFormRef"
      :model="ruleForm"
      :rules="rules"
      label-width="auto"
      class="demo-ruleForm"
      :size="formSize"
      label-position="top"
      status-icon
    >
      <div class="md:flex flex-wrap w-full justify-between gap-y-3">
        <el-form-item class="md:w-[48%] w-full" label="Name" prop="name">
          <el-input v-model="ruleForm.name" />
        </el-form-item>
        <el-form-item class="md:w-[48%] w-full" label="Company" prop="company">
          <el-input v-model="ruleForm.company" />
        </el-form-item>
        <el-form-item class="md:w-[48%] w-full me-1" label="e-mail" prop="email">
          <el-input v-model="ruleForm.email" />
        </el-form-item>
        <el-form-item class="md:w-[48%] w-full" label="Phone" prop="phone">
          <el-input v-model="ruleForm.phone" />
        </el-form-item>
      </div>

      <!-- <el-form-item label="Activity zone" prop="region">
        <el-select v-model="ruleForm.region" placeholder="Activity zone">
          <el-option label="Zone one" value="shanghai" />
          <el-option label="Zone two" value="beijing" />
        </el-select>
      </el-form-item>
      <el-form-item label="Activity count" prop="count">
        <el-select-v2 v-model="ruleForm.count" placeholder="Activity count" :options="options" />
      </el-form-item>
      <el-form-item label="Activity time" required>
        <el-col :span="11">
          <el-form-item prop="date1">
            <el-date-picker
              v-model="ruleForm.date1"
              type="date"
              aria-label="Pick a date"
              placeholder="Pick a date"
              style="width: 100%"
            />
          </el-form-item>
        </el-col>
        <el-col class="text-center" :span="2">
          <span class="text-gray-500">-</span>
        </el-col>
        <el-col :span="11">
          <el-form-item prop="date2">
            <el-time-picker
              v-model="ruleForm.date2"
              aria-label="Pick a time"
              placeholder="Pick a time"
              style="width: 100%"
            />
          </el-form-item>
        </el-col>
      </el-form-item> -->

      <!-- <el-form-item label="Activity location" prop="location">
        <el-segmented v-model="ruleForm.location" :options="locationOptions" />
      </el-form-item> -->

      <el-form-item label=" I am looking for service like..." prop="type">
        <!-- <div class="flex-col">
          <slot class="w-full" name="service"></slot> -->
        <el-checkbox-group v-model="ruleForm.type">
          <el-checkbox value="Online activities" name="type"> 會議記錄e指通 </el-checkbox>
          <el-checkbox value="translation-PPT" name="type"> 文件快譯通 - PPT </el-checkbox>
          <el-checkbox value="translation-Word" name="type"> 文件快譯通 -Word </el-checkbox>
          <el-checkbox value="real-time interpretation" name="type"> 即時口譯蒟蒻 </el-checkbox>
          <el-checkbox value="AI service" name="type"> AI即時小幫手 </el-checkbox>
          <el-checkbox value="auto replier" name="type"> 自動回信快手 </el-checkbox>
          <el-checkbox value="others" name="type"> 其他 </el-checkbox>
        </el-checkbox-group>
        <!-- </div> -->
      </el-form-item>
      <!-- <el-form-item label="Resources" prop="resource">
        <el-radio-group v-model="ruleForm.resource">
          <el-radio value="Sponsorship">Sponsorship</el-radio>
          <el-radio value="Venue">Venue</el-radio>
        </el-radio-group>
      </el-form-item> -->
      <!-- <el-form-item label="Activity form" prop="desc" class="max-w-[900px]">
        <el-input v-model="ruleForm.desc" type="textarea" />
      </el-form-item> -->
      <!-- <el-form-item>
        <el-button type="primary" @click="submitForm(ruleFormRef)"> Create </el-button>
        <el-button @click="resetForm(ruleFormRef)">Reset</el-button>
      </el-form-item> -->
    </el-form>
  </div>
</template>

<style scoped lang="scss">
#formItem {
  .el-form-item__label {
    color: white !important;
  }
  /* --el-form-item__label-color: white !important; */
}
</style>
<script setup>
import { reactive, ref } from 'vue'
// import { ComponentSize, FormInstance, FormRules } from 'element-plus'

// interface RuleForm {
//   name: string
//   region: string
//   count: string
//   date1: string
//   date2: string
//   delivery: boolean
//   location: string
//   type: string[]
//   resource: string
//   desc: string
// }

const formSize = ref('default')
const ruleFormRef = ref()
const ruleForm = reactive({
  name: 'Hello',
  company: 'Dexatek',
  email: 'xxx@mail.com',
  phone: '0212345678',
  // region: '',
  // count: '',
  // date1: '',
  // date2: '',
  // delivery: false,
  // location: '',
  type: []
  // resource: '',
  // desc: ''
})

// const locationOptions = ['Home', 'Company', 'School']

const rules = reactive({
  name: [
    { required: true, message: 'Please input  name', trigger: 'blur' },
    { min: 3, max: 5, message: 'Length should be 3 to 5', trigger: 'blur' }
  ],
  company: [
    { required: true, message: 'Please input company name', trigger: 'blur' },
    { min: 3, max: 20, message: 'Length should be 3 to 20', trigger: 'blur' }
  ],
  email: [
    {
      required: true,
      message: 'Please input email address',
      trigger: 'blur'
    },
    {
      type: 'email',
      message: 'Please input correct email address',
      trigger: ['blur', 'change']
    }
  ],
  phone: [
    {
      required: true,
      message: 'Please input phone number',
      trigger: 'blur'
    },
    { min: 10, max: 10, message: 'Length should be 10', trigger: 'blur' }
  ],

  // region: [
  //   {
  //     required: true,
  //     message: 'Please select Activity zone',
  //     trigger: 'change'
  //   }
  // ],
  // count: [
  //   {
  //     required: true,
  //     message: 'Please select Activity count',
  //     trigger: 'change'
  //   }
  // ],
  // date1: [
  //   {
  //     type: 'date',
  //     required: true,
  //     message: 'Please pick a date',
  //     trigger: 'change'
  //   }
  // ],
  // date2: [
  //   {
  //     type: 'date',
  //     required: true,
  //     message: 'Please pick a time',
  //     trigger: 'change'
  //   }
  // ],
  // location: [
  //   {
  //     required: true,
  //     message: 'Please select a location',
  //     trigger: 'change'
  //   }
  // ],
  type: [
    {
      type: 'array',
      required: true,
      message: 'Please select at least one activity type',
      trigger: 'change'
    }
  ]
  // resource: [
  //   {
  //     required: true,
  //     message: 'Please select activity resource',
  //     trigger: 'change'
  //   }
  // ],
  // desc: [{ required: true, message: 'Please input activity form', trigger: 'blur' }]
})

const submitForm = async (formEl) => {
  if (!formEl) return
  await formEl.validate((valid, fields) => {
    if (valid) {
      console.log('submit!')
    } else {
      console.log('error submit!', fields)
    }
  })
}

const resetForm = (formEl) => {
  if (!formEl) return
  formEl.resetFields()
}

const options = Array.from({ length: 10000 }).map((_, idx) => ({
  value: `${idx + 1}`,
  label: `${idx + 1}`
}))
</script>
