Wrapper for OpenERP's cryptic for x2many fields writing conventions.

Example usage:

    import m2m
    browse_rec.write({'many_ids': m2m.clear())
    browse_rec.write({'many_ids': m2m.link(99))
    browse_rec.write({'many_ids': m2m.add({'name': 'Monty'}))
    browse_rec.write({'many_ids': m2m.replace([98, 99]))

Since returned values are lists, the can be joined using the plus operator:

    browse_rec.write({'many_ids': m2m.clear() + m2m.link(99))

[Operations supported](https://doc.openerp.com/trunk/server/api_models/#openerp.osv.orm.BaseModel.write) on one2many and many2many:

  * `create(values)` or `add(values)`: create and link new record
  * `write(id, values)`: update a currently linked record
  * `remove(id)`: unlink and delete the referenced record

Operations supported on many2many fields only:

  * `unlink(id)`: unlink the record without deleting it
  * `link(id)`: add a link to an existing record
  * `clear()`: unlink all references
  * `replace(ids)`: unlink all references and replace them by an id list

