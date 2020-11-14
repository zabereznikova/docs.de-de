---
title: Installieren der lokalisierten IntelliSense-Dateien
description: Erfahren Sie, wie Sie Ihren Entwicklungscomputer für die Verwendung lokalisierter IntelliSense-Dateien für .NET 5-Projekte (einschließlich .NET-Core) und höher in Visual Studio einrichten.
ms.date: 11/06/2020
ms.openlocfilehash: 45eeae12ca79179cacb3d48fca28118de70e0a4f
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506765"
---
# <a name="how-to-install-localized-intellisense-files-for-net"></a><span data-ttu-id="b4769-103">Installieren lokalisierter IntelliSense-Dateien für .NET</span><span class="sxs-lookup"><span data-stu-id="b4769-103">How to install localized IntelliSense files for .NET</span></span>

<span data-ttu-id="b4769-104">[IntelliSense](/visualstudio/ide/using-intellisense) ist ein Hilfsmittel zur Codevervollständigung, das in verschiedenen integrierten Entwicklungsumgebungen (IDEs), z. B. Visual Studio, verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b4769-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that's available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="b4769-105">Wenn Sie .NET-Projekte entwickeln, enthält das SDK standardmäßig nur die englische Version der IntelliSense-Dateien.</span><span class="sxs-lookup"><span data-stu-id="b4769-105">By default, when you're developing .NET projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="b4769-106">In diesem Artikel erfahren Sie:</span><span class="sxs-lookup"><span data-stu-id="b4769-106">This article explains:</span></span>

- <span data-ttu-id="b4769-107">wie Sie die lokalisierte Version dieser Dateien installieren.</span><span class="sxs-lookup"><span data-stu-id="b4769-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="b4769-108">wie Sie die Visual Studio-Installation ändern, um eine andere Sprache zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4769-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b4769-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b4769-109">Prerequisites</span></span>

- <span data-ttu-id="b4769-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder eine höhere Version wie [.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="b4769-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version, such as [.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0).</span></span>
- <span data-ttu-id="b4769-111">[Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder eine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="b4769-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="b4769-112">Herunterladen und Installieren der lokalisierten IntelliSense-Dateien</span><span class="sxs-lookup"><span data-stu-id="b4769-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4769-113">Für diese Prozedur ist es erforderlich, dass Sie über Administratorberechtigungen zum Kopieren der IntelliSense-Dateien in den .NET-Installationsordner verfügen.</span><span class="sxs-lookup"><span data-stu-id="b4769-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET installation folder.</span></span>

1. <span data-ttu-id="b4769-114">Navigieren Sie zur [Seite zum Herunterladen der IntelliSense-Dateien](https://dotnet.microsoft.com/download/intellisense).</span><span class="sxs-lookup"><span data-stu-id="b4769-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/intellisense) page.</span></span>

1. <span data-ttu-id="b4769-115">Laden Sie die IntelliSense-Datei für die Sprache und Version herunter, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b4769-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="b4769-116">Extrahieren Sie den Inhalt der ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="b4769-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="b4769-117">Navigieren Sie zum IntelliSense-Ordner für .NET.</span><span class="sxs-lookup"><span data-stu-id="b4769-117">Navigate to the .NET Intellisense folder.</span></span>

   1. <span data-ttu-id="b4769-118">Navigieren Sie zum .NET-Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="b4769-118">Navigate to the .NET installation folder.</span></span> <span data-ttu-id="b4769-119">Standardmäßig befindet sich dieser unter *%ProgramFiles%\dotnet\packs*.</span><span class="sxs-lookup"><span data-stu-id="b4769-119">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>
   1. <span data-ttu-id="b4769-120">Wählen Sie aus, für welches SDK Sie IntelliSense installieren möchten, und navigieren Sie zum zugehörigen Pfad.</span><span class="sxs-lookup"><span data-stu-id="b4769-120">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="b4769-121">Sie haben die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="b4769-121">You have the following options:</span></span>

      | <span data-ttu-id="b4769-122">SDK-Typ</span><span class="sxs-lookup"><span data-stu-id="b4769-122">SDK type</span></span>              | <span data-ttu-id="b4769-123">`Path`</span><span class="sxs-lookup"><span data-stu-id="b4769-123">Path</span></span>                               |
      |-----------------------|------------------------------------|
      | <span data-ttu-id="b4769-124">.NET 5 oder höher und .NET Core</span><span class="sxs-lookup"><span data-stu-id="b4769-124">.NET 5+ and .NET Core</span></span> | <span data-ttu-id="b4769-125">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="b4769-125">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="b4769-126">Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="b4769-126">Windows Desktop</span></span>       | <span data-ttu-id="b4769-127">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="b4769-127">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="b4769-128">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="b4769-128">.NET Standard</span></span>         | <span data-ttu-id="b4769-129">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="b4769-129">*NETStandard.Library.Ref*</span></span>          |

   1. <span data-ttu-id="b4769-130">Navigieren Sie zur Version, für die Sie die lokalisierte IntelliSense-Datei installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b4769-130">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="b4769-131">Beispielsweise *5.0.0*.</span><span class="sxs-lookup"><span data-stu-id="b4769-131">For example, *5.0.0*.</span></span>
   1. <span data-ttu-id="b4769-132">Öffnen Sie den *ref* -Ordner.</span><span class="sxs-lookup"><span data-stu-id="b4769-132">Open the *ref* folder.</span></span>
   1. <span data-ttu-id="b4769-133">Öffnen Sie den Monikerordner.</span><span class="sxs-lookup"><span data-stu-id="b4769-133">Open the moniker folder.</span></span> <span data-ttu-id="b4769-134">Zum Beispiel: *net5.0*.</span><span class="sxs-lookup"><span data-stu-id="b4769-134">For example, *net5.0*.</span></span>

   <span data-ttu-id="b4769-135">Der vollständige Pfad, zu dem Sie navigieren würden, würde also in etwa wie folgt aussehen: *C:\Programme\dotnet\packs\Microsoft.NETCore.App.Ref\5.0.0\ref\net5.0*.</span><span class="sxs-lookup"><span data-stu-id="b4769-135">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\5.0.0\ref\net5.0*.</span></span>

1. <span data-ttu-id="b4769-136">Erstellen Sie einen Unterordner innerhalb des soeben geöffneten Monikerordners.</span><span class="sxs-lookup"><span data-stu-id="b4769-136">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="b4769-137">Der Name des Ordners gibt an, welche Sprache Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b4769-137">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="b4769-138">In der folgenden Tabelle werden die verschiedenen Optionen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="b4769-138">The following table specifies the different options:</span></span>

   | <span data-ttu-id="b4769-139">Sprache</span><span class="sxs-lookup"><span data-stu-id="b4769-139">Language</span></span>              | <span data-ttu-id="b4769-140">Ordnername</span><span class="sxs-lookup"><span data-stu-id="b4769-140">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="b4769-141">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="b4769-141">Brazilian Portuguese</span></span>  | <span data-ttu-id="b4769-142">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="b4769-142">*pt-br*</span></span>     |
   | <span data-ttu-id="b4769-143">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="b4769-143">Chinese (simplified)</span></span>  | <span data-ttu-id="b4769-144">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="b4769-144">*zh-hans*</span></span>   |
   | <span data-ttu-id="b4769-145">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="b4769-145">Chinese (traditional)</span></span> | <span data-ttu-id="b4769-146">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="b4769-146">*zh-hant*</span></span>   |
   | <span data-ttu-id="b4769-147">Französisch</span><span class="sxs-lookup"><span data-stu-id="b4769-147">French</span></span>                | <span data-ttu-id="b4769-148">*fr*</span><span class="sxs-lookup"><span data-stu-id="b4769-148">*fr*</span></span>        |
   | <span data-ttu-id="b4769-149">Deutsch</span><span class="sxs-lookup"><span data-stu-id="b4769-149">German</span></span>                | <span data-ttu-id="b4769-150">*de*</span><span class="sxs-lookup"><span data-stu-id="b4769-150">*de*</span></span>        |
   | <span data-ttu-id="b4769-151">Italienisch</span><span class="sxs-lookup"><span data-stu-id="b4769-151">Italian</span></span>               | <span data-ttu-id="b4769-152">*it*</span><span class="sxs-lookup"><span data-stu-id="b4769-152">*it*</span></span>        |
   | <span data-ttu-id="b4769-153">Japanisch</span><span class="sxs-lookup"><span data-stu-id="b4769-153">Japanese</span></span>              | <span data-ttu-id="b4769-154">*ja*</span><span class="sxs-lookup"><span data-stu-id="b4769-154">*ja*</span></span>        |
   | <span data-ttu-id="b4769-155">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="b4769-155">Korean</span></span>                | <span data-ttu-id="b4769-156">*ko*</span><span class="sxs-lookup"><span data-stu-id="b4769-156">*ko*</span></span>        |
   | <span data-ttu-id="b4769-157">Russisch</span><span class="sxs-lookup"><span data-stu-id="b4769-157">Russian</span></span>               | <span data-ttu-id="b4769-158">*ru*</span><span class="sxs-lookup"><span data-stu-id="b4769-158">*ru*</span></span>        |
   | <span data-ttu-id="b4769-159">Spanisch</span><span class="sxs-lookup"><span data-stu-id="b4769-159">Spanish</span></span>               | <span data-ttu-id="b4769-160">*es*</span><span class="sxs-lookup"><span data-stu-id="b4769-160">*es*</span></span>        |

1. <span data-ttu-id="b4769-161">Kopieren Sie die *XML* -Dateien, die Sie in Schritt 3 extrahiert haben, in diesen neuen Ordner.</span><span class="sxs-lookup"><span data-stu-id="b4769-161">Copy the *.xml* files you extracted in step 3 to this new folder.</span></span> <span data-ttu-id="b4769-162">Die *XML* -Dateien sind nach SDK-Ordnern aufgeschlüsselt. Kopieren Sie diese also in den entsprechenden SDK-Ordner, den Sie in Schritt 4 ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b4769-162">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose in step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="b4769-163">Ändern der Sprache in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b4769-163">Modify Visual Studio language</span></span>

<span data-ttu-id="b4769-164">Damit Visual Studio eine andere Sprache für IntelliSense verwenden kann, installieren Sie das entsprechende Sprachpaket.</span><span class="sxs-lookup"><span data-stu-id="b4769-164">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="b4769-165">Dies kann [während der Installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) oder zu einem späteren Zeitpunkt durch Ändern der Visual Studio-Installation erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b4769-165">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="b4769-166">Wenn Sie Visual Studio bereits auf die Sprache Ihrer Wahl konfiguriert haben, ist Ihre IntelliSense-Installation bereit.</span><span class="sxs-lookup"><span data-stu-id="b4769-166">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="b4769-167">Installieren des Sprachpakets</span><span class="sxs-lookup"><span data-stu-id="b4769-167">Install the language pack</span></span>

<span data-ttu-id="b4769-168">Wenn Sie das gewünschte Sprachpaket während des Setups nicht installiert haben, aktualisieren Sie Visual Studio wie folgt, um das Sprachpaket zu installieren:</span><span class="sxs-lookup"><span data-stu-id="b4769-168">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4769-169">Sie müssen sich mit einem Konto mit Administratorberechtigung anmelden, um Visual Studio zu installieren, zu aktualisieren oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b4769-169">To install, update, or modify Visual Studio, you must log on with an account that has administrator permission.</span></span> <span data-ttu-id="b4769-170">Weitere Informationen finden Sie unter [Benutzerberechtigungen und Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="b4769-170">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="b4769-171">Suchen Sie den Visual Studio-Installer auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="b4769-171">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="b4769-172">Auf einem Computer mit Windows 10 wählen Sie beispielsweise **Start** und blättern dann zum Buchstaben **V** , wo das Installationsprogramm als **Visual Studio-Installer** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b4769-172">For example, on a computer running Windows 10, select **Start** , and then scroll to the letter **V** , where it's listed as **Visual Studio Installer**.</span></span>

   ![Öffnen des Visual Studio-Installer unter Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="b4769-174">Sie können den Visual Studio-Installer auch an folgendem Speicherort finden:</span><span class="sxs-lookup"><span data-stu-id="b4769-174">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="b4769-175">Möglicherweise müssen Sie den Installer aktualisieren, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b4769-175">You might have to update the installer before continuing.</span></span> <span data-ttu-id="b4769-176">Wenn dies der Fall ist, befolgen Sie die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b4769-176">If so, follow the prompts.</span></span>

1. <span data-ttu-id="b4769-177">Suchen Sie im Installer nach der Edition von Visual Studio, der Sie das Sprachpaket hinzufügen möchten, und wählen Sie dann **Ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="b4769-177">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Aktualisieren oder Ändern von Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="b4769-179">Wenn die Schaltfläche **Ändern** nicht angezeigt wird, aber stattdessen eine Schaltfläche **Aktualisieren** angezeigt wird, müssen Sie Visual Studio aktualisieren, bevor Sie Ihre Installation ändern können.</span><span class="sxs-lookup"><span data-stu-id="b4769-179">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="b4769-180">Sobald die Aktualisierung abgeschlossen ist, sollte die Schaltfläche **Ändern** erscheinen.</span><span class="sxs-lookup"><span data-stu-id="b4769-180">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="b4769-181">Wählen Sie auf der Registerkarte **Sprachpakete** die Sprachen aus oder ab, die Sie installieren bzw. deinstallieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b4769-181">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Registerkarte der Sprachpakete in Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="b4769-183">Klicken Sie auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="b4769-183">Choose **Modify**.</span></span> <span data-ttu-id="b4769-184">Das Update startet.</span><span class="sxs-lookup"><span data-stu-id="b4769-184">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="b4769-185">Ändern der Spracheinstellungen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b4769-185">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="b4769-186">Nachdem Sie die gewünschten Sprachpakete installiert haben, ändern Sie Ihre Visual Studio-Einstellungen, um eine andere Sprache zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="b4769-186">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="b4769-187">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4769-187">Open Visual Studio.</span></span>

1. <span data-ttu-id="b4769-188">Wählen Sie im Startfenster **Ohne Code fortfahren** aus.</span><span class="sxs-lookup"><span data-stu-id="b4769-188">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="b4769-189">Wählen Sie in der Menüleiste **Tools** > **Optionen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4769-189">On the menu bar, select **Tools** > **Options**.</span></span> <span data-ttu-id="b4769-190">Das Dialogfeld „Optionen“ wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b4769-190">The Options dialog opens.</span></span>

1. <span data-ttu-id="b4769-191">Wählen Sie unter dem Knoten **Umgebung** **Internationale Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4769-191">Under the **Environment** node, choose **International Settings**.</span></span>

1. <span data-ttu-id="b4769-192">Wählen Sie aus der **Sprachen** -Dropdownliste eine Sprache Ihrer Wahl aus.</span><span class="sxs-lookup"><span data-stu-id="b4769-192">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="b4769-193">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4769-193">Choose **OK**.</span></span>

1. <span data-ttu-id="b4769-194">Ein Dialogfeld informiert Sie, dass Sie Visual Studio neu starten müssen, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="b4769-194">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="b4769-195">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4769-195">Choose **OK**.</span></span>

1. <span data-ttu-id="b4769-196">Starten Sie Visual Studio neu.</span><span class="sxs-lookup"><span data-stu-id="b4769-196">Restart Visual Studio.</span></span>

<span data-ttu-id="b4769-197">Danach sollte IntelliSense wie erwartet funktionieren, wenn Sie ein .NET-Projekt öffnen, das auf die Version der soeben installierten IntelliSense-Dateien ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b4769-197">After this, your IntelliSense should work as expected when you open a .NET project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4769-198">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4769-198">See also</span></span>

- [<span data-ttu-id="b4769-199">IntelliSense in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b4769-199">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
