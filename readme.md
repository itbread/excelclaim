## excelclaim
包装了[excelize](https://github.com/360EntSecGroup-Skylar/excelize)简化表格的生成。

## 使用
- 生成交通补贴
```
sheet := excel.NewSheet(xlsx, "加班交通费", 7, 28)
sheet.SetAllColsWidth(7, 14, 10, 11, 12, 8, 8)
excelStyle := excel.NewExcelStyle(11, 0, false);
sheet.ApplyRows(excelStyle, 6);

excelStyle2 := excel.NewExcelStyle(11, 0, true);

sheet.WriteRow("市内交通费报销明细").SetRowHeight(34)
sheet.WriteRow("月份", "6", "姓名", "wwww", "部门", "", "研发部")
sheet.WriteRow("序号", "日期", "出发地", "到达地", "公务事由", "金额", "备注")
sheet.ApplyRowsRange(excelStyle2, 1, 3)

sheet.WriteRow("1", "2018.06.07", "公司", "宝安", "加班", "80.00", "").ApplyItem(1, excelStyle2)
sheet.WriteRow("2", "2018.06.07", "公司", "宝安", "加班", "80.00", "").ApplyItem(1, excelStyle2)
sheet.WriteRow("", "", "", "", "金额合计", "160.00")
```
![excelclaim](./img/交通费.jpg)


- 生成加班补贴
```
sheet := excel.NewSheet(xlsx, "加班餐费", 6, 22)
sheet.SetAllColsWidth(7, 14, 8, 11, 8, 12)

sheet.WriteRow("加班餐费明细")
sheet.WriteRow("月份", "2018年06月", "姓名", "wwww", "部门", "研发部")
sheet.WriteRow("序号", "日期", "事由", "中餐/晚餐", "金额", "备注")
sheet.WriteRow("1", "2018-06-01", "加班", "晚餐", "20", "21:05")
sheet.WriteRow("2", "2018-06-02", "加班", "晚餐", "20", "21:05")
sheet.WriteRow("3", "2018-06-01", "加班", "晚餐", "20", "21:05")
sheet.WriteRow("4", "2018-06-02", "加班", "晚餐", "20", "21:05")
sheet.WriteRow("", "", "", "", "金额合计", "80.00", "")
sheet.Apply(excel.NewExcelStyle(10, -1, false));
```
![excelclaim](./img/餐费.jpg)
