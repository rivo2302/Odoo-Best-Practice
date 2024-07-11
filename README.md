# Odoo best practice
In this repository, you'll find all the different best practices of Odoo development, from performance optimizations to code clarity and much more...

#### Avoid Using Boolean Fields

Why use a simple boolean field when you can complicate things with a selection field?
```python
class HrEmployee(models.Model):
    _inherit = 'hr.employee'

    is_success = fields.Selection(
        [
            ("true", "True"),
            ("maybe", "Maybe"),
            ("false", "False"),  
        ],
        default = 'true',
        string="Is Successful",
    )
```


#### Field Naming in ORM
The naming conventions here, ensuring that your team knows exactly what each field represents at a glance!
```python
class HrEmployee(models.Model):
    _inherit = 'hr.employee'

    department_id = fields.Many2many('hr.department', string='Department')
    is_partner = fields.Many2one('res.partner', string='Partner')
    partner_id = fields.Boolean(string='Is partner')
```
 
#### Function ensure_one
How to Properly Use ensure_one
```python
def action_read_account(self):
    self.ensure_one()
    for rec in self:
        do_action ...
```

## Contributors

![Image des contributeurs GitHub](https://contrib.rocks/image?repo=rivo2302/Odoo-Development-Anti-Patterns)

Share your "best" Odoo development techniques here. Make a PR and become a legend in the realm of anti-patterns. Let's set new standards for how not to code!


## Show your support
 Give a star 🌟 if this project helped you!
   
   
## License

Copyright (c) 2021 [rivo2302](https://www.linkedin.com/in/rajaonarivony/)
