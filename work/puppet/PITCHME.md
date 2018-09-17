## @color[#FE9F17](Puppet)
### declarative & tasked based
### configuration management

---

#### What is declarative configuration management?

@ul[](false)
- This is what I want, make it so.
- If x changes to y, change it back to x.
- Traditionally code based.
@ulend


---

#### Example

```ruby
class { 'secure_channel':
  sll_3_0_client => false,
  sll_3_0_server => false,
}
```

---

## Is @color[#FE9F17](Puppet) a replacement for @color[#4169E1](GPO)?

@ol[]
- No
- Yes
- Maybe
- It depends
@olend

---

## Not about @color[#FE9F17](Puppet) vs @color[#4169E1](GPO).

@ul[](false)
- The right tool for the right job.
- Yes, there's overlap.
@ulend


---

### Classifications & Scoping

Think @color[#4169E1](GPO) WMI filtering and item level targeting on @color[#FF0000](steroids) with greater granularity and control.

@ol[](false)
All jump hosts configured the same way.
ALl jump hosts in DEN3 configured the same way.
All jump hosts in DEN3 for team USB configured the same way.
ALl jump hosts in DEN3 for team USB in
@ol[]

---

@snap[north]
@color[#FE9F17](Puppet) features.
@snapend

@snap[west]
@ul[](false)
- Reporting.
- Taskable.
- Package management.
@ulend
@snapend

@snap[east]
@ul[](false)
- Desired state.
- Version control.
- Auditable.
@ulend
@snapend