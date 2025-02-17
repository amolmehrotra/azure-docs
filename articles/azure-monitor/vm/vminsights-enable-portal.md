---
title: Enable Azure Monitor for single virtual machine or virtual machine scale set in the Azure portal
description: Learn how to enable VM insights on a single Azure virtual machine or virtual machine scale set using the Azure portal.
ms.topic: conceptual
author: bwren
ms.author: bwren
ms.date: 06/08/2022

---

# Enable Azure Monitor for single virtual machine or virtual machine scale set in the Azure portal
This article describes how to enable VM insights for a virtual machine or virtual machine scale set using the Azure portal. This procedure can be used for the following:

- Azure virtual machine
- Azure virtual machine scale set
- Hybrid virtual machine connected with Azure Arc

## Prerequisites

- [Create and configure a Log Analytics workspace](./vminsights-configure-workspace.md). Alternatively, you can create a new workspace during this process.
- See [Supported operating systems](./vminsights-enable-overview.md#supported-operating-systems) to ensure that the operating system of the virtual machine or virtual machine scale set you're enabling is supported. 

## Enable VM insights

From the Azure portal, select **Virtual machines**, **Virtual machine scale sets**, or **Servers - Azure Arc** and select a resource from the list. In the **Monitoring** section of the menu, select **Insights** and then **Enable**. The following example shows an Azure virtual machine, but the menu is similar for Azure virtual machine scale set or Azure Arc.

![Enable VM insights for a VM](media/vminsights-enable-portal/enable-vminsights-vm-portal.png)

If the virtual machine isn't already connected to a Log Analytics workspace, then you'll be prompted to select one. If you haven't previously [created a workspace](../logs/quick-create-workspace.md), then you can select a default for the location where the virtual machine or virtual machine scale set is deployed in the subscription. This workspace will be created and configured if it doesn't already exist. If you select an existing workspace, it will be configured for VM insights if it wasn't already.

> [!NOTE]
> If you select a workspace that wasn't previously configured for VM insights, the *VMInsights* management pack will be added to this workspace. This will be applied to any agent already connected to the workspace, whether or not it's enabled for VM insights. Performance data will be collected from these virtual machines and stored in the *InsightsMetrics* table.

![Select workspace](media/vminsights-enable-portal/select-workspace.png)

You will receive status messages as the configuration is performed.

>[!NOTE]
>If you use a manual upgrade model for your virtual machine scale set, upgrade the instances to complete the setup. You can start the upgrades from the **Instances** page, in the **Settings** section.

![Enable VM insights monitoring deployment processing](media/vminsights-enable-portal/onboard-vminsights-vm-portal-status.png)



## Next steps

* See [Use VM insights Map](vminsights-maps.md) to view discovered application dependencies. 
* See [View Azure VM performance](vminsights-performance.md) to identify bottlenecks, overall utilization, and your VM's performance.
