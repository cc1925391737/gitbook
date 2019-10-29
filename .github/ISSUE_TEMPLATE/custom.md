---
name: Custom issue template
about: Describe this issue template's purpose here.
title: ''
labels: ''
assignees: ''

---

package main

import (
	"fmt"
	"os"
	"text/template"
)

func main() {
	type UserInfo struct {
		Name string
		Age  int
	}
//初始化结构体
	var user1 UserInfo
	user1.Name = "ZhangSan"
	user1.Age = 22
// New创建模板对象，Parse解析模板字符串，Execute数据驱动模板，对标识位进行替换
	tpl, err := template.New("test").Parse("my name is {{.Name}},my age is {{.Age}}")
	if err != nil {
		fmt.Println(err)
	}
	tpl.Execute(os.Stdout, user1)
}
