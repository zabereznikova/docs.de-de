---
title: Installieren lokalisierter IntelliSense-Dateien
description: Erfahren Sie, wie Sie Ihren Entwicklungscomputer einrichten, um lokalisierte IntelliSense-Dateien für .NET Core-Projekte in Visual Studio zu verwenden.
author: mairaw
ms.author: mairaw
ms.date: 12/18/2019
ms.openlocfilehash: 98d75544ab853e75c175dd2919991b250cfaa3b0
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75436673"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a><span data-ttu-id="f0c63-103">Installieren lokalisierter IntelliSense-Dateien für .NET Core</span><span class="sxs-lookup"><span data-stu-id="f0c63-103">How to install localized IntelliSense files for .NET Core</span></span>

<span data-ttu-id="f0c63-104">[IntelliSense](/visualstudio/ide/using-intellisense) ist eine Codevervollständigungshilfe, die in unterschiedlichen integrierten Entwicklungsumgebungen (IDEs) wie zum Beispiel Visual Studio verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f0c63-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that is available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="f0c63-105">In der Standardeinstellung fügt das SDK beim Entwickeln von .NET Core-Projekten die englische Version der IntelliSense-Dateien ein.</span><span class="sxs-lookup"><span data-stu-id="f0c63-105">By default, when you're developing .NET Core projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="f0c63-106">In diesem Artikel wird Folgendes erläutert:</span><span class="sxs-lookup"><span data-stu-id="f0c63-106">This article explains:</span></span>

- <span data-ttu-id="f0c63-107">Die Installation der lokalisierten Version dieser Dateien</span><span class="sxs-lookup"><span data-stu-id="f0c63-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="f0c63-108">Die Änderung der Visual Studio-Installation, sodass diese eine andere Sprache verwendet</span><span class="sxs-lookup"><span data-stu-id="f0c63-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0c63-109">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="f0c63-109">Prerequisites</span></span>

- <span data-ttu-id="f0c63-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder eine spätere Version</span><span class="sxs-lookup"><span data-stu-id="f0c63-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="f0c63-111">[Visual Studio 2019, Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher</span><span class="sxs-lookup"><span data-stu-id="f0c63-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="f0c63-112">Herunterladen und Installieren der lokalisierten IntelliSense-Dateien</span><span class="sxs-lookup"><span data-stu-id="f0c63-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0c63-113">Für diese Prozedur ist erforderlich, dass Sie über Administratorberechtigungen zum Kopieren der IntelliSense-Dateien in den .NET Core-Installationsordner verfügen.</span><span class="sxs-lookup"><span data-stu-id="f0c63-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET Core installation folder.</span></span>

1. <span data-ttu-id="f0c63-114">Wechseln Sie zur Seite [Herunterladen von IntelliSense-Dateien](https://dotnet.microsoft.com/download/dotnet-core/intellisense).</span><span class="sxs-lookup"><span data-stu-id="f0c63-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/dotnet-core/intellisense) page.</span></span>

1. <span data-ttu-id="f0c63-115">Laden Sie die IntelliSense-Datei für die gewünschte Sprache und Version herunter.</span><span class="sxs-lookup"><span data-stu-id="f0c63-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="f0c63-116">Extrahieren Sie den Inhalt der ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="f0c63-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="f0c63-117">Navigieren Sie zum .NET Core-Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="f0c63-117">Navigate to the .NET Core installation folder.</span></span> <span data-ttu-id="f0c63-118">Dieser befindet sich in der Regel unter *%ProgramFiles%\dotnet\packs*.</span><span class="sxs-lookup"><span data-stu-id="f0c63-118">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>

   - <span data-ttu-id="f0c63-119">Wählen Sie aus, für welches SDK Sie die IntelliSense-Datei installieren möchten, und navigieren Sie zum zugeordneten Pfad.</span><span class="sxs-lookup"><span data-stu-id="f0c63-119">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="f0c63-120">Folgende Optionen stehen zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="f0c63-120">You have the following options:</span></span>

      | <span data-ttu-id="f0c63-121">SDK-Typ</span><span class="sxs-lookup"><span data-stu-id="f0c63-121">SDK type</span></span>        | <span data-ttu-id="f0c63-122">Pfad</span><span class="sxs-lookup"><span data-stu-id="f0c63-122">Path</span></span>                               |
      | --------------- | ---------------------------------- |
      | <span data-ttu-id="f0c63-123">.NET Core</span><span class="sxs-lookup"><span data-stu-id="f0c63-123">.NET Core</span></span>       | <span data-ttu-id="f0c63-124">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="f0c63-124">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="f0c63-125">Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="f0c63-125">Windows Desktop</span></span> | <span data-ttu-id="f0c63-126">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="f0c63-126">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="f0c63-127">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="f0c63-127">.NET Standard</span></span>   | <span data-ttu-id="f0c63-128">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="f0c63-128">*NETStandard.Library.Ref*</span></span>          |
   
   - <span data-ttu-id="f0c63-129">Navigieren Sie zu der Version, für die Sie die lokalisierte IntelliSense-Datei installieren möchten,</span><span class="sxs-lookup"><span data-stu-id="f0c63-129">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="f0c63-130">zum Beispiel *3.1.0*.</span><span class="sxs-lookup"><span data-stu-id="f0c63-130">For example, *3.1.0*.</span></span>
   - <span data-ttu-id="f0c63-131">Öffnen Sie den Ordner *ref*.</span><span class="sxs-lookup"><span data-stu-id="f0c63-131">Open the *ref* folder.</span></span>
   - <span data-ttu-id="f0c63-132">Öffnen Sie den Monikerordner,</span><span class="sxs-lookup"><span data-stu-id="f0c63-132">Open the moniker folder.</span></span> <span data-ttu-id="f0c63-133">zum Beispiel *netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="f0c63-133">For example, *netcoreapp3.1*.</span></span>

   <span data-ttu-id="f0c63-134">Der vollständige Pfad, zu dem Sie also navigieren würden, würde in etwa so aussehen: *C:\Programme\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="f0c63-134">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span></span>

1. <span data-ttu-id="f0c63-135">Erstellen Sie einen Unterordner innerhalb des Monikerordners, den Sie gerade geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="f0c63-135">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="f0c63-136">Der Name des Ordner gibt die Sprache an, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f0c63-136">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="f0c63-137">In der folgenden Tabelle sind die unterschiedlichen Optionen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f0c63-137">The following table specifies the different options:</span></span>

   | <span data-ttu-id="f0c63-138">Sprache</span><span class="sxs-lookup"><span data-stu-id="f0c63-138">Language</span></span>              | <span data-ttu-id="f0c63-139">Ordnername</span><span class="sxs-lookup"><span data-stu-id="f0c63-139">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="f0c63-140">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="f0c63-140">Brazilian Portuguese</span></span>  | <span data-ttu-id="f0c63-141">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="f0c63-141">*pt-br*</span></span>     |
   | <span data-ttu-id="f0c63-142">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="f0c63-142">Chinese (simplified)</span></span>  | <span data-ttu-id="f0c63-143">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="f0c63-143">*zh-hans*</span></span>   |
   | <span data-ttu-id="f0c63-144">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="f0c63-144">Chinese (traditional)</span></span> | <span data-ttu-id="f0c63-145">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="f0c63-145">*zh-hant*</span></span>   |
   | <span data-ttu-id="f0c63-146">Französisch</span><span class="sxs-lookup"><span data-stu-id="f0c63-146">French</span></span>                | <span data-ttu-id="f0c63-147">*fr*</span><span class="sxs-lookup"><span data-stu-id="f0c63-147">*fr*</span></span>        |
   | <span data-ttu-id="f0c63-148">Deutsch</span><span class="sxs-lookup"><span data-stu-id="f0c63-148">German</span></span>                | <span data-ttu-id="f0c63-149">*de*</span><span class="sxs-lookup"><span data-stu-id="f0c63-149">*de*</span></span>        |
   | <span data-ttu-id="f0c63-150">Italienisch</span><span class="sxs-lookup"><span data-stu-id="f0c63-150">Italian</span></span>               | <span data-ttu-id="f0c63-151">*it*</span><span class="sxs-lookup"><span data-stu-id="f0c63-151">*it*</span></span>        |
   | <span data-ttu-id="f0c63-152">Japanisch</span><span class="sxs-lookup"><span data-stu-id="f0c63-152">Japanese</span></span>              | <span data-ttu-id="f0c63-153">*ja*</span><span class="sxs-lookup"><span data-stu-id="f0c63-153">*ja*</span></span>        |
   | <span data-ttu-id="f0c63-154">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="f0c63-154">Korean</span></span>                | <span data-ttu-id="f0c63-155">*ko*</span><span class="sxs-lookup"><span data-stu-id="f0c63-155">*ko*</span></span>        |
   | <span data-ttu-id="f0c63-156">Russisch</span><span class="sxs-lookup"><span data-stu-id="f0c63-156">Russian</span></span>               | <span data-ttu-id="f0c63-157">*ru*</span><span class="sxs-lookup"><span data-stu-id="f0c63-157">*ru*</span></span>        |
   | <span data-ttu-id="f0c63-158">Spanisch</span><span class="sxs-lookup"><span data-stu-id="f0c63-158">Spanish</span></span>               | <span data-ttu-id="f0c63-159">*es*</span><span class="sxs-lookup"><span data-stu-id="f0c63-159">*es*</span></span>        |

1. <span data-ttu-id="f0c63-160">Kopieren Sie die *XML*-Datei, die Sie unter Schritt 3 in diesen neuen Ordner extrahiert haben.</span><span class="sxs-lookup"><span data-stu-id="f0c63-160">Copy the *.xml* files you extracted on step 3 to this new folder.</span></span> <span data-ttu-id="f0c63-161">Die *XML*-Dateien sind durch SDK-Ordner untergliedert, kopieren Sie diese also in das entsprechende SDK, das Sie unter Schritt 4 ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="f0c63-161">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose on step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="f0c63-162">Ändern der Visual Studio-Sprache</span><span class="sxs-lookup"><span data-stu-id="f0c63-162">Modify Visual Studio language</span></span>

<span data-ttu-id="f0c63-163">Damit Visual Studio eine andere Sprache für IntelliSense verwendet, müssen Sie das entsprechende Language Pack installieren.</span><span class="sxs-lookup"><span data-stu-id="f0c63-163">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="f0c63-164">Dies kann [während der Installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) oder zu einem späteren Zeitpunkt geschehen, indem Sie die Visual Studio-Installation ändern.</span><span class="sxs-lookup"><span data-stu-id="f0c63-164">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="f0c63-165">Wenn Visual Studio bereits auf die Sprache Ihrer Wahl konfiguriert ist, ist Ihre IntelliSense-Installation bereit.</span><span class="sxs-lookup"><span data-stu-id="f0c63-165">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="f0c63-166">So installieren Sie ein Language Pack</span><span class="sxs-lookup"><span data-stu-id="f0c63-166">Install the language pack</span></span>

<span data-ttu-id="f0c63-167">Wenn Sie das gewünschte Language Pack noch nicht während der Einrichtung installiert haben, aktualisieren Sie Visual Studio wie folgt, um das Language Pack zu installieren:</span><span class="sxs-lookup"><span data-stu-id="f0c63-167">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0c63-168">Zum Installieren, Aktualisieren und Anpassen von Visual Studio müssen Sie sich mit einem Konto anmelden, das über Administratorberechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="f0c63-168">To install, update, or modify Visual Studio, you must log on with an account that has administrative permissions.</span></span> <span data-ttu-id="f0c63-169">Weitere Informationen finden Sie unter [Benutzerberechtigungen und Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f0c63-169">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="f0c63-170">Suchen Sie den Visual Studio-Installer auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="f0c63-170">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="f0c63-171">Auf einem Computer mit Windows 10 wählen Sie beispielsweise **Start** und blättern dann zum Buchstaben **V**, wo das Installationsprogramm als **Visual Studio-Installer** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f0c63-171">For example, on a computer running Windows 10, select **Start**, and then scroll to the letter **V**, where it's listed as **Visual Studio Installer**.</span></span>

   ![Öffnen des Visual Studio-Installers unter Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="f0c63-173">Sie können den Visual Studio-Installer auch an folgendem Speicherort finden:</span><span class="sxs-lookup"><span data-stu-id="f0c63-173">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="f0c63-174">Möglicherweise müssen Sie den Installer aktualisieren, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f0c63-174">You might have to update the installer before continuing.</span></span> <span data-ttu-id="f0c63-175">Wenn dies der Fall ist, befolgen Sie die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f0c63-175">If so, follow the prompts.</span></span>

1. <span data-ttu-id="f0c63-176">Suchen Sie im Installer nach der Edition von Visual Studio, der Sie das Language Pack hinzufügen möchten, und klicken Sie dann auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="f0c63-176">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Aktualisieren oder Ändern von Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="f0c63-178">Wenn keine **Ändern**-Schaltfläche angezeigt wird, Sie jedoch die Schaltfläche **Aktualisieren** sehen, müssen Sie Visual Studio aktualisieren, bevor Sie Ihre Installation ändern können.</span><span class="sxs-lookup"><span data-stu-id="f0c63-178">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="f0c63-179">Nach Abschluss des Updates sollte die **Ändern**-Schaltfläche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f0c63-179">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="f0c63-180">Wählen Sie auf der Registerkarte **Language Pack** die Sprache oder Sprachen aus oder ab, die Sie installieren bzw. deinstallieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f0c63-180">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Registerkarte der Visual Studio-Language Packs](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="f0c63-182">Klicken Sie auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="f0c63-182">Choose **Modify**.</span></span> <span data-ttu-id="f0c63-183">Das Update wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="f0c63-183">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="f0c63-184">Ändern der Spracheinstellungen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f0c63-184">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="f0c63-185">Sobald Sie die gewünschten Language Packs installiert haben, ändern Sie Ihre Visual Studio-Einstellungen zur Verwendung einer anderen Sprache:</span><span class="sxs-lookup"><span data-stu-id="f0c63-185">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="f0c63-186">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f0c63-186">Open Visual Studio.</span></span>

1. <span data-ttu-id="f0c63-187">Wählen Sie im Startfenster **Ohne Code fortfahren** aus.</span><span class="sxs-lookup"><span data-stu-id="f0c63-187">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="f0c63-188">Wählen Sie im Hauptmenü die Optionen **Extras** > **Optionen** aus.</span><span class="sxs-lookup"><span data-stu-id="f0c63-188">On the main menu, select **Tools** > **Options**.</span></span> <span data-ttu-id="f0c63-189">Das Dialogfeld „Optionen“ wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f0c63-189">The Options dialog opens.</span></span>

1. <span data-ttu-id="f0c63-190">Wählen Sie unter dem Ordner **Umgebung** **Internationale Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="f0c63-190">Under the **Environment** folder, choose **International Settings**.</span></span>

1. <span data-ttu-id="f0c63-191">Wählen Sie eine Sprache aus der Dropdownliste **Sprache**.</span><span class="sxs-lookup"><span data-stu-id="f0c63-191">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="f0c63-192">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0c63-192">Choose **OK**.</span></span> 

1. <span data-ttu-id="f0c63-193">Ein Dialogfeld gibt an, dass Sie Visual Studio neu starten müssen, damit die Änderungen greifen.</span><span class="sxs-lookup"><span data-stu-id="f0c63-193">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="f0c63-194">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0c63-194">Choose **OK**.</span></span>

1. <span data-ttu-id="f0c63-195">Starten Sie Visual Studio neu.</span><span class="sxs-lookup"><span data-stu-id="f0c63-195">Restart Visual Studio.</span></span>

<span data-ttu-id="f0c63-196">Nach dem Neustart sollte IntelliSense erwartungsgemäß funktionieren, wenn Sie ein .NET Core-Projekt öffnen, das sich auf die Version der IntelliSense-Dateien bezieht, die Sie soeben installiert haben.</span><span class="sxs-lookup"><span data-stu-id="f0c63-196">After this, your IntelliSense should work as expected when you open a .NET Core project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0c63-197">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0c63-197">See also</span></span>

- [<span data-ttu-id="f0c63-198">IntelliSense in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f0c63-198">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
