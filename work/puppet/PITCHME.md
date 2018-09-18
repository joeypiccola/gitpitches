## @color[#FE9F17](Puppet)
### declarative & task based
### configuration management

---

#### What is declarative configuration management?

@ul[](false)
- This is what I want, make it so!
- Don't care how, just do it.
- All about abstraction.
- Traditionally code based.
- [optional] Easily enforceable. If @color[Tomato](x) changes to @color[DodgerBlue](y), change it back to @color[Tomato](x).
@ulend

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
- Using both to manage the same config is like putting two raccoons in a bag.
- Yes, there's overlap.
@ulend

---
@snap[north]
Abstraction
@snapend

@snap[west]
![full](assets/image/abstract.jpg)
@snapend

@snap[east]
![abst](assets/image/sc.jpg)
@snapend

---

#### Examples / Layers

```ruby
class { 'schannel':
  ssl_3_0_client => false,
  ssl_3_0_server => false,
}

class profile::base (
) {
  include profile::base::dns
  include profile::base::firewall
  include profile::base::kms
  include profile::base::localaccounts
  include profile::base::patch_install
  include profile::base::patch_reporting
  include profile::base::powershell
  include profile::base::schannel
  include profile::base::timezone
  include profile::base::uac
  include profile::base::wsus
}

class role::jumphost {
  include profile::base
  include profile::jumphost::jumphost_install
}
```

@[1-4](Settings)
@[6-19](Profiles.)
@[15](schannel.)
@[21-24](Roles.)

---

### Classifications & Scoping

Think @color[#4169E1](GPO) WMI filtering and item level targeting on @color[Tomato](steroids). Provides greater granularity and control.

@ol[](false)
- All @color[MediumSeaGreen](jump hosts).
- All @color[MediumSeaGreen](jump hosts) in @color[SlateBlue](DEN4).
- All @color[MediumSeaGreen](jump hosts) in @color[SlateBlue](DEN4) for @color[Orange](Team USB).
@ol[]

---

### Classifications & Scoping Extended

Scope systems to a project or application.

@ol[](false)
- Ensure IIS is installed for @color[DodgerBlue](u) project
- In @color[Tomato](v) location named @color[Orange](w)
- With @color[SlateBlue](x) App Pool
- With @color[MediumSeaGreen](y) MIME Types
- With @color[Violet](z) Bindings
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

---

### Tasks & Demo

@ol[](false)
- Upgrade PowerShell: 5.1.14409.20180811
- Disable SMBv1
- Find HotFix: KB3110329
@ol[]