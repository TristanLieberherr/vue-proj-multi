<template>
  <v-card style="margin-bottom: 50px" elevation="2">
    <v-card-title style="justify-content: center">
      {{ project.title }}
    </v-card-title>
    <div v-html="project.description"></div>

    <v-row>
      <v-col>
        <v-chip-group column>
          <v-chip v-for="(tag, index) in project.tags" :key="index">
            {{ tag.name }}
          </v-chip>
        </v-chip-group>
      </v-col>
    </v-row>

    <v-chip-group column>
      <v-chip v-for="(orientation, index) in project.orientations" :key="index">
        {{ orientation.name }}
      </v-chip>
    </v-chip-group>
  </v-card>
</template>

<script>
import "quill/dist/quill.core.css";
import "quill/dist/quill.snow.css";
import "quill/dist/quill.bubble.css";
export default {
  name: "ProjectComponent",
  props: {
    project: {
      type: Object,
      required: true,
    },
  },
};
</script>
