---
title: 'Gewusst wie: Installieren und Deinstallieren von Diensten'
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
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: bf767813f965b2c52a5061f74bbf2fab4572791b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-and-uninstall-services"></a><span data-ttu-id="955fb-102">Gewusst wie: Installieren und Deinstallieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="955fb-102">How to: Install and Uninstall Services</span></span>
<span data-ttu-id="955fb-103">Wenn Sie einen Windows-Dienst mit dem.NET Framework entwickeln, können Sie die Dienstanwendung schnell installieren, indem Sie ein Befehlszeilen-Dienstprogramm InstallUtil.exe aufrufen.</span><span class="sxs-lookup"><span data-stu-id="955fb-103">If you’re developing a Windows Service by using the .NET Framework, you can quickly install your service application by using a command-line utility called InstallUtil.exe.</span></span> <span data-ttu-id="955fb-104">Wenn Sie ein Entwickler sind, der einen Windows-Dienst freigeben möchte, die Benutzer installieren und deinstallieren können, sollten Sie InstallShield verwenden.</span><span class="sxs-lookup"><span data-stu-id="955fb-104">If you’re a developer who wants to release a Windows Service that users can install and uninstall  you should use InstallShield.</span></span> <span data-ttu-id="955fb-105">Finden Sie unter [Windows Installer-Bereitstellung](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).</span><span class="sxs-lookup"><span data-stu-id="955fb-105">See [Windows Installer Deployment](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="955fb-106">Wenn Sie einen Dienst auf Ihrem Computer deinstallieren möchten, befolgen Sie die Schritte in diesem Artikel nicht.</span><span class="sxs-lookup"><span data-stu-id="955fb-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="955fb-107">Stattdessen herauszufinden, welches Programm oder Software-Paket den Dienst installiert, und wählen Sie dann **Programme hinzufügen/entfernen** in der Systemsteuerung, um das Programm zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="955fb-107">Instead, find out which program or software package installed the service, and then choose **Add/Remove Programs** in Control Panel to uninstall that program.</span></span> <span data-ttu-id="955fb-108">Beachten Sie, dass viele Dienste Bestandteile von Windows sind; wenn Sie sie entfernen, können Sie die Instabilität des Systems verursachen.</span><span class="sxs-lookup"><span data-stu-id="955fb-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="955fb-109">Um die Schritte in diesem Artikel zu verwenden, müssen Sie zuerst einen Serviceinstaller auf dem Windows-Dienst hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="955fb-109">In order to use the steps in this article, you first need to add a service installer to your Windows Service.</span></span> <span data-ttu-id="955fb-110">Finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung im Komponenten-Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="955fb-110">See [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="955fb-111">Windows-Dienstprojekte können nicht durch Drücken von F5 direkt aus der Entwicklungsumgebung von Visual Studio ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="955fb-111">Windows Service projects cannot be run directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="955fb-112">Der Grund besteht darin, dass die Dienste des Projekts installiert werden müssen, bevor das Projekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="955fb-112">This is because the service in the project must be installed before you can run the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="955fb-113">Sie können starten **Server-Explorer** und stellen Sie sicher, dass der Dienst installiert oder deinstalliert wurde.</span><span class="sxs-lookup"><span data-stu-id="955fb-113">You can launch **Server Explorer** and verify that your service has been installed or uninstalled.</span></span> <span data-ttu-id="955fb-114">Weitere Informationen finden Sie unter Vorgehensweise: Zugriff und Server-Explorer-Datenbank-Explorer zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="955fb-114">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
### <a name="to-install-your-service-manually"></a><span data-ttu-id="955fb-115">So installieren Sie einen Dienst manuell</span><span class="sxs-lookup"><span data-stu-id="955fb-115">To install your service manually</span></span>  
  
1.  <span data-ttu-id="955fb-116">Auf der Windows **starten** Menü oder **starten** Bildschirm **Visual Studio** , **Visual Studio-Tools**, **Developer Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="955fb-116">On the Windows **Start** menu or **Start** screen, choose **Visual Studio** , **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="955fb-117">Eine Visual Studio-Eingabeaufforderung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="955fb-117">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="955fb-118">Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.</span><span class="sxs-lookup"><span data-stu-id="955fb-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="955fb-119">Führen Sie die Datei "InstallUtil.exe" von der Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter.</span><span class="sxs-lookup"><span data-stu-id="955fb-119">Run InstallUtil.exe from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     <span data-ttu-id="955fb-120">Wenn Sie die Visual Studio-Eingabeaufforderung verwenden, sollten InstallUtil.exe sich auf dem Systempfad befinden.</span><span class="sxs-lookup"><span data-stu-id="955fb-120">If you’re using the Visual Studio command prompt, InstallUtil.exe should be on the system path.</span></span> <span data-ttu-id="955fb-121">Wenn dies nicht der Fall, können Sie den Pfad hinzufügen oder den vollständig qualifizierten Pfad verwenden, um es aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="955fb-121">If not, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="955fb-122">Dieses Tool wird mit dem.NET Framework installiert und lautet `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span><span class="sxs-lookup"><span data-stu-id="955fb-122">This tool is installed with the .NET Framework, and its path is `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span></span> <span data-ttu-id="955fb-123">Z. B. für die 32-Bit-Version von.NET Framework 4 oder 4.5. *, wenn Ihr Windows-Installationsverzeichnis C:\Windows, der Pfad ist `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`lautet.</span><span class="sxs-lookup"><span data-stu-id="955fb-123">For example, for the 32-bit version of the .NET Framework 4 or 4.5.*, if your Windows installation directory is C:\Windows, the path is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span> <span data-ttu-id="955fb-124">Für die 64-Bit-Version von .NET Framework 4 oder 4.5. \*, der Standardpfad lautet `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="955fb-124">For the 64-bit version of the .NET Framework 4 or 4.5.\*, the default path is `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span></span>  
  
### <a name="to-uninstall-your-service-manually"></a><span data-ttu-id="955fb-125">So deinstallieren Sie einen Dienst manuell</span><span class="sxs-lookup"><span data-stu-id="955fb-125">To uninstall your service manually</span></span>  
  
1.  <span data-ttu-id="955fb-126">Auf der Windows **starten** Menü oder **starten** Bildschirm **Visual Studio**, **Visual Studio-Tools**, **Developer Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="955fb-126">On the Windows **Start** menu or **Start** screen, choose **Visual Studio**, **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="955fb-127">Eine Visual Studio-Eingabeaufforderung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="955fb-127">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="955fb-128">Führen Sie die Datei "InstallUtil.exe" von der Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter.</span><span class="sxs-lookup"><span data-stu-id="955fb-128">Run InstallUtil.exe from the command prompt with your project's output as a parameter:</span></span>  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  <span data-ttu-id="955fb-129">In einigen Fällen könnte der Dienst noch in der Registrierung vorhanden sein, nachdem die ausführbaren Datei für einen Dienst gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="955fb-129">Sometimes, after the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="955fb-130">In diesem Fall verwenden Sie den Befehl [sc Delete](http://technet.microsoft.com/library/cc742045.aspx) aus der Registrierung den Eintrag für den Dienst zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="955fb-130">In that case, use the command [sc delete](http://technet.microsoft.com/library/cc742045.aspx) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="955fb-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="955fb-131">See Also</span></span>  
 [<span data-ttu-id="955fb-132">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="955fb-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="955fb-133">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="955fb-133">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="955fb-134">Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="955fb-134">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="955fb-135">Installutil.exe (Installer-Tool)</span><span class="sxs-lookup"><span data-stu-id="955fb-135">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)
