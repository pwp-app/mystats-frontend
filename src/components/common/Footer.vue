<template>
    <div class="footer">
        <el-row class="row-copyright">
            <el-col :span="24">
                <span v-if="endYear == null">
                    Copyright &copy; {{startYear}} <a class="orgLink" :href="orgLink">{{org}}</a><span class="author-split">|</span>
                    <template v-if="author != null">Developed by {{author}}</template>
                </span>
                <span v-else>
                    Copyright &copy; {{startYear}} - {{endYear}} <a :href="orgLink">{{org}}</a><span class="author-split">|</span>
                    <template v-if="author != null">Developed by {{author}}</template>
                </span>
            </el-col>
        </el-row>
    </div>
</template>

<script>
export default {
    name: "common.footer",
    data() {
        return {
            org: "pwp.app",
            orgLink: "https://pwp.app",
            startYear: this.dayjs().format("YYYY"),
            endYear: null,
            author: "BackRunner"
        };
    }
};
</script>

<style lang="less" scope>
.footer {
    margin-top: 6rem;
    margin-bottom: 1.5rem;
}
.orgLink{
    color: #909399;
    transition: 100ms;
}
.orgLink:hover{
    cursor: pointer;
    color: #606266;
}
.orgLink:focus{
    color: #909399;
}
.row-copyright {
    letter-spacing: 0.05rem;
    margin-top: 1.125rem;
    font-size: 0.875rem;
    color: #909399;
    text-align: center;
    user-select: none;
    -webkit-user-drag: none;
}
.author-split{
    margin: 0 0.8rem;
}
@media (max-width: 1600px) {
    .footer {
        margin-top: 3rem;
        margin-bottom: 1.5rem;
    }
}
@media (max-width: 768px) {
    .footer-split{
        display: none;
    }
}
</style>
