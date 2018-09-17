## @color[#FE9F17](Puppet)
### declarative & tasked based
### configuration management

---

## What is declarative configuration management?

@ul[](false)
- Here is what I want, make it so.
- If x changes to y, change it back to x.
- Traditionally code based.
@ulend

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
- Everyone's job is different.
@ulend

## @color[#FE9F17](Puppet) features.

@ul[](false)
- Desired state.
- Version control.
- Auditable.
- Reporting.
- Task driven.
@ulend