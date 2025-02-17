---
title: PowerShell module for Azure Lab Services
titleSuffix: ""
description: Learn how to install and launch Az.LabServices PowerShell module
ms.topic: how-to
ms.date: 04/06/2022
ms.custom: devdivchpfy22
---

# Az.LabServices PowerShell module for lab accounts in Azure Lab Services

[!INCLUDE [preview note](./includes/lab-services-new-update-note.md)]

> [!NOTE]
> To learn more about the integrated Az module experience available with the April 2022 Update (preview), see [Quickstart: Create a lab plan using PowerShell and the Azure modules](quick-create-lab-plan-powershell.md).

The [Az.LabServices (preview)](https://github.com/Azure/azure-devtestlab/tree/master/samples/ClassroomLabs/Modules/Library) PowerShell module simplifies the management of Azure Lab Services. This module provides composable functions to create, query, update and delete resources, such as labs, lab accounts, VMs, and images.

## Install and launch

1. Install [Azure PowerShell](/powershell/azure/).
1. Download [Az.LabServices.psm1](https://github.com/Azure/azure-devtestlab/blob/master/samples/ClassroomLabs/Modules/Library/Az.LabServices.psm1) module to your machine.
1. Import the module:

    ```powershell
    Import-Module .\Az.LabServices.psm1
    ```

Some example commands:

```powershell
# To list all the labs in your subscription:
Get-AzLabAccount | Get-AzLab

# To stop all running VMs in all labs
Get-AzLabAccount | Get-AzLab | Get-AzLabVm -Status Running | Stop-AzLabVm
```

## Next steps

Learn more about module at the [Az.LabServices home page on GitHub](https://github.com/Azure/azure-devtestlab/tree/master/samples/ClassroomLabs/Modules/Library).
