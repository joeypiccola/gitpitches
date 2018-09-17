## @color[#FE9F17](Puppet)
### declarative & task based
### configuration management

---

#### What is declarative configuration management?

@ul[](false)
- This is what I want, make it so!
- If x changes to y, change it back to x.
- Traditionally code based.
- All about abstraction.
  + Don't care how, just do it!
@ulend

---

#### Examples / Layers

```ruby
class { 'crypto':
  ssl_3_0_client => false,
  ssl_3_0_server => false,
}

class profile::base (
) {
  include profile::base::chocolatey
  include profile::base::crypto
  include profile::base::firewall
  include profile::base::kms
  include profile::base::localaccounts
  include profile::base::powershell
  include profile::base::nameservers
  include profile::base::timezone
  include profile::base::wsus
  include profile::base::uac
  include profile::base::patch_reporting
  include profile::base::patch_install
  include profile::puppet_agent
}

class role::jumphost {
  include profile::base
  include profile::jumphost::jumphost_install
}
```

@[1-4](Settings)
@[6-21](Profiles.)
@[23-26](Roles.)

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

Think @color[#4169E1](GPO) WMI filtering and item level targeting on @color[#FF0000](steroids). Provides greater granularity and control.

@ol[](false)
- All jump hosts.
- All jump hosts in DEN3.
- All jump hosts in DEN3 for team USB.
- All jump hosts in DEN3 for team USB with
@ol[]

---

### Classifications & Scoping Extended

Scope systems to a project or application.

@ol[](false)
- Ensure IIS is installed for the EWP project
  + In @color[Tomato](v) location named @color[#Orange](w)
  + With @color[#SlateBlue](x) App Pool
  + with @color[#MediumSeaGreen](y) MIME Types
  + with @color[#Violet](z) Bindings
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