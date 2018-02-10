<template>
  <div id="preview">
    <h1>{{resume.profile.name || '请填写姓名'}}</h1>
    <p>{{resume.profile.city || '请填写城市'}}</p> | <p>{{resume.profile.birth || '请填写出生年月'}}</p>

    <section   class="work">
      <h2>工作经历</h2>
  <ul>
    <li v-for="work in resume.workHistory">
      {{work.company || '请填写公司' }}
      {{work.content ||  '请填写工作内容'}}
    </li>
  </ul>
    </section>
    <section class="study">
      <h2>学习经历</h2>
      <ul>
        <li v-for="study in resume.studyHistory">
          {{study.school || '请填写学校'}}
          {{study.duration|| '请填写时间'}}
          {{study.degree || '请填写学位'}}
        </li>
      </ul>
    </section>
    <section class="project">
      <h2>项目经历</h2>
      <ul>
        <li v-for="project in resume.projectHistory">
          {{project.projectName || '请填写项目名称'}}
          {{project.introduction || '请填写项目简介'}}
          {{project.duration || '请填写时间'}}
        </li>
      </ul>
    </section>
    <section class="interest">
        <h2>兴趣爱好</h2>
      <ul>
        <li v-for="h in resume.hobbies">
          {{h.hobby ||'请填写兴趣爱好'}}
        </li>
      </ul>
    </section>
    <section class="contact">
      <h2>联系方式</h2>
      <p>{{resume.Information.phone_number || '请填写联系电话'}}</p>
      <p>{{resume.Information.WeiXin || '请填写微信'}}</p>
      <p> {{resume.Information.email || '请填写邮箱'}}</p>
      <p>{{resume.Information.address || '请填写地址'}}</p>

    </section>
  </div>
</template>
<script>
  export  default {
    name:'Preview',
    props:['resume'],
    methods:{

      IsEmpty(object){
        let empty = true
        for(let key in object){
          if(object[key]){
            empty = false
            break
          }

        }
        return empty
      },
      filter(array){
        return array.filter(item => !this.IsEmpty(item))
      }

    }
  }
</script>
<style lang="scss">
  #preview{

    border-radius: 4px;
    height:100%;
    background:#ffffff;
    box-shadow: 0 1px 3px 0 rgba(0,0,0,0.25);

  }
</style>
