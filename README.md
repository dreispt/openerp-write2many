Wrapper for OpenERP's cryptic write conventions for x2many fields.

Example usage:

    import m2m
    browse_rec.write({'many_ids: m2m.clear())
    browse_rec.write({'many_ids: m2m.link(99))
    browse_rec.write({'many_ids: m2m.add({'name': 'Monty'}))
    browse_rec.write({'many_ids: m2m.replace([98, 99]))

Since returned values are lists, the can be joined using the plus operator:

    browse_rec.write({'many_ids: m2m.clear() + m2m.link(99))

