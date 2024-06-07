<template>
    <section>
        <div class="my-64 mx-auto max-w-screen-md">
            <h2 class="mb-4 text-4xl tracking-tight font-extrabold text-center text-gray-900 dark:text-white">Contact Me</h2>
            <p class="mb-8 lg:mb-10 font-light text-center text-gray-500 dark:text-gray-400 sm:text-xl">If you'd like to get in touch, please fill out the form below.</p>
            <div className="formcarry-container">
                <form @submit.prevent="onSubmit" class="space-y-8">
                    <div className="formcarry-block">
                        <label for="name" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Name</label>
                        <input type="text" v-model="name" id="name" placeholder="John Doe" class="shadow-sm dark:bg-opacity-50 bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg outline-none focus:ring-emerald-500 focus:border-emerald-500 block w-full p-2.5 dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-emerald-500 dark:focus:border-emerald-500 dark:shadow-sm-light"/>
                    </div>
                    <div className="formcarry-block">
                        <label for="email" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Email Address</label>
                        <input type="email" v-model="email" id="email" placeholder="john@doe.com"  class="shadow-sm dark:bg-opacity-50 bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg outline-none focus:ring-emerald-500 focus:border-emerald-500 block w-full p-2.5 dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-emerald-500 dark:focus:border-emerald-500 dark:shadow-sm-light"/>
                    </div>
                    <div className="formcarry-block">
                        <label for="message" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300">Message</label>
                        <textarea rows="6" v-model="message" id="message" placeholder="Enter your message..." class="shadow-sm dark:bg-opacity-50 outline-none bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-emerald-500 focus:border-emerald-500 block w-full p-2.5 dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-emerald-500 dark:focus:border-emerald-500 dark:shadow-sm-light"></textarea>
                    </div>
                    <div className="formcarry-block flex justify-center">
                        <!-- <button :disabled="message.length <= 0" type="submit" class="min-w-[10rem] py-3 px-5 text-sm font-medium text-center text-white rounded-lg bg-emerald-700 sm:w-fit hover:bg-emerald-800 focus:ring-4 focus:outline-none focus:ring-emerald-300 dark:bg-emerald-600 dark:hover:bg-emerald-700 dark:focus:ring-emerald-800" :class="[message.length <= 0 ? 'bg-slate-500' : '']">Send</button> -->
                        <button type="submit"
                        class="text-white rounded-full py-2 bg-transparent px-6 transition duration-500 hover:shadow-lg hover:shadow-emerald-500/20 bg-emerald-500 dark:bg-transparent dark:border dark:border-emerald-400"
                        @click="toggleWorkPage"
                        >
                        Send
                        </button>
                    </div>

                    <div v-if="showNotification()" class="formcarry-block">
                        <div :class="`formcarry-message-block fc-${icon} active`">
                            <div class="fc-message-icon"></div>
                            <div class="fc-message-content">{{ errorMessage() }}</div>
                            <div class="fc-message-close" @click="resetStates()"></div>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </section>
</template>

<script>
import { ref } from 'vue';

export default {
    setup() {
        const name = ref('');
        const email = ref('');
        const message = ref('');
        const error = ref('');
        const submitted = ref(false);

        const resetStates = () => {
            submitted.value = false;
            error.value = '';
        };

        const resetForm = () => {
            name.value = '';
            email.value = '';
            message.value = '';
        };

        const onSubmit = async () => {
            resetStates();

            try {
                const response = await fetch("https://formcarry.com/s/mB1Qk1B-AIS", {
                    method: 'POST',
                    headers: {
                        "Accept": "application/json",
                        "Content-Type": "application/json"
                    },
                    body: JSON.stringify({ name: name.value, email: email.value, message: message.value })
                });

                const data = await response.json();

                if (data.code === 200) {
                    submitted.value = true;
                    resetForm();
                } else if (data.code === 422) {
                    error.value = data.message;
                } else {
                    error.value = data.message;
                }
            } catch (err) {
                error.value = err.message ? err.message : err;
            }
        };

        const showNotification = () => submitted.value || error.value;
        const icon = () => error.value ? 'error' : 'success';
        const errorMessage = () => error.value ? error.value : "Thanks for reaching out!, we'll get back to you soon.";

        return {
            name,
            email,
            message,
            onSubmit,
            showNotification,
            icon,
            errorMessage,
            resetStates
        };
    }
}
</script>