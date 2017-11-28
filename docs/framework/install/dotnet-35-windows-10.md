---
title: Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8
description: Informationen zum Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8.
author: rlander
ms.author: mairaw
keywords: .Net Framework, installieren
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="facff-104">Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8</span><span class="sxs-lookup"><span data-stu-id="facff-104">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="facff-105">Möglicherweise wird .NET Framework 3.5 zum Ausführen einer App auf Windows 10, Windows 8.1 und Windows 8 benötigt.</span><span class="sxs-lookup"><span data-stu-id="facff-105">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="facff-106">Sie können diese Schritte auch für frühere Versionen von Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="facff-106">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="facff-107">Installieren von .NET Framework 3.5 bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="facff-107">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="facff-108">Wenn Sie versuchen, eine App auszuführen, die .NET Framework 3.5 erfordert, wird möglicherweise das folgende Konfigurationsdialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="facff-108">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="facff-109">Wählen Sie **Feature installieren** aus, um .NET Framework 3.5 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="facff-109">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="facff-110">Für diese Option ist eine Internetverbindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="facff-110">This option requires an Internet connection.</span></span>

![Dialogfeld für die Installation .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="facff-112">Aktivieren von .NET Framework 3.5 in der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="facff-112">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="facff-113">Sie können .NET Framework 3.5 auch über die Systemsteuerung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="facff-113">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="facff-114">Für diese Option ist eine Internetverbindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="facff-114">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="facff-115">Drücken Sie die Windows-Taste ![Windows-Logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) auf der Tastatur, geben Sie „Windows-Funktionen“ ein, und drücken Sie EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="facff-115">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="facff-116">Das Dialogfeld **Windows-Funktionen ein- oder ausschalten** erscheint.</span><span class="sxs-lookup"><span data-stu-id="facff-116">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="facff-117">Aktivieren Sie das Kontrollkästchen **.NET Framework 3.5 (umfasst .NET 2.0 und 3.0)**, klicken Sie auf **OK**, und starten Sie den Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="facff-117">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Installieren von .NET über die Systemsteuerung](./media/dotnet-control-panel.png)

   <span data-ttu-id="facff-119">Sie müssen die untergeordneten Elemente für die **HTTP-Aktivierung von Windows Communication Foundation (WCF)** und die **Nicht-HTTP-Aktivierung von Windows Communication Foundation (WCF)** nicht auswählen, es sei denn, Sie sind ein Entwickler oder Serveradministrator und benötigen diese Funktionen.</span><span class="sxs-lookup"><span data-stu-id="facff-119">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>
