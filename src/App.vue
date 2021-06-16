<template>
    <div id="app">
        <input class="initialData" v-model="text" placeholder="Введите текст" autofocus>
        <convertedData :text="convertedText" />
    </div>
</template>

<script>
import convertedData from '@/components/convertedData'

export default {
    data() {
        return {
            text: ''
        }
    },
    components: {
        convertedData
    },
    computed: {
        convertedText: function() {
          const chars = [
                'в',
                'без',
                'до',
                'для',
                'за',
                'через',
                'над',
                'по',
                'из',
                'у',
                'около',
                'под',
                'о',
                'про',
                'на',
                'к',
                'перед',
                'при',
                'с',
                'между',
                'ли',
                'ль',
                'а',
                'как',
                'не',
                'ни',
                'нет',
                'да',
                'так',
                'вот',
                'лишь',
                'почти',
                'хоть',
                'чуть',
                'именно',
                'точно',
                'бы',
                'б',
            ];
          const strMap = this.text.trim().split(' ');
          let newStr = '';

          if(this.text.length !== 0) {
            for (const item in strMap) {
              if (chars.indexOf(strMap[item]) === -1) {
                newStr += strMap[item] + " ";
                console.log('true');
              } else {
                newStr += strMap[item] + "&nbsp;";
                console.log('false');
              }
            }

            return newStr;
          }
        }
    }
}
</script>

<style>
#app {
    display: flex;
    justify-content: space-between;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

.initialData {
    width: 45vw;
    max-width: 45vw;
    padding: 20px;
}
</style>
