<template>
    <div>
        <text>setTimeout timeout=3000</text>
        <div class="wrapper-top">
            <text test-id="setTimeout" class="t" @click="stimeout">SetTimeOut</text>
            <text test-id="clearTimeout" class="t" @click="ctimeout">ClearTimeOut</text>
        </div>
        <text class="content" test-id="timeout">{{timeout_content}}</text>

        <text style="margin-top: 100px">setInterval interval=3000</text>
        <div class="wrapper-bottom">
            <text test-id="setInterval" class="t" @click="sinterval">SetInterval</text>
            <text test-id="clearInterval" class="t" @click="cinterval">ClearInterval</text>
        </div>
        <text test-id="interval" class="content">{{interval_content}}</text>
    </div>
</template>

<style>
    .wrapper-top {
        height: 100px;
        width: 750px;
        background-color: yellow;
        align-items: center;
        flex-direction: row
    }
    
    .wrapper-bottom {
        height: 100px;
        width: 750px;
        background-color: red;
        align-items: center;
        flex-direction: row
    }

    .t {
        font-size: 36px;
        color: #ffffff;
        align-items: center;
        flex: 1;
        text-align: center;
    }

    .content {
        font-size: 32px;
        background-color: blue;
        color: black;
        text-align: center;
    }
</style>

<script>
    var tfnId;
    var ifnId;
    module.exports = {
        data: function () {
            return {
                timeout_content: 0,
                interval_content: 0
            }
        },
        methods: {
            stimeout: function () {
                var self = this;
                tfnId = setTimeout(function () {
                    self.timeout_content += 1
                }, 3000);
            },
            ctimeout: function () {
                clearTimeout(tfnId)
            },
            sinterval: function () {
                var self = this;
                ifnId = setInterval(function () {
                    self.interval_content += 1
                }, 3000);
            },
            cinterval: function () {
                clearInterval(ifnId)
            }
        }
    }
</script>