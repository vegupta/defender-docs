--- 
title: 'Using tags in Microsoft Defender Threat Intelligence (Defender TI)'
description: 'Learn about the tag types and how to add, modify, delete, and search custom tags in Microsoft Defender Threat Intelligence (Defender TI).'
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: how-to
ms.date: 10/18/2024
ms.custom: 
- template-overview
- cx-ti
- cx-mdti
---

# Using tags

>[!IMPORTANT] 
> On June 30, 2024, The Microsoft Defender Threat Intelligence (Defender TI) standalone portal (https://ti.defender.microsoft.com) was retired and is no longer accessible. Customers can continue using Defender TI in the [Microsoft Defender portal](https://aka.ms/mdti-intel-explorer) or with [Microsoft Copilot for Security](security-copilot-and-defender-threat-intelligence.md). [Learn more](https://aka.ms/mdti-standaloneportal)

Microsoft Defender Threat Intelligence (Defender TI) tags provide quick insight about an artifact, whether derived by the system or generated by other users. Tags aid analysts in connecting the dots between current incidents and investigations and their historical context for improved analysis.

Defender TI offers two types of tags: [system tags](#system-tags) and [custom tags](#custom-tags).

## Prerequisites

- A Microsoft Entra ID or personal Microsoft account. [Sign in or create an account](https://signup.microsoft.com/)
- A Defender TI premium license.

    > [!NOTE]
    > Users without a Defender TI premium license can still access our free Defender TI offering.


## System tags

Defender TI generates system tags automatically for you to guide your analysis. These tags require no input or effort on your part.

System tags can include:

- **Routable:** Indicates that the artifact is accessible.
- **ASN:** Pulls an abbreviated portion of an IP address autonomous system number (ASN) description into a tag to provide analysts context into who the IP address belongs to.
- **Dynamic:** Indicates if a dynamic domain name system (DNS) service, such as No-IP or Change IP, owns the domain.
- **Sinkhole:** Indicates that an IP address is a research sinkhole used by security organizations to investigate attack campaigns. Therefore, the domains associated aren't directly connected to each other.

:::image type="content" source="/defender/threat-intelligence/media/system-tags.png" alt-text="System tags." lightbox="/defender/threat-intelligence/media/system-tags.png":::


## Custom tags

Custom tags bring context to indicators of compromise (IOCs) and make analysis even simpler by identifying those domains that are known bad from public reporting or that you categorized as such. You create these tags manually based on your own investigations, and these tags let you share key insights about an artifact with other Defender TI premium license users within your tenant.

:::image type="content" source="/defender/threat-intelligence/media/custom-tags.png" alt-text="Custom tags." lightbox="/defender/threat-intelligence/media/custom-tags.png":::

### Adding, modifying, and removing custom tags

You can add your own custom tags to the tag cluster by entering them into the tag bar. You and your team members, if your organization is a Defender TI customer, can view these tags. Tags entered into the system are private and aren't shared with the larger community.

You can also modify or remove tags. Once you add a tag, you or another paid license user within your organization can modify or remove it, allowing for easy collaboration among the security team.

1. Access the [Defender portal](https://security.microsoft.com/) and complete the Microsoft authentication process. [Learn more about the Defender portal](/defender-xdr/microsoft-365-defender-portal)
2. Navigate to **Threat intelligence** > **Intel explorer**.
3. Search an indicator that you would like to add tags for in the Intel explorer search bar.
   
   :::image type="content" source="/defender/threat-intelligence/media/edit-tags-01.png" alt-text="Tags search." lightbox="/defender/threat-intelligence/media/edit-tags-01.png":::

4. Select **Edit tags** on the upper left-hand corner of the page.
   
   :::image type="content" source="/defender/threat-intelligence/media/edit-tags-02.png" alt-text="Tags search Edit tags." lightbox="/defender/threat-intelligence/media/edit-tags-02.png":::

5. Add any tags you would like to associate with this indicator on the **Custom tags** pop-up window that appears. To add a new indicator, press the **Tab** key to add a new indicator.

   :::image type="content" source="/defender/threat-intelligence/media/edit-tags-03.png" alt-text="Tags search Add tags." lightbox="/defender/threat-intelligence/media/edit-tags-03.png":::

6. Select **Save** once you finish adding all your tags to save your changes.

   :::image type="content" source="/defender/threat-intelligence/media/edit-tags-04.png" alt-text="Tags search Save tags." lightbox="/defender/threat-intelligence/media/edit-tags-04.png":::

7. Repeat step 3 to edit tags. Remove a tag by selecting **X** at the end of it, then add new ones by repeating the steps 4 to 6.

8. Save your changes.

### Viewing and searching custom tags

You can view tags that you or others added within your tenant after searching an IP address, domain, or host artifact.

:::image type="content" source="/defender/threat-intelligence/media/tag-search-match.png" alt-text="Custom tag search." lightbox="/defender/threat-intelligence/media/tag-search-match.png":::


1. Access the [Defender portal](https://security.microsoft.com/) and complete the Microsoft authentication process.
2. Navigate to **Threat intelligence** > **Intel explorer**.
3. Select the **Tag** search type in the Intel explorer search bar drop-down then search the tag value to identify all other indicators that share that same tag value.

   :::image type="content" source="/defender/threat-intelligence/media/search-for-tag.png" alt-text="Search for tags in Intel explorer." lightbox="/defender/threat-intelligence/media/search-for-tag.png":::


## Common tag use case workflow

Let's say you're investigating an incident and you find that it's related to phishing. You can add `phish` as a tag to the IOCs related to that incident. Later, your incident response and threat hunting team can further analyze these IOCs and work with their threat intelligence counterparts to identify which actor group was responsible for the phishing incident. They can then add another `[actor name]` tag to those IOCs or what infrastructure was used that connected them to other related IOCs, such as an `[SHA-1 hash]` custom tag.

### See also

- [What is Microsoft Defender Threat Intelligence (Defender TI)?](what-is-microsoft-defender-threat-intelligence-defender-ti.md)
- [Data sets](data-sets.md)
- [Sorting, filtering, and downloading data](sorting-filtering-and-downloading-data.md)
- [Reputation scoring](reputation-scoring.md)
- [Analyst insights](analyst-insights.md)
- [Using projects](using-projects.md)