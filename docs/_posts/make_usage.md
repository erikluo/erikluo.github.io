## make

## makefile
* [make help实现参考](https://github.com/erikluo/project-layout/blob/master/Makefile)
* makefile依赖关系中的竖线 `|`
    - 如：$(BUILD_DIR)/%.o: %.c | $(BUILD_DIR) 
    - 这个意思是: 目标的生成依赖于.c 文件和 $(BUILD_DIR)目录的存在，但是并不关心 $(BUILD_DIR)目录的修改时间。即便$(BUILD_DIR)目录的最后修改时间比目标文件更新，但是该条规则也不执行，只有 .c文件比目标文件更新时才会执行。
    - 原因如下: 因为目标文件 %.o 保存在 $(BUILD_DIR) 目录下，因此当目标文件更新时，意味着$(BUILD_DIR)目录的修改时间也更新了。如果没有那个短竖线，那么make命令认为目标依赖的.c虽然没有修改，但是$(BUILD_DIR)修改了，因此每次都会重新执行该条规则，这显然是我们不希望看到的，因此加上一条竖线 |，告诉make，仅仅关心$(BUILD_DIR)是否存在，而不关注最后修改时间。
* foreach
* 
