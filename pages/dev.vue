<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6">

        <!-- Test -->
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">{{ test.title }}</h5>
            <h6 class="card-subtitle mb-2 text-muted">{{ test.description }}</h6>

            <!-- Sections -->
            <div v-for="(section, index) in test.sections"
                 :key="index" :id="`section_${index}`"
                 class="card"
            >
              <div class="card-body">
                <h5 class="card-title">{{ section.title }}</h5>

                <!-- Parts -->
                <div v-for="(part, index) in section.parts"
                     :key="index" :id="`part_${index}`"
                     class="card"
                >
                  <div class="card-body">
                    <h5 class="card-title">{{ part.title }}</h5>

                    <!-- Questions -->
                    <div v-for="(question, index) in part.questions"
                         :key="index" :id="`question_${question.number}`"
                         class="card"
                    >
                      <div class="card-body">
                        <h5 class="card-title">Question {{ question.number }}</h5>

                        <input type="text" class="form-control" v-model="question.body">
                      </div>
                    </div>

                    <!-- Group -->

                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-md-6">
        <pre>{{ test }}</pre>
      </div>
    </div>
  </div>
</template>

<script>
import { testContent } from '@/assets/testContents/01'

export default {
  data () {
    return {
      test: testContent
    }
  },
  methods: {

  }
}
</script>

<style>
.container {
  padding-top: 20px;
}
.card {
  margin-bottom: 20px;
}
</style>
