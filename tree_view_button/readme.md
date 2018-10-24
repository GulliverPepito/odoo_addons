
### 1.安装本模块

### 2.在对应model里面添加函数

```python
def button1(self, select_ids):
    print select_ids # 选中的订单id
    view_id = self.env.ref('sale.view_order_form').id
    res_id = 10 # 订单id
    res = {
        'type': 'ir.actions.act_window',
        'res_model': 'sale.order',
        'view_type': 'form',
        'view_mode': 'tree, form',
        'views': [(view_id, 'form')],
        'target': 'current',
        'res_id': res_id,
        'context': self._context,
    }
    return res
```

### 3.在要添加button的tree view编辑
```xml
<?xml version="1.0"?>
<tree buttons='[["button1", "按钮1"], ["buttonN", "按钮N"]]'>
     <field name="sequence" widget="handle"/>
     ...
</tree>
```