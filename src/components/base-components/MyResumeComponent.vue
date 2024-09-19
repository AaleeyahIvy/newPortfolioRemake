<template>
    <div>
        <p>{{ aboutpage }}</p>
        <pdf src="../../assets/files/Resume.docx (1).pdf"></pdf>
    </div>
</template>
<script>    
import pdf from 'vue-pdf';
export default {
    name: 'MyResumeComponent',
    components: {
        pdf
    },
    data() {
        return {
            aboutpage: 'This is the Resume page'
        }
    }
}
</script>