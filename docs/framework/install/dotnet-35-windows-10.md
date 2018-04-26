---
title: Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8
description: Informationen zum Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8.
author: rlander
ms.author: mairaw
ms.date: 03/30/2018
ms.topic: article
ms.prod: .net-framework
ms.workload:
- dotnet
ms.openlocfilehash: 09c4f81da76bb6608c3e579c442cf686ffab1688
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2018
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="273e4-103">Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8</span><span class="sxs-lookup"><span data-stu-id="273e4-103">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="273e4-104">Möglicherweise wird .NET Framework 3.5 zum Ausführen einer App auf Windows 10, Windows 8.1 und Windows 8 benötigt.</span><span class="sxs-lookup"><span data-stu-id="273e4-104">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="273e4-105">Sie können diese Schritte auch für frühere Versionen von Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="273e4-105">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="273e4-106">Installieren von .NET Framework 3.5 bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="273e4-106">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="273e4-107">Wenn Sie versuchen, eine App auszuführen, die .NET Framework 3.5 erfordert, wird möglicherweise das folgende Konfigurationsdialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="273e4-107">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="273e4-108">Wählen Sie **Feature installieren** aus, um .NET Framework 3.5 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="273e4-108">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="273e4-109">Für diese Option ist eine Internetverbindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="273e4-109">This option requires an Internet connection.</span></span>

![Dialogfeld für die Installation .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

### <a name="why-am-i-getting-this-pop-up"></a><span data-ttu-id="273e4-111">Warum wird mir dieses Popup angezeigt?</span><span class="sxs-lookup"><span data-stu-id="273e4-111">Why am I getting this pop-up?</span></span>

<span data-ttu-id="273e4-112">.NET Framework wurde von Microsoft erstellt und bietet eine Umgebung zur Ausführung von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="273e4-112">The .NET Framework is created by Microsoft and provides an environment for running applications.</span></span> <span data-ttu-id="273e4-113">Es stehen verschiedene Versionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="273e4-113">There are different versions available.</span></span> <span data-ttu-id="273e4-114">Viele Unternehmen entwickeln ihre Apps zur Ausführung mit .NET Framework, und diese Apps sind für eine bestimmte Version entworfen.</span><span class="sxs-lookup"><span data-stu-id="273e4-114">Many companies develop their apps to run using the .NET Framework, and these apps target a specific version.</span></span> <span data-ttu-id="273e4-115">Wenn Sie dieses Popup sehen, versuchen Sie, eine Anwendung auszuführen, für die .NET Framework 3.5 erforderlich ist, aber diese Version ist auf Ihrem Computer nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="273e4-115">If you see this pop-up, you're trying to run an application that requires the .NET Framework version 3.5, but that version is not installed on your system.</span></span>

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="273e4-116">Aktivieren von .NET Framework 3.5 in der Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="273e4-116">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="273e4-117">Sie können .NET Framework 3.5 auch über die Systemsteuerung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="273e4-117">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="273e4-118">Für diese Option ist eine Internetverbindung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="273e4-118">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="273e4-119">Drücken Sie die Windows-Taste ![Windows-Logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) auf der Tastatur, geben Sie „Windows-Funktionen“ ein, und drücken Sie EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="273e4-119">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="273e4-120">Das Dialogfeld **Windows-Funktionen ein- oder ausschalten** erscheint.</span><span class="sxs-lookup"><span data-stu-id="273e4-120">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="273e4-121">Aktivieren Sie das Kontrollkästchen **.NET Framework 3.5 (umfasst .NET 2.0 und 3.0)**, klicken Sie auf **OK**, und starten Sie den Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="273e4-121">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Installieren von .NET über die Systemsteuerung](./media/dotnet-control-panel.png)

   <span data-ttu-id="273e4-123">Sie müssen die untergeordneten Elemente für die **HTTP-Aktivierung von Windows Communication Foundation (WCF)** und die **Nicht-HTTP-Aktivierung von Windows Communication Foundation (WCF)** nicht auswählen, es sei denn, Sie sind ein Entwickler oder Serveradministrator und benötigen diese Funktionen.</span><span class="sxs-lookup"><span data-stu-id="273e4-123">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a><span data-ttu-id="273e4-124">Problembehandlung bei der Installation von .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="273e4-124">Troubleshoot the installation of the .NET Framework 3.5</span></span>

<span data-ttu-id="273e4-125">Während der Installation tritt möglicherweise der Fehler 0x800f0906, 0x800f0907, 0x800f081f oder 0x800F0922 auf. In diesem Fall finden Sie unter [.NET Framework 3.5-Installationsfehler: 0x800f0906, 0x800f0907 oder 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) Informationen zur Problemlösung.</span><span class="sxs-lookup"><span data-stu-id="273e4-125">During installation, you may encounter error 0x800f0906, 0x800f0907, 0x800f081f, or 0x800F0922, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) to see how to resolve these issues.</span></span>

<span data-ttu-id="273e4-126">Wenn Sie das Installationsproblem weiterhin nicht lösen können oder keine Internetverbindung zur Verfügung steht, können Sie versuchen, die Installation über Ihr Windows-Installationsmedium durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="273e4-126">If you still can't resolve your installation issue or you don't have an Internet connection, you can try installing it using your Windows installation media.</span></span> <span data-ttu-id="273e4-127">Weitere Informationen finden Sie unter [Bereitstellen von .NET Framework 3.5 mit der Abbildverwaltung für die Bereitstellung (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism).</span><span class="sxs-lookup"><span data-stu-id="273e4-127">For more information, see [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism).</span></span> <span data-ttu-id="273e4-128">Wenn keine Installationsmedien vorhanden sind, lesen Sie [Erstellen eines Installationsmediums für Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span><span class="sxs-lookup"><span data-stu-id="273e4-128">If you don't have the installation media, see [Create installation media for Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span></span>
