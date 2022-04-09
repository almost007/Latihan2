<template>
<div v-if="!task.isDone || ok"
          :class="[
            'item-task d-flex align-items-start border-bottom pt-3 pb-4',
            isGrid ? 'col-12 col-md-6 col-lg-4' : 'col-12',
          ]"
        >
          <input
            type="checkbox"
            name="status"
            id="task"
            class="me-2 mt-2"
            :checked="task.isDone"
            v-model="task.isDone"
          />
          <div

            :class="[
              'd-flex flex-column',
              task.isDone ? 'text-decoration-line-through fst-italic' : '',
            ]"
          >
            <A1><div class="title-task mb-1"><b>{{ task.title }}</b></div></A1>
            <div class="description-task small text-muted">
            <div class="btn btn-primary btn-sm" > {{ task.category }}  </div>
            <div class="description-task small text-muted">
              {{ task.description }}
            </div>

            </div>
          </div>
        </div>
</template>

<script>
export default {
props: {
task: Object,
ok: false,
 all: false,
project: false,
research: false,



isGrid: {
type: Boolean,
required: true,
default: false
}

}
}
</script>
