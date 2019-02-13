---
title: 'Vorgehensweise: Installieren und Deinstallieren von Windows-Diensten'
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 43b5ad2f346406897e8bcbcce5660a6c9524f9af
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826259"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="cdbc0-102">Vorgehensweise: Installieren und Deinstallieren von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="cdbc0-102">How to: Install and uninstall Windows services</span></span>
<span data-ttu-id="cdbc0-103">Wenn Sie einen Windows-Dienst mit dem .NET Framework entwickeln, können Sie Ihre Dienstanwendung schnell installieren, indem Sie das Befehlszeilendienstprogramm [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-103">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility.</span></span> <span data-ttu-id="cdbc0-104">Entwickler, die einen Windows-Dienst veröffentlichen möchten, den Benutzer installieren und deinstallieren können, sollten InstallShield verwenden.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-104">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="cdbc0-105">Weitere Informationen finden Sie unter [Erstellen eines Installationspakets (Windows-Client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span><span class="sxs-lookup"><span data-stu-id="cdbc0-105">For more information, see [Create an installer package (Windows client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span></span>
  
> [!WARNING]
>  <span data-ttu-id="cdbc0-106">Wenn Sie einen Dienst auf Ihrem Computer deinstallieren möchten, befolgen Sie die Schritte in diesem Artikel nicht.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="cdbc0-107">In diesem Fall finden Sie heraus, welches Programm oder Software-Paket den Dienst installiert hat. Wählen Sie dann in den Einstellungen **Apps** aus, um das Programm zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-107">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="cdbc0-108">Beachten Sie, dass viele Dienste Bestandteile von Windows sind; wenn Sie sie entfernen, können Sie die Instabilität des Systems verursachen.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="cdbc0-109">Sie müssen zunächst ein Dienstinstallationsprogramm zu Ihrem Windows-Dienst hinzufügen, um die in diesem Artikel aufgeführten Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-109">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="cdbc0-110">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="cdbc0-110">For more information, see [Walkthrough: Creating a Windows service app](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="cdbc0-111">Sie können Windows-Dienstprojekte nicht durch Drücken von F5 direkt aus der Entwicklungsumgebung von Visual Studio ausführen.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-111">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="cdbc0-112">Bevor Sie das Projekt ausführen können, müssen Sie den Dienst im Projekt installieren.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-112">Before you can run the project, you must install the service in the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="cdbc0-113">Sie können den **Server-Explorer** verwenden, um zu überprüfen, ob Sie Ihren Dienst installiert oder deinstalliert haben.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-113">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="cdbc0-114">Weitere Informationen finden Sie unter [How to use Server Explorer in Visual Studio (Verwenden des Server-Explorers in Visual Studio)](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="cdbc0-114">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>
  
### <a name="install-your-service-manually"></a><span data-ttu-id="cdbc0-115">Manuelles Installieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="cdbc0-115">Install your service manually</span></span>  
  
1.  <span data-ttu-id="cdbc0-116">Wählen Sie im Menü **Start** das Verzeichnis **Visual Studio\<*Version*>** aus, und wählen Sie anschließend **Developer-Eingabeaufforderung für VS \<*Version*>** aus.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-116">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>
  
     <span data-ttu-id="cdbc0-117">Daraufhin wird die Developer-Eingabeaufforderung für Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-117">The Developer Command Prompt for Visual Studio appears.</span></span> 
  
2.  <span data-ttu-id="cdbc0-118">Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="cdbc0-119">Führen Sie die *InstallUtil.exe* über die Eingabeaufforderung mit der ausführbaren Datei Ihres Projekts als Parameter aus:</span><span class="sxs-lookup"><span data-stu-id="cdbc0-119">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```console
    installutil <yourproject>.exe  
    ```  

     <span data-ttu-id="cdbc0-120">Wenn Sie die Developer-Eingabeaufforderung für Visual Studio verwenden, sollte *InstallUtil.exe* sich im Systempfad befinden.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-120">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="cdbc0-121">Andernfalls können Sie die Datei in den Pfad einfügen oder den vollqualifizierten Pfad zum Aufrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-121">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="cdbc0-122">Dieses Tool wird mit dem .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<Frameworkversion>* installiert.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-122">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version>*.</span></span>
     
     <span data-ttu-id="cdbc0-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cdbc0-123">For example:</span></span>
     - <span data-ttu-id="cdbc0-124">Für die 32-Bit-Version von .NET Framework 4 oder 4.5 und höher lautet der Standardpfad wie folgt, wenn Ihr Windows-Installationsverzeichnis *C:\Windows* ist: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-124">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="cdbc0-125">Für die 64-Bit-Version von .NET Framework 4 oder 4.5 und höher lautet der Standardpfad wie folgt: *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-125">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>
  
### <a name="uninstall-your-service-manually"></a><span data-ttu-id="cdbc0-126">Manuelles Deinstallieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="cdbc0-126">Uninstall your service manually</span></span>  
  
1. <span data-ttu-id="cdbc0-127">Wählen Sie im Menü **Start** das Verzeichnis **Visual Studio\<*Version*>** aus, und wählen Sie anschließend **Developer-Eingabeaufforderung für VS \<*Version*>** aus.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-127">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>
  
     <span data-ttu-id="cdbc0-128">Daraufhin wird die Developer-Eingabeaufforderung für Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-128">The Developer Command Prompt for Visual Studio appears.</span></span>  
  
2.  <span data-ttu-id="cdbc0-129">Führen Sie die Datei *InstallUtil.exe* über die Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter:</span><span class="sxs-lookup"><span data-stu-id="cdbc0-129">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>  
  
    ```console  
    installutil /u <yourproject>.exe  
    ```  
  
3. <span data-ttu-id="cdbc0-130">Nachdem die ausführbare Datei für ein Dienst gelöscht wurde, kann der Dienst weiterhin in der Registrierung vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-130">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="cdbc0-131">Verwenden Sie in diesem Fall den Befehl [sc delete](/windows-server/administration/windows-commands/sc-delete), um den Eintrag für den Dienst aus der Registrierung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="cdbc0-131">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdbc0-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdbc0-132">See also</span></span>
- [<span data-ttu-id="cdbc0-133">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="cdbc0-133">Introduction to Windows service applications</span></span>](../windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="cdbc0-134">Vorgehensweise: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="cdbc0-134">How to: Create Windows services</span></span>](../windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="cdbc0-135">Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="cdbc0-135">How to: Add installers to your service application</span></span>](../windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="cdbc0-136">Installutil.exe (Installer-Tool)</span><span class="sxs-lookup"><span data-stu-id="cdbc0-136">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
