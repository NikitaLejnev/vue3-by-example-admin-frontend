<template>
  <Form @submit="onSubmit" :validation-schema="schema">
    <Field v-slot="{ field, errors }" v-model="name" name="name">
      <div class="p-col-12">
        <div class="p-inputgroup">
          <InputText placeholder="Name" :class="{ 'p-invalid': errors.length > 0 }" v-bind="field" />
        </div>
        <small class="p-error" v-if="errors.length > 0">Name is invalid.</small>
      </div>
    </Field>
    <Field v-slot="{ field, errors }" v-model="description" name="description">
      <div class="p-col-12">
        <div class="p-inputgroup">
          <Textarea
            placeholder="Description"
            :class="{ 'p-invalid': errors.length > 0 }"
            v-bind="field"
          />
        </div>
        <small class="p-error" v-if="errors.length > 0">Description is invalid</small>
      </div>
    </Field>
    <Field v-slot="{ field, errors }" v-model="imageUrl" name="imageUrl">
      <div class="p-col-12">
        <div class="p-inputgroup">
          <InputText
            placeholder="Image URL"
            :class="{ 'p-invalid': errors.length > 0 }"
            v-bind="field"
          />
        </div>
        <small class="p-error" v-if="errors.length > 0">Image URL is invalid.</small>
      </div>
    </Field>
    <div class="p-col-12">
      <Button label="Add" type="submit" />
    </div>
  </Form>
</template>
