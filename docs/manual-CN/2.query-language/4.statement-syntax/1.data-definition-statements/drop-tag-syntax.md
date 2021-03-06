# DROP TAG 语法

```ngql
DROP TAG [IF EXISTS] <tag_name>
```

仅支持有 DROP 权限的用户进行此操作。
> 请谨慎进行此操作。

**注意：** 删除标签时 **Nebula Graph** 将判断相应标签是否有关联的索引，如果有则拒绝删除。

请参考[索引文档](index.md)了解索引详情。

删除标签可使用 `IF EXISTS` 关键字，这个关键字会自动检测对应的标签是否存在，如果存在则删除，如果不存在则直接返回。

一个节点可以有一个或多个标签（类型）。

删除所有标签后，节点将不可访问，同时与节点连接的边也不可使用。

删除单个标签后，节点仍可访问，但是已删除标签的属性不可访问。

此操作仅删除 Schema 信息，硬盘中所有文件及目录均**未被直接删除**，数据会在下次 compaction 时删除。
