<template>
    <div>
        <p>
            {{alertMessage}}
        </p>
        {{parentMessage}}
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue, Watch } from 'vue-property-decorator';

@Component
export default class Children extends Vue {
    @Prop() parentMessage? : string; //parentMessage의 속성을 optional로 설정 ?
    alertMessage : string = '';

    @Watch('parentMessage') //immediate = 속성의 현재값으로 parentMessage를 즉시 호출한다, deep = 불러오는 것이 객체일 경우, 객체 내부의 속성까지 감시한다
    update(value: string, oldValue: string){
        this.alertMessage = '메세지를 업로드했습니다.'
    }
}
</script>
