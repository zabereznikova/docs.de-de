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
ms.openlocfilehash: 8937ef8b4007253b06444e59b292395084e4df2f
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607918"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="0f308-102">Vorgehensweise: Installieren und Deinstallieren von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="0f308-102">How to: Install and uninstall Windows services</span></span>

<span data-ttu-id="0f308-103">Wenn Sie einen Windows-Dienst mit dem .NET Framework entwickeln, können Sie Ihre Dienstanwendung schnell installieren, indem Sie das Befehlszeilendienstprogramm [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) oder [PowerShell](/powershell/scripting/overview) verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f308-103">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility or [PowerShell](/powershell/scripting/overview).</span></span> <span data-ttu-id="0f308-104">Entwickler, die einen Windows-Dienst veröffentlichen möchten, den Benutzer installieren und deinstallieren können, sollten InstallShield verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f308-104">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="0f308-105">Weitere Informationen finden Sie unter [Erstellen eines Installationspakets (Windows-Desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span><span class="sxs-lookup"><span data-stu-id="0f308-105">For more information, see [Create an installer package (Windows desktop)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

> [!WARNING]
> <span data-ttu-id="0f308-106">Wenn Sie einen Dienst auf Ihrem Computer deinstallieren möchten, befolgen Sie die Schritte in diesem Artikel nicht.</span><span class="sxs-lookup"><span data-stu-id="0f308-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="0f308-107">In diesem Fall finden Sie heraus, welches Programm oder Software-Paket den Dienst installiert hat. Wählen Sie dann in den Einstellungen **Apps** aus, um das Programm zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="0f308-107">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="0f308-108">Beachten Sie, dass viele Dienste Bestandteile von Windows sind; wenn Sie sie entfernen, können Sie die Instabilität des Systems verursachen.</span><span class="sxs-lookup"><span data-stu-id="0f308-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>

<span data-ttu-id="0f308-109">Sie müssen zunächst ein Dienstinstallationsprogramm zu Ihrem Windows-Dienst hinzufügen, um die in diesem Artikel aufgeführten Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="0f308-109">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="0f308-110">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows-Dienstanwendung](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="0f308-110">For more information, see [Walkthrough: Creating a Windows service app](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>

<span data-ttu-id="0f308-111">Sie können Windows-Dienstprojekte nicht durch Drücken von F5 direkt aus der Entwicklungsumgebung von Visual Studio ausführen.</span><span class="sxs-lookup"><span data-stu-id="0f308-111">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="0f308-112">Bevor Sie das Projekt ausführen können, müssen Sie den Dienst im Projekt installieren.</span><span class="sxs-lookup"><span data-stu-id="0f308-112">Before you can run the project, you must install the service in the project.</span></span>

> [!TIP]
> <span data-ttu-id="0f308-113">Sie können den **Server-Explorer** verwenden, um zu überprüfen, ob Sie Ihren Dienst installiert oder deinstalliert haben.</span><span class="sxs-lookup"><span data-stu-id="0f308-113">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="0f308-114">Weitere Informationen finden Sie unter [How to use Server Explorer in Visual Studio (Verwenden des Server-Explorers in Visual Studio)](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0f308-114">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>

### <a name="install-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="0f308-115">Manuelles Installieren Ihres Diensts mithilfe des Hilfsprogramms „InstallUtil.exe“</span><span class="sxs-lookup"><span data-stu-id="0f308-115">Install your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="0f308-116">Wählen Sie im Menü **Start** das Verzeichnis **Visual Studio\<*Version*>** aus, und wählen Sie anschließend **Developer-Eingabeaufforderung für VS \<*Version*>** aus.</span><span class="sxs-lookup"><span data-stu-id="0f308-116">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="0f308-117">Daraufhin wird die Developer-Eingabeaufforderung für Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f308-117">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="0f308-118">Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.</span><span class="sxs-lookup"><span data-stu-id="0f308-118">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="0f308-119">Führen Sie die *InstallUtil.exe* über die Eingabeaufforderung mit der ausführbaren Datei Ihres Projekts als Parameter aus:</span><span class="sxs-lookup"><span data-stu-id="0f308-119">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>

    ```console
    installutil <yourproject>.exe
    ```

     <span data-ttu-id="0f308-120">Wenn Sie die Developer-Eingabeaufforderung für Visual Studio verwenden, sollte *InstallUtil.exe* sich im Systempfad befinden.</span><span class="sxs-lookup"><span data-stu-id="0f308-120">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="0f308-121">Andernfalls können Sie die Datei in den Pfad einfügen oder den vollqualifizierten Pfad zum Aufrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f308-121">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="0f308-122">Dieses Tool wird mit dem .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<Frameworkversion>\>* installiert.</span><span class="sxs-lookup"><span data-stu-id="0f308-122">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version\>*.</span></span>

     <span data-ttu-id="0f308-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0f308-123">For example:</span></span>
     - <span data-ttu-id="0f308-124">Für die 32-Bit-Version von .NET Framework 4 oder 4.5 und höher lautet der Standardpfad wie folgt, wenn Ihr Windows-Installationsverzeichnis *C:\Windows* ist: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="0f308-124">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="0f308-125">Für die 64-Bit-Version von .NET Framework 4 oder 4.5 und höher lautet der Standardpfad wie folgt: *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span><span class="sxs-lookup"><span data-stu-id="0f308-125">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a><span data-ttu-id="0f308-126">Manuelles Deinstallieren Ihres Diensts mithilfe des Hilfsprogramms „InstallUtil.exe“</span><span class="sxs-lookup"><span data-stu-id="0f308-126">Uninstall your service manually using InstallUtil.exe utility</span></span>

1. <span data-ttu-id="0f308-127">Wählen Sie im Menü **Start** das Verzeichnis **Visual Studio\<*Version*>** aus, und wählen Sie anschließend **Developer-Eingabeaufforderung für VS \<*Version*>** aus.</span><span class="sxs-lookup"><span data-stu-id="0f308-127">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>

     <span data-ttu-id="0f308-128">Daraufhin wird die Developer-Eingabeaufforderung für Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f308-128">The Developer Command Prompt for Visual Studio appears.</span></span>

2. <span data-ttu-id="0f308-129">Führen Sie die Datei *InstallUtil.exe* über die Eingabeaufforderung aus. Übergeben Sie die Ausgabe des Projekts als Parameter:</span><span class="sxs-lookup"><span data-stu-id="0f308-129">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>

    ```console
    installutil /u <yourproject>.exe
    ```

3. <span data-ttu-id="0f308-130">Nachdem die ausführbare Datei für ein Dienst gelöscht wurde, kann der Dienst weiterhin in der Registrierung vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="0f308-130">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="0f308-131">Verwenden Sie in diesem Fall den Befehl [sc delete](/windows-server/administration/windows-commands/sc-delete), um den Eintrag für den Dienst aus der Registrierung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0f308-131">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

### <a name="install-your-service-manually-using-powershell"></a><span data-ttu-id="0f308-132">Manuelles Installieren Ihres Diensts mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f308-132">Install your service manually using PowerShell</span></span>

1. <span data-ttu-id="0f308-133">Wählen Sie im Menü **Start** das Verzeichnis **Windows PowerShell** aus, und klicken Sie dann auf **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0f308-133">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="0f308-134">Greifen Sie auf das Verzeichnis zu, in dem sich die kompilierte ausführbare Datei des Projekts befindet.</span><span class="sxs-lookup"><span data-stu-id="0f308-134">Access the directory where your project's compiled executable file is located.</span></span>

3. <span data-ttu-id="0f308-135">Führen Sie das Cmdlet [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) mit der Ausgabe Ihres Projekts und einem Dienstnamen als Parameter aus:</span><span class="sxs-lookup"><span data-stu-id="0f308-135">Run the [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) cmdlet with the with your project's output and a service name as parameters:</span></span>

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a><span data-ttu-id="0f308-136">Manuelles Deinstallieren Ihres Diensts mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f308-136">Uninstall your service manually using PowerShell</span></span>

1. <span data-ttu-id="0f308-137">Wählen Sie im Menü **Start** das Verzeichnis **Windows PowerShell** aus, und klicken Sie dann auf **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0f308-137">From the **Start** menu, select the **Windows PowerShell** directory, then select **Windows PowerShell**.</span></span>

2. <span data-ttu-id="0f308-138">Führen Sie das Cmdlet [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) mit dem Namen Ihres Diensts als Parameter aus:</span><span class="sxs-lookup"><span data-stu-id="0f308-138">Run the [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) cmdlet with the name of your service as parameter:</span></span>

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. <span data-ttu-id="0f308-139">Nachdem die ausführbare Datei für ein Dienst gelöscht wurde, kann der Dienst weiterhin in der Registrierung vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="0f308-139">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="0f308-140">Verwenden Sie in diesem Fall den Befehl [sc delete](/windows-server/administration/windows-commands/sc-delete), um den Eintrag für den Dienst aus der Registrierung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0f308-140">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a><span data-ttu-id="0f308-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f308-141">See also</span></span>

- [<span data-ttu-id="0f308-142">Einführung in Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="0f308-142">Introduction to Windows service applications</span></span>](../windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="0f308-143">How to: Erstellen von Windows-Diensten</span><span class="sxs-lookup"><span data-stu-id="0f308-143">How to: Create Windows services</span></span>](../windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="0f308-144">How to: Hinzufügen von Installern zur Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="0f308-144">How to: Add installers to your service application</span></span>](../windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="0f308-145">Installutil.exe (Installer-Tool)</span><span class="sxs-lookup"><span data-stu-id="0f308-145">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
