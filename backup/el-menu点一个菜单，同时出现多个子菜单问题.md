根本原因：多个子菜单使用了相同的index，被认为是同一个菜单
间接原因：路由设置的path值相同，又使用了item.path作为el-menu-item的index，导致菜单的index相同