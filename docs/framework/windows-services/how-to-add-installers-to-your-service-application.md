---
title: "Gewusst wie: Hinzufügen von Installern zur Dienstanwendung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 0dcb666f317ab285ae0156d2df16947f71665aee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="1ba3f-102">Gewusst wie: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="1ba3f-102">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="1ba3f-103">Visual Studio geliefert Installationskomponenten, die Ihre dienstanwendungen zugeordnete Ressourcen installieren können.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-103">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="1ba3f-104">Installationskomponenten registrieren Sie einen einzelnen Dienst auf dem System, das installiert wird, und lassen Sie den Dienststeuerungs-Manager wissen, dass der Dienst vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-104">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="1ba3f-105">Bei der Arbeit mit einer dienstanwendung können Sie einen Link im Fenster Eigenschaften die entsprechenden Installationsprogramme automatisch zu Ihrem Projekt hinzufügen auswählen.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-105">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ba3f-106">Eigenschaftswerte für Ihren Dienst werden aus der Dienstklasse in die Installerklasse kopiert.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-106">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="1ba3f-107">Wenn Sie die Eigenschaftswerte in die Dienstklasse aktualisieren, werden sie in das Installationsprogramm nicht automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-107">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="1ba3f-108">Wenn Sie ein Installationsprogramm Ihrem Projekt eine neue Klasse hinzufügen (, die standardmäßig heißt `ProjectInstaller`) wird erstellt, in das Projekt, und klicken Sie auf Instanzen der entsprechenden Installation Komponenten darin erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-108">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="1ba3f-109">Diese Klasse fungiert als ein zentraler Verwaltungspunkt für alle Installationskomponenten für das Projekt benötigt.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-109">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="1ba3f-110">Wenn Sie Ihre Anwendung einen zweiten Dienst hinzu, und klicken Sie auf den Link Installer hinzufügen, wird eine zweite Installerklasse z. B. nicht erstellt; Stattdessen wird die vorhandene Klasse der erforderlichen zusätzlichen Installationskomponente für den zweiten Dienst hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-110">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="1ba3f-111">Sie brauchen keine besondere Codierung innerhalb der Installationsprogramme, stellen die Dienste ordnungsgemäß zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-111">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="1ba3f-112">Allerdings müssen Sie gelegentlich den Inhalt der Installationsprogramme zu ändern, wenn Sie spezielle Funktionen während des Installationsvorgangs hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-112">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ba3f-113">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1ba3f-114">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1ba3f-115">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="1ba3f-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="1ba3f-116">Die dienstanwendung Installationsprogramme hinzu</span><span class="sxs-lookup"><span data-stu-id="1ba3f-116">To add installers to your service application</span></span>  
  
1.  <span data-ttu-id="1ba3f-117">In **Projektmappen-Explorer**, Zugriff **Entwurf** Ansicht für den Dienst für die Sie eine Komponente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-117">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2.  <span data-ttu-id="1ba3f-118">Klicken Sie auf dem Hintergrund des Designers, um den Dienst ausgewählt haben, selbst statt einen seiner Inhalte.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-118">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3.  <span data-ttu-id="1ba3f-119">Mit dem Designer den Fokus hat, mit der rechten Maustaste, und klicken Sie dann auf **Installer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-119">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="1ba3f-120">Eine neue Klasse `ProjectInstaller`, und zwei Installationskomponenten <xref:System.ServiceProcess.ServiceProcessInstaller> und <xref:System.ServiceProcess.ServiceInstaller>, hinzukommen zum Projekt und Eigenschaftswerte für der Dienst für die Komponenten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-120">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4.  <span data-ttu-id="1ba3f-121">Klicken Sie auf die <xref:System.ServiceProcess.ServiceInstaller> Komponente und überprüfen Sie, ob der Wert des der <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> Eigenschaftensatz wird auf den gleichen Wert wie die <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> Eigenschaft für den Dienst selbst.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-121">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5.  <span data-ttu-id="1ba3f-122">Um zu bestimmen, wie der Dienst gestartet wird, klicken Sie auf die <xref:System.ServiceProcess.ServiceInstaller> Komponente, und legen die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> Eigenschaft auf den entsprechenden Wert.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-122">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="1ba3f-123">Wert</span><span class="sxs-lookup"><span data-stu-id="1ba3f-123">Value</span></span>|<span data-ttu-id="1ba3f-124">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="1ba3f-124">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="1ba3f-125">Der Dienst muss nach der Installation manuell gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-125">The service must be manually started after installation.</span></span> <span data-ttu-id="1ba3f-126">Weitere Informationen finden Sie unter [Vorgehensweise: Starten von Diensten](../../../docs/framework/windows-services/how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ba3f-126">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="1ba3f-127">Der Dienst kann selbst gestartet, sobald der Computer neu gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-127">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="1ba3f-128">Der Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-128">The service cannot be started.</span></span>|  
  
6.  <span data-ttu-id="1ba3f-129">Um den Sicherheitskontext fest, in dem der Dienst ausgeführt wird, klicken Sie auf die <xref:System.ServiceProcess.ServiceProcessInstaller> Komponente, und legen Sie die entsprechenden Eigenschaftswerte.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-129">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="1ba3f-130">Weitere Informationen finden Sie unter [Vorgehensweise: Angeben des Sicherheitskontexts für Dienste](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ba3f-130">For more information, see [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span></span>  
  
7.  <span data-ttu-id="1ba3f-131">Überschreiben Sie alle Methoden, die für die benutzerdefinierte Verarbeitung durchgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-131">Override any methods for which you need to perform custom processing.</span></span>  
  
8.  <span data-ttu-id="1ba3f-132">Führen Sie die Schritte 1 bis 7 für jeden Dienst in Ihrem Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-132">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ba3f-133">Für jeden Dienst in Ihrem Projekt, müssen Sie ein zusätzliches hinzufügen <xref:System.ServiceProcess.ServiceInstaller> -Komponente auf des Projekts `ProjectInstaller` Klasse.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-133">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="1ba3f-134">Die <xref:System.ServiceProcess.ServiceProcessInstaller> Komponente, die in Schritt 3 hinzugefügten funktioniert mit allen einzelnen Dienstinstallationsprogramm im Projekt.</span><span class="sxs-lookup"><span data-stu-id="1ba3f-134">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba3f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ba3f-135">See Also</span></span>  
 [<span data-ttu-id="1ba3f-136">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="1ba3f-136">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="1ba3f-137">Vorgehensweise: Installieren und Deinstallieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="1ba3f-137">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="1ba3f-138">Vorgehensweise: Starten von Diensten</span><span class="sxs-lookup"><span data-stu-id="1ba3f-138">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="1ba3f-139">Vorgehensweise: Angeben des Sicherheitskontexts für Dienste</span><span class="sxs-lookup"><span data-stu-id="1ba3f-139">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
