---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "statuscake_maintenance_window Resource - terraform-provider-statuscake"
subcategory: ""
description: |-
  
---

# statuscake_maintenance_window (Resource)



## Example Usage

```terraform
resource "statuscake_maintenance_window" "weekends" {
  name     = "Weekends"
  timezone = "UTC"

  start           = "2022-01-29T00:00:00Z"
  end             = "2022-01-30T23:59:59Z"
  repeat_interval = "1w"

  tags = [
    "production"
  ]

  tests = [
    statuscake_uptime_check.statuscake_com.id,
  ]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **end** (String) End of the maintenance window (RFC3339 format)
- **name** (String) Name of the maintenance window
- **start** (String) Start of the maintenance window (RFC3339 format)
- **timezone** (String) Standard timezone associated with this maintenance window

### Optional

- **id** (String) The ID of this resource.
- **repeat_interval** (String) How often the maintenance window should occur
- **tags** (Set of String) List of tags used to include matching uptime checks in this maintenance window
- **tests** (Set of String) List of uptime check IDs explicitly included in this maintenance window

