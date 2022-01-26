<template>
  <Form @submit="onSubmit" :validation-schema="schema">
    <div class="p-col-12">
      <h1>Admin Log In</h1>
    </div>

    <Field v-slot="{ field, errors }" v-model="username" name="username">
      <div class="p-col-12">
        <div class="p-inputgroup">
          <InputText
            placeholder="Username"
            :class="{ 'p-invalid': errors.length > 0 }"
            v-bind="field"
          />
        </div>
        <small class="p-error" v-if="errors.length > 0">Username is invalid.</small>
      </div>
    </Field>
  </Form>
</template>
