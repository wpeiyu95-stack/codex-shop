<script setup>
import { reactive, ref } from "vue";

const emptyForm = () => ({ name: "", phone: "", date: "", guests: "" });
const form = reactive(emptyForm());
const message = ref("");

function submitBooking() {
  const name = form.name.trim() || "您好";
  message.value = `${name}，订位请求已收到。我们会尽快电话确认。`;
  Object.assign(form, emptyForm());
}
</script>

<template>
  <section id="booking" class="booking">
    <div class="booking-copy">
      <p class="eyebrow">Reservation</p>
      <h2>预订今晚的位置</h2>
      <p>留下信息后，我们会在营业时段内确认桌位。7 人以上聚餐可备注预算和偏好。</p>
    </div>
    <form class="booking-form" @submit.prevent="submitBooking">
      <label>
        姓名
        <input v-model="form.name" type="text" name="name" placeholder="你的称呼" required />
      </label>
      <label>
        电话
        <input v-model="form.phone" type="tel" name="phone" placeholder="用于确认订位" required />
      </label>
      <label>
        日期
        <input v-model="form.date" type="date" name="date" required />
      </label>
      <label>
        人数
        <select v-model="form.guests" name="guests" required>
          <option value="">请选择</option>
          <option value="2">2 位</option>
          <option value="3-4">3-4 位</option>
          <option value="5-6">5-6 位</option>
          <option value="7+">7 位以上</option>
        </select>
      </label>
      <button class="button button-primary" type="submit">提交订位</button>
      <p class="form-message" role="status" aria-live="polite">{{ message }}</p>
    </form>
  </section>
</template>
