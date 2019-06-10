---
title: Dyn Domain Configuration
provider: Dyn
dnsprovider: true
description: Learn how to point your Dyn domain to a Pantheon site.
tags: [providers]
permalink: docs/:basename/
editpath: dns-providers/dyn.md/
---
## Before You Begin
Be sure that you have a:


- Registered domain name using Dyn to host DNS
- [Paid Pantheon plan](/docs/guides/launch/plans/)
- [Domain connected](/docs/guides/launch/domains/) to the target Pantheon environment (typically Live):
 ![Domains / HTTPS**.](/source/docs/assets/images/dashboard/domain-added.png)

## Locate Pantheon's DNS Values
Identify DNS values to point your domain to Pantheon:

1. Navigate to the Site Dashboard and select the target environment (typically <span class="glyphicons glyphicons-cardio"></span> Live) then click **<span class="glyphicons glyphicons-global"></span> Domains / HTTPS**.
2. Click the **Details** button next to your domain.

Keep this page open and login to your [Dyn DNS account <span class="glyphicons glyphicons-new-window-alt"></span>](https://portal.dynect.net/login/" target="blank) in a new tab before you continue.

## Configure DNS Records on Dyn
### A Record
1. Click **Overview** then **Manage** from the far right menu.
2. Navigate to **Simple Editor** > **Records**.
3. Select **A** from the record type dropdown menu.
4. Enter the A record value provided by Pantheon in the **IP Address** field.
5. Select desired Time to Live (TTL).

    <Accordion title="Learn More" id="ttl" icon="info-sign">

    #### Time to Live (TTL)

    The TTL dictates the lifespan of a DNS record; a shorter time means less time to wait until the changes go into effect. TTLs are always set in seconds with a few common ones being 86400 (24 hours),  43200 (12 hours), and 3600 (1 hour).

    When you make a change to the TTL of an existing record, you need to wait for the old TTL time to pass - that is, if it had been set to 86400, you would need to wait a full 24 hours for the new setting to begin propagating everywhere.

    </Alert>

6. Click **Add**.

### AAAA Records
1. Select **AAAA** from the record type dropdown menu.
2. Enter the first AAAA record value provided by Pantheon in the **IP Address** field.
3. Select desired Time to Live (TTL).
4. Click **Add**.
5. Repeat steps 1-4 for the second AAAA record value provided by Pantheon. There are two AAAA records for improved uptime and reliability.

### CNAME Record
A CNAME record is required to configure a subdomain (e.g., `www.example.com`).

1. Select **CNAME** from the record type dropdown menu.
2. Enter the CNAME record value provided by Pantheon (e.g. `live-example.pantheonsite.io`) in the **Cname** field.
3. Select desired Time to Live (TTL).
4. Click **Add**.

## Dyn Docs

* [Creating a Zone <span class="glyphicons glyphicons-new-window-alt"></span>](https://help.dyn.com/creating-a-zone/" target="blank)
* [Zone Records <span class="glyphicons glyphicons-new-window-alt"></span>](https://help.dyn.com/zone-records/" target="blank)

## Next Steps

* [Launch Essentials: Domains & HTTPS](/docs/guides/launch/domains/)
* [Launch Essentials: Redirect to a Primary Domain](/docs/guides/launch/redirects/)