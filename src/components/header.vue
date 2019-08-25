<template>
    <div id="header">
        <div class="logo"></div>
        <div class="header-menu">
            <div class="search-bar">
                <input class="search" placeholder="搜索音乐，MV..." />
            </div>
            <div class="icons">
                <div class="user">
                    <div class="user-avatar sm">
                        <i class="lg iconfont icon-user"></i>
                    </div>
                    <span class="user-nickname">欢迎！</span>
                </div>
                <i class="lg iconfont icon-skin"></i>
                <i class="lg iconfont icon-setting"></i>
                <i class="lg iconfont icon-full"></i>
            </div>
        </div>
    </div>
</template><script>export default {
        name: 'vheader'

    }

</script><style lang="scss"scoped>
    #header {
        width: 100%;
        height: 60px;

        /*---------------导航栏------------------*/

        .logo,
        .header-menu {
            height: 100%;
        }

        .logo {
            float: left;
            margin-left: 30px;
            width: 200px;
            height: 40px;
            background: url("../../public/img/logo/logo.png");
            background-repeat: no-repeat;
        }

        .header-menu {
            font-size: 20px;
            width: calc(100% - 246px);

            .search-bar,
            .icons {
                height: 100%;
            }

            .search-bar {
                .search {
                    padding: 5px;
                    width: 100%;
                    height: 30px;
                    border-radius: 1em;
                }
            }

            .icons {
                width: 280px;

                .user {
                    overflow: hidden;
                    width: 120px;
                    text-overflow: ellipsis;
                    white-space: nowrap;
                    font-size: 15px;
                    line-height: 32px;

                    .user-avatar {
                        float: left;
                    }

                    .user-nickname {
                        margin-left: 10px;
                    }
                }
            }
        }
    }
</style>