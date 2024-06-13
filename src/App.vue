<script>
export default {
    data() {
        return {
            text: 'Hello',
            color: 'border-orange-300 border-4 rounded-2xl',
            textarea: document.getElementById('textarea'),
            addition: false,
            list: true,
            AddButton: document.getElementById('AddButton')
        }
    },
    methods: {
        ChangeBGColor: function () {
            textarea.classList.add('bg-cyan-800')
        },
        ChangeBGColorBack: function () {
            textarea.classList.remove('bg-cyan-800')
        },
        AddPage: function () {
            this.list = !this.list
            this.addition = !this.addition
            AddButton.textContent = 'Назад'

        }
    }
}
</script>
<template>
    <div class="bg-cyan-950 w-full h-96">
        <div class="pt-3.5 mb-1 mx-40 bg-cyan-950">
            <button @click="AddPage" id="AddButton"
                class="bg-violet-800 rounded-lg border-2 border-violet-700 mb-3 shadow-lg shadow-violet-800/50 hover:bg-violet-700">Добавить</button>
        </div>
        <div v-if="addition">
            это добавление
        </div>
        <ol v-if="list">
            <li>
                <div @mouseover="ChangeBGColor" @mouseout="ChangeBGColorBack"
                    class="mx-40 bg-cyan-900 grid grid-cols-3 gap-x-4 h-40 rounded-lg hover:shadow-2xl hover:shadow-sky-600/50 shadow-xl shadow-sky-600/30 hover:bg-cyan-800 ">
                    <div class="col-span-2 my-0.5 mx-1 ">
                        <h1 class="text-lime-50 text-2xl">title это моя ссылка</h1>
                        <button
                            class="text-gray-400 text-lg text-left w-full px-1.5 text-ellipsis overflow-hidden whitespace-nowrap">https://code.mu/ru/javascript/framework/vue/book/prime/basis/object-data/</button>
                        <textarea readonly="true" id="textarea"
                            class="text-sm mt-2.5 text-gray-500 bg-cyan-900 whitespace-normal cursor-auto w-full outline-none border-none overflow-hidden resize-none h-1/2 ">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Praesentium dolores dignissimos itaque sint quasi maiores ratione, commodi deleniti iusto eaque et illum, velit quis nihil placeat corrupti soluta temporibus alias? Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci nostrum ipsam cum quis! Vitae quisquam laboriosam commodi, veniam voluptatum amet modi minima officia, consequatur mollitia ipsum cupiditate illum soluta eos?</textarea>
                    </div>
                    <div class="my-0.5 mx-1">
                        <ol class=" place-content-center text-center text-sm grid grid-cols-2 gap-2 ">
                            <li><button :class="color">sometexthere1</button></li>
                        </ol>
                    </div>
                </div>
            </li>
        </ol>
    </div>
</template>
