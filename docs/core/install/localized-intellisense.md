---
title: Installieren der lokalisierten IntelliSense-Dateien
description: Erfahren Sie, wie Sie Ihren Entwicklungscomputer für die Verwendung lokalisierter IntelliSense-Dateien für .NET Core-Projekte in Visual Studio einrichten.
ms.date: 01/23/2020
ms.openlocfilehash: e45e225e58865ca2b529000ada0984fbeca850f3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157712"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a><span data-ttu-id="516ea-103">Installieren der lokalisierten IntelliSense-Dateien für .NET Core</span><span class="sxs-lookup"><span data-stu-id="516ea-103">How to install localized IntelliSense files for .NET Core</span></span>

<span data-ttu-id="516ea-104">[IntelliSense](/visualstudio/ide/using-intellisense) ist ein Hilfsmittel zur Codevervollständigung, die in verschiedenen integrierten Entwicklungsumgebungen (IDEs), wie z. B. Visual Studio, verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="516ea-104">[IntelliSense](/visualstudio/ide/using-intellisense) is a code-completion aid that is available in different integrated development environments (IDEs), such as Visual Studio.</span></span> <span data-ttu-id="516ea-105">Wenn Sie .NET Core-Projekte entwickeln, enthält das SDK standardmäßig nur die englische Version der IntelliSense-Dateien.</span><span class="sxs-lookup"><span data-stu-id="516ea-105">By default, when you're developing .NET Core projects, the SDK only includes the English version of the IntelliSense files.</span></span> <span data-ttu-id="516ea-106">In diesem Artikel erfahren Sie:</span><span class="sxs-lookup"><span data-stu-id="516ea-106">This article explains:</span></span>

- <span data-ttu-id="516ea-107">wie Sie die lokalisierte Version dieser Dateien installieren.</span><span class="sxs-lookup"><span data-stu-id="516ea-107">How to install the localized version of those files.</span></span>
- <span data-ttu-id="516ea-108">wie Sie die Visual Studio-Installation ändern, um eine andere Sprache zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="516ea-108">How to modify the Visual Studio installation to use a different language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="516ea-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="516ea-109">Prerequisites</span></span>

- <span data-ttu-id="516ea-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="516ea-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="516ea-111">[Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder eine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="516ea-111">[Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or a later version.</span></span>

## <a name="download-and-install-the-localized-intellisense-files"></a><span data-ttu-id="516ea-112">Herunterladen und Installieren der lokalisierten IntelliSense-Dateien</span><span class="sxs-lookup"><span data-stu-id="516ea-112">Download and install the localized IntelliSense files</span></span>

> [!IMPORTANT]
> <span data-ttu-id="516ea-113">Für diese Prozedur ist es erforderlich, dass Sie über eine Administratorberechtigung zum Kopieren der IntelliSense-Dateien in den .NET Core-Installationsordner verfügen.</span><span class="sxs-lookup"><span data-stu-id="516ea-113">This procedure requires that you have administrator permission to copy the IntelliSense files to the .NET Core installation folder.</span></span>

1. <span data-ttu-id="516ea-114">Navigieren Sie zur [Seite zum Herunterladen der IntelliSense-Dateien](https://dotnet.microsoft.com/download/dotnet-core/intellisense).</span><span class="sxs-lookup"><span data-stu-id="516ea-114">Go to the [Download IntelliSense files](https://dotnet.microsoft.com/download/dotnet-core/intellisense) page.</span></span>

1. <span data-ttu-id="516ea-115">Laden Sie die IntelliSense-Datei für die Sprache und Version herunter, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="516ea-115">Download the IntelliSense file for the language and version you'd like to use.</span></span>

1. <span data-ttu-id="516ea-116">Extrahieren Sie den Inhalt der ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="516ea-116">Extract the contents of the zip file.</span></span>

1. <span data-ttu-id="516ea-117">Navigieren Sie zum .NET Core IntelliSense-Ordner.</span><span class="sxs-lookup"><span data-stu-id="516ea-117">Navigate to the .NET Core Intellisense folder.</span></span>

   1. <span data-ttu-id="516ea-118">Navigieren Sie zum .NET Core IntelliSense-Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="516ea-118">Navigate to the .NET Core installation folder.</span></span> <span data-ttu-id="516ea-119">Standardmäßig befindet sich dieser unter *%ProgramFiles%\dotnet\packs*.</span><span class="sxs-lookup"><span data-stu-id="516ea-119">By default, it's under *%ProgramFiles%\dotnet\packs*.</span></span>
   1. <span data-ttu-id="516ea-120">Wählen Sie aus, für welches SDK Sie IntelliSense installieren möchten, und navigieren Sie zum zugehörigen Pfad.</span><span class="sxs-lookup"><span data-stu-id="516ea-120">Choose which SDK you want to install the IntelliSense for, and navigate to the associated path.</span></span> <span data-ttu-id="516ea-121">Sie haben die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="516ea-121">You have the following options:</span></span>

      | <span data-ttu-id="516ea-122">SDK-Typ</span><span class="sxs-lookup"><span data-stu-id="516ea-122">SDK type</span></span>        | <span data-ttu-id="516ea-123">Pfad</span><span class="sxs-lookup"><span data-stu-id="516ea-123">Path</span></span>                               |
      | --------------- | ---------------------------------- |
      | <span data-ttu-id="516ea-124">.NET Core</span><span class="sxs-lookup"><span data-stu-id="516ea-124">.NET Core</span></span>       | <span data-ttu-id="516ea-125">*Microsoft.NETCore.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="516ea-125">*Microsoft.NETCore.App.Ref*</span></span>        |
      | <span data-ttu-id="516ea-126">Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="516ea-126">Windows Desktop</span></span> | <span data-ttu-id="516ea-127">*Microsoft.WindowsDesktop.App.Ref*</span><span class="sxs-lookup"><span data-stu-id="516ea-127">*Microsoft.WindowsDesktop.App.Ref*</span></span> |
      | <span data-ttu-id="516ea-128">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="516ea-128">.NET Standard</span></span>   | <span data-ttu-id="516ea-129">*NETStandard.Library.Ref*</span><span class="sxs-lookup"><span data-stu-id="516ea-129">*NETStandard.Library.Ref*</span></span>          |

   1. <span data-ttu-id="516ea-130">Navigieren Sie zur Version, für die Sie die lokalisierte IntelliSense-Datei installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="516ea-130">Navigate to the version you want to install the localized IntelliSense for.</span></span> <span data-ttu-id="516ea-131">Zum Beispiel *3.1.0*.</span><span class="sxs-lookup"><span data-stu-id="516ea-131">For example, *3.1.0*.</span></span>
   1. <span data-ttu-id="516ea-132">Öffnen Sie den *ref*-Ordner.</span><span class="sxs-lookup"><span data-stu-id="516ea-132">Open the *ref* folder.</span></span>
   1. <span data-ttu-id="516ea-133">Öffnen Sie den Monikerordner.</span><span class="sxs-lookup"><span data-stu-id="516ea-133">Open the moniker folder.</span></span> <span data-ttu-id="516ea-134">Zum Beispiel *netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="516ea-134">For example, *netcoreapp3.1*.</span></span>

   <span data-ttu-id="516ea-135">Der vollständige Pfad, zu dem Sie navigieren würden, würde also ähnlich aussehen wie *C:\Programme\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span><span class="sxs-lookup"><span data-stu-id="516ea-135">So, the full path that you'd navigate to would look similar to *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.</span></span>

1. <span data-ttu-id="516ea-136">Erstellen Sie einen Unterordner innerhalb des soeben geöffneten Monikerordners.</span><span class="sxs-lookup"><span data-stu-id="516ea-136">Create a subfolder inside the moniker folder you just opened.</span></span> <span data-ttu-id="516ea-137">Der Name des Ordners gibt an, welche Sprache Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="516ea-137">The name of the folder indicates which language you want to use.</span></span> <span data-ttu-id="516ea-138">In der folgenden Tabelle werden die verschiedenen Optionen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="516ea-138">The following table specifies the different options:</span></span>

   | <span data-ttu-id="516ea-139">Sprache</span><span class="sxs-lookup"><span data-stu-id="516ea-139">Language</span></span>              | <span data-ttu-id="516ea-140">Ordnername</span><span class="sxs-lookup"><span data-stu-id="516ea-140">Folder name</span></span> |
   | --------------------- | ----------- |
   | <span data-ttu-id="516ea-141">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="516ea-141">Brazilian Portuguese</span></span>  | <span data-ttu-id="516ea-142">*pt-br*</span><span class="sxs-lookup"><span data-stu-id="516ea-142">*pt-br*</span></span>     |
   | <span data-ttu-id="516ea-143">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="516ea-143">Chinese (simplified)</span></span>  | <span data-ttu-id="516ea-144">*zh-hans*</span><span class="sxs-lookup"><span data-stu-id="516ea-144">*zh-hans*</span></span>   |
   | <span data-ttu-id="516ea-145">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="516ea-145">Chinese (traditional)</span></span> | <span data-ttu-id="516ea-146">*zh-hant*</span><span class="sxs-lookup"><span data-stu-id="516ea-146">*zh-hant*</span></span>   |
   | <span data-ttu-id="516ea-147">Französisch</span><span class="sxs-lookup"><span data-stu-id="516ea-147">French</span></span>                | <span data-ttu-id="516ea-148">*fr*</span><span class="sxs-lookup"><span data-stu-id="516ea-148">*fr*</span></span>        |
   | <span data-ttu-id="516ea-149">Deutsch</span><span class="sxs-lookup"><span data-stu-id="516ea-149">German</span></span>                | <span data-ttu-id="516ea-150">*de*</span><span class="sxs-lookup"><span data-stu-id="516ea-150">*de*</span></span>        |
   | <span data-ttu-id="516ea-151">Italienisch</span><span class="sxs-lookup"><span data-stu-id="516ea-151">Italian</span></span>               | <span data-ttu-id="516ea-152">*it*</span><span class="sxs-lookup"><span data-stu-id="516ea-152">*it*</span></span>        |
   | <span data-ttu-id="516ea-153">Japanisch</span><span class="sxs-lookup"><span data-stu-id="516ea-153">Japanese</span></span>              | <span data-ttu-id="516ea-154">*ja*</span><span class="sxs-lookup"><span data-stu-id="516ea-154">*ja*</span></span>        |
   | <span data-ttu-id="516ea-155">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="516ea-155">Korean</span></span>                | <span data-ttu-id="516ea-156">*ko*</span><span class="sxs-lookup"><span data-stu-id="516ea-156">*ko*</span></span>        |
   | <span data-ttu-id="516ea-157">Russisch</span><span class="sxs-lookup"><span data-stu-id="516ea-157">Russian</span></span>               | <span data-ttu-id="516ea-158">*ru*</span><span class="sxs-lookup"><span data-stu-id="516ea-158">*ru*</span></span>        |
   | <span data-ttu-id="516ea-159">Spanisch</span><span class="sxs-lookup"><span data-stu-id="516ea-159">Spanish</span></span>               | <span data-ttu-id="516ea-160">*es*</span><span class="sxs-lookup"><span data-stu-id="516ea-160">*es*</span></span>        |

1. <span data-ttu-id="516ea-161">Kopieren Sie die *xml*-Dateien, die Sie in Schritt 3 extrahiert haben, in diesen neuen Ordner.</span><span class="sxs-lookup"><span data-stu-id="516ea-161">Copy the *.xml* files you extracted on step 3 to this new folder.</span></span> <span data-ttu-id="516ea-162">Die *xml*-Dateien sind nach SDK-Ordnern aufgeschlüsselt. Kopieren Sie diese also in den entsprechenden SDK-Ordner, den Sie in Schritt 4 ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="516ea-162">The *.xml* files are broken down by SDK folders, so copy them to the matching SDK you chose on step 4.</span></span>

## <a name="modify-visual-studio-language"></a><span data-ttu-id="516ea-163">Ändern der Sprache in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="516ea-163">Modify Visual Studio language</span></span>

<span data-ttu-id="516ea-164">Damit Visual Studio eine andere Sprache für IntelliSense verwenden kann, installieren Sie das entsprechende Sprachpaket.</span><span class="sxs-lookup"><span data-stu-id="516ea-164">For Visual Studio to use a different language for IntelliSense, install the appropriate language pack.</span></span> <span data-ttu-id="516ea-165">Dies kann [während der Installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) oder zu einem späteren Zeitpunkt durch Ändern der Visual Studio-Installation erfolgen.</span><span class="sxs-lookup"><span data-stu-id="516ea-165">This can be done [during installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) or at a later time by modifying the Visual Studio installation.</span></span> <span data-ttu-id="516ea-166">Wenn Sie Visual Studio bereits auf die Sprache Ihrer Wahl konfiguriert haben, ist Ihre IntelliSense-Installation bereit.</span><span class="sxs-lookup"><span data-stu-id="516ea-166">If you already have Visual Studio configured to the language of your choice, your IntelliSense installation is ready.</span></span>

### <a name="install-the-language-pack"></a><span data-ttu-id="516ea-167">Installieren des Sprachpakets</span><span class="sxs-lookup"><span data-stu-id="516ea-167">Install the language pack</span></span>

<span data-ttu-id="516ea-168">Wenn Sie das gewünschte Sprachpaket während des Setups nicht installiert haben, aktualisieren Sie Visual Studio wie folgt, um das Sprachpaket zu installieren:</span><span class="sxs-lookup"><span data-stu-id="516ea-168">If you didn't install the desired language pack during setup, update Visual Studio as follows to install the language pack:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="516ea-169">Sie müssen sich mit einem Konto mit Administratorberechtigung anmelden, um Visual Studio zu installieren, zu aktualisieren oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="516ea-169">To install, update, or modify Visual Studio, you must log on with an account that has administrator permission.</span></span> <span data-ttu-id="516ea-170">Weitere Informationen finden Sie unter [Benutzerberechtigungen und Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="516ea-170">For more information, see [User permissions and Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).</span></span>

1. <span data-ttu-id="516ea-171">Suchen Sie den Visual Studio-Installer auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="516ea-171">Find the Visual Studio Installer on your computer.</span></span>

   <span data-ttu-id="516ea-172">Auf einem Computer mit Windows 10 wählen Sie beispielsweise **Start** und blättern dann zum Buchstaben **V**, wo das Installationsprogramm als **Visual Studio-Installer** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="516ea-172">For example, on a computer running Windows 10, select **Start**, and then scroll to the letter **V**, where it's listed as **Visual Studio Installer**.</span></span>

   ![Öffnen des Visual Studio-Installer unter Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > <span data-ttu-id="516ea-174">Sie können den Visual Studio-Installer auch an folgendem Speicherort finden:</span><span class="sxs-lookup"><span data-stu-id="516ea-174">You can also find the Visual Studio Installer in the following location:</span></span>
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   <span data-ttu-id="516ea-175">Möglicherweise müssen Sie den Installer aktualisieren, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="516ea-175">You might have to update the installer before continuing.</span></span> <span data-ttu-id="516ea-176">Wenn dies der Fall ist, befolgen Sie die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="516ea-176">If so, follow the prompts.</span></span>

1. <span data-ttu-id="516ea-177">Suchen Sie im Installer nach der Edition von Visual Studio, der Sie das Sprachpaket hinzufügen möchten, und wählen Sie dann **Ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="516ea-177">In the installer, look for the edition of Visual Studio that you want to add the language pack to, and then choose **Modify**.</span></span>

   ![Aktualisieren oder Ändern von Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > <span data-ttu-id="516ea-179">Wenn die Schaltfläche **Ändern** nicht angezeigt wird, aber stattdessen eine Schaltfläche **Aktualisieren** angezeigt wird, müssen Sie Visual Studio aktualisieren, bevor Sie Ihre Installation ändern können.</span><span class="sxs-lookup"><span data-stu-id="516ea-179">If you don't see a **Modify** button but you see an **Update** one instead, you need to update your Visual Studio before you can modify your installation.</span></span>
   > <span data-ttu-id="516ea-180">Sobald die Aktualisierung abgeschlossen ist, sollte die Schaltfläche **Ändern** erscheinen.</span><span class="sxs-lookup"><span data-stu-id="516ea-180">After the update is finished, the **Modify** button should appear.</span></span>

1. <span data-ttu-id="516ea-181">Wählen Sie auf der Registerkarte **Sprachpakete** die Sprachen aus oder ab, die Sie installieren bzw. deinstallieren möchten.</span><span class="sxs-lookup"><span data-stu-id="516ea-181">In the **Language packs** tab, select or deselect the languages you want to install or uninstall.</span></span>

   ![Registerkarte der Sprachpakete in Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. <span data-ttu-id="516ea-183">Klicken Sie auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="516ea-183">Choose **Modify**.</span></span> <span data-ttu-id="516ea-184">Das Update startet.</span><span class="sxs-lookup"><span data-stu-id="516ea-184">The update starts.</span></span>

### <a name="modify-language-settings-in-visual-studio"></a><span data-ttu-id="516ea-185">Ändern der Spracheinstellungen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="516ea-185">Modify language settings in Visual Studio</span></span>

<span data-ttu-id="516ea-186">Nachdem Sie die gewünschten Sprachpakete installiert haben, ändern Sie Ihre Visual Studio-Einstellungen, um eine andere Sprache zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="516ea-186">Once you've installed the desired language packs, modify your Visual Studio settings to use a different language:</span></span>

1. <span data-ttu-id="516ea-187">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="516ea-187">Open Visual Studio.</span></span>

1. <span data-ttu-id="516ea-188">Wählen Sie im Startfenster **Ohne Code fortfahren** aus.</span><span class="sxs-lookup"><span data-stu-id="516ea-188">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="516ea-189">Wählen Sie in der Menüleiste **Tools** > **Optionen** aus.</span><span class="sxs-lookup"><span data-stu-id="516ea-189">On the menu bar, select **Tools** > **Options**.</span></span> <span data-ttu-id="516ea-190">Das Dialogfeld „Optionen“ wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="516ea-190">The Options dialog opens.</span></span>

1. <span data-ttu-id="516ea-191">Wählen Sie unter dem Knoten **Umgebung** **Internationale Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="516ea-191">Under the **Environment** node, choose **International Settings**.</span></span>

1. <span data-ttu-id="516ea-192">Wählen Sie aus der **Sprachen**-Dropdownliste eine Sprache Ihrer Wahl aus.</span><span class="sxs-lookup"><span data-stu-id="516ea-192">On the **Language** drop-down, select the desired language.</span></span> <span data-ttu-id="516ea-193">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="516ea-193">Choose **OK**.</span></span>

1. <span data-ttu-id="516ea-194">Ein Dialogfeld informiert Sie, dass Sie Visual Studio neu starten müssen, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="516ea-194">A dialog informs you that you have to restart Visual Studio for the changes to take effect.</span></span> <span data-ttu-id="516ea-195">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="516ea-195">Choose **OK**.</span></span>

1. <span data-ttu-id="516ea-196">Starten Sie Visual Studio neu.</span><span class="sxs-lookup"><span data-stu-id="516ea-196">Restart Visual Studio.</span></span>

<span data-ttu-id="516ea-197">Danach sollte IntelliSense wie erwartet funktionieren, wenn Sie ein .NET Core-Projekt öffnen, das auf die Version der soeben installierten IntelliSense-Dateien abzielt.</span><span class="sxs-lookup"><span data-stu-id="516ea-197">After this, your IntelliSense should work as expected when you open a .NET Core project that targets the version of the IntelliSense files you just installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="516ea-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="516ea-198">See also</span></span>

- [<span data-ttu-id="516ea-199">IntelliSense in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="516ea-199">IntelliSense in Visual Studio</span></span>](/visualstudio/ide/using-intellisense)
