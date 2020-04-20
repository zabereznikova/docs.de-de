---
title: Bereitstellen von .NET Core-Apps mit Visual Studio
description: Erfahren Sie, wie Sie eine .NET Core-App mit Visual Studio bereitstellen.
ms.date: 09/03/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: f2299ac807c845dab482306cc4c710560bb7f1e7
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607861"
---
# <a name="deploy-net-core-apps-with-visual-studio"></a><span data-ttu-id="20eac-103">Bereitstellen von .NET Core-Apps mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20eac-103">Deploy .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="20eac-104">Sie können eine .NET Core-Anwendung entweder als *Framework-abhängige Bereitstellung* bereitstellen, was die Binärdateien Ihrer Anwendung einschließt, jedoch von Präsenz von .NET Core auf dem Zielsystem abhängt, oder als *eigenständige Bereitstellung*,die jeweils Ihre Anwendung sowie .NET Core-Binärdateien einschließt.</span><span class="sxs-lookup"><span data-stu-id="20eac-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and .NET Core binaries.</span></span> <span data-ttu-id="20eac-105">Einen Überblick über die Bereitstellung von .NET Core-Anwendungen finden Sie unter [.NET Core Anwendungsbereitstellung](index.md).</span><span class="sxs-lookup"><span data-stu-id="20eac-105">For an overview of .NET Core application deployment, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="20eac-106">Die folgenden Abschnitte zeigen, wie Sie Microsoft Visual Studio zum Erstellen der folgenden Bereitstellungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="20eac-106">The following sections show how to use Microsoft Visual Studio to create the following kinds of deployments:</span></span>

- <span data-ttu-id="20eac-107">Framework-abhängige Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="20eac-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="20eac-108">Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="20eac-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="20eac-109">Eigenständige Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="20eac-109">Self-contained deployment</span></span>
- <span data-ttu-id="20eac-110">Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="20eac-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="20eac-111">Informationen zur Verwendung von Visual Studio für die Entwicklung von .NET Core-Anwendungen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](../install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="20eac-111">For information on using Visual Studio to develop .NET Core applications, see [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-windows).</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="20eac-112">Framework-abhängige Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="20eac-112">Framework-dependent deployment</span></span>

<span data-ttu-id="20eac-113">Die Bereitstellung einer Framework-abhängigen Bereitstellung ohne Drittanbieter-Abhängigkeiten umfasst nur das Erstellen, Testen und Veröffentlichen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="20eac-113">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="20eac-114">Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess.</span><span class="sxs-lookup"><span data-stu-id="20eac-114">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="20eac-115">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="20eac-115">Create the project.</span></span>

   <span data-ttu-id="20eac-116">Wählen Sie **Datei** > **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-116">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="20eac-117">Erweitern Sie im Dialogfeld **Neues Projekt** die Projektkategorien Ihrer Programmiersprache (C# oder Visual Basic) im Bereich **Installiert**, wählen Sie **.NET Core** aus, und wählen Sie dann im mittleren Bereich die Vorlage **Konsolenanwendung (.NET Core)** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-117">In the **New Project** dialog, expand your language's (C# or Visual Basic) project categories in the **Installed** project types pane, choose **.NET Core**, and then select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="20eac-118">Geben Sie im Textfeld **Name** einen Projektnamen ein, z.B. „FDD“.</span><span class="sxs-lookup"><span data-stu-id="20eac-118">Enter a project name, such as "FDD", in the **Name** text box.</span></span> <span data-ttu-id="20eac-119">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="20eac-119">Select the **OK** button.</span></span>

1. <span data-ttu-id="20eac-120">Fügen Sie den Quellcode der Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="20eac-120">Add the application's source code.</span></span>

   <span data-ttu-id="20eac-121">Öffnen Sie die Datei *Program.cs* oder *Program.vb* im Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="20eac-121">Open the *Program.cs* or *Program.vb* file in the editor and replace the autogenerated code with the following code.</span></span> <span data-ttu-id="20eac-122">Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20eac-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="20eac-123">Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.</span><span class="sxs-lookup"><span data-stu-id="20eac-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. <span data-ttu-id="20eac-124">Erstellen Sie ein Debugbuild Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="20eac-124">Create a Debug build of your app.</span></span>

   <span data-ttu-id="20eac-125">Wählen Sie **Erstellen** > **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-125">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="20eac-126">Sie können auch das Debugbuild Ihrer Anwendung erstellen und ausführen, indem Sie **Debuggen** > **Debugging starten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="20eac-126">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="20eac-127">Stellen Sie Ihre App bereit.</span><span class="sxs-lookup"><span data-stu-id="20eac-127">Deploy your app.</span></span>

   <span data-ttu-id="20eac-128">Nachdem Sie die Anwendung debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="20eac-128">After you've debugged and tested the program, create the files to be deployed with your app.</span></span> <span data-ttu-id="20eac-129">Um eine Veröffentlichung über Visual Studio durchzuführen, tun Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20eac-129">To publish from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="20eac-130">Ändern Sie die Projektmappenkonfiguration von **Debuggen** zu **Freigabe** auf der Symbolleiste, um eine Releaseversion (anstatt eine Debugversion) Ihrer App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20eac-130">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="20eac-131">Führen Sie auf dem Projekt (nicht in der Projektmappe) im **Projektmappen-Explorer** einen Rechtsklick aus, und wählen Sie **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-131">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

      1. <span data-ttu-id="20eac-132">Wählen Sie auf der Registerkarte **Veröffentlichen** **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-132">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="20eac-133">Visual Studio schreibt die Dateien, die Ihre Anwendung enthalten, in das lokale Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="20eac-133">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="20eac-134">Die Registerkarte **Veröffentlichen** zeigt nun ein einzelnes Profil an: **FolderProfile**.</span><span class="sxs-lookup"><span data-stu-id="20eac-134">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="20eac-135">Die Konfigurationseinstellungen des Profils werden im Abschnitt **Zusammenfassung** der Registerkarte gezeigt.</span><span class="sxs-lookup"><span data-stu-id="20eac-135">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span>

   <span data-ttu-id="20eac-136">Die resultierenden Dateien werden unter Windows und `publish` auf Unix-Systemen in ein Verzeichnis namens `Publish` platziert, das sich in einem Unterverzeichnis des Unterverzeichnisses *.\bin\release\netcoreapp2.1* Ihres Projekts befindet.</span><span class="sxs-lookup"><span data-stu-id="20eac-136">The resulting files are placed in a directory named `Publish` on Windows and `publish` on Unix systems that is in a subdirectory of your project's *.\bin\release\netcoreapp2.1* subdirectory.</span></span>

<span data-ttu-id="20eac-137">Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="20eac-137">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="20eac-138">Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich.</span><span class="sxs-lookup"><span data-stu-id="20eac-138">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="20eac-139">Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu packen.</span><span class="sxs-lookup"><span data-stu-id="20eac-139">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="20eac-140">Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="20eac-140">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="20eac-141">Stellen Sie den vollständige Satz von Anwendungsdateien so bereit, wie Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="20eac-141">Deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="20eac-142">Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="20eac-142">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="20eac-143">Sobald die Anwendung installiert ist, können Benutzer sie mithilfe des `dotnet`-Befehls ausführen und den Dateinamen der Anwendung bereitstellen, z.B. `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="20eac-143">Once installed, users can then execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="20eac-144">Das Installationsprogramm sollte zusätzlich zu den Binärdateien der Anwendung das freigegebene Framework-Installationsprogramm bündeln, oder als erforderliche Komponente im Rahmen der Anwendungsinstallation überprüfen.</span><span class="sxs-lookup"><span data-stu-id="20eac-144">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="20eac-145">Die Installation des gemeinsam genutzten Frameworks erfordert Administrator-/Root-Zugriff, da es sich um eine computerweite Installation handelt.</span><span class="sxs-lookup"><span data-stu-id="20eac-145">Installation of the shared framework requires Administrator/root access since it is machine-wide.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="20eac-146">Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="20eac-146">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="20eac-147">Die Bereitstellung einer Framework-abhängigen Bereitstellung mit mindestens einer Drittanbieterabhängigkeit erfordert, dass Abhängigkeiten für Ihr Projekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="20eac-147">Deploying a framework-dependent deployment with one or more third-party dependencies requires that any dependencies be available to your project.</span></span> <span data-ttu-id="20eac-148">Die folgenden Schritte müssen noch durchgeführt werden, bevor Sie Ihre App erstellen können:</span><span class="sxs-lookup"><span data-stu-id="20eac-148">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="20eac-149">Verwenden Sie den **NuGet-Paket-Manager**, um einem NuGet-Paket einen Verweis für Ihr Projekt hinzuzufügen. Falls das Paket noch nicht auf Ihrem System verfügbar ist, installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="20eac-149">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="20eac-150">Wählen Sie zum Öffnen des Paket-Managers **Tools** > **NuGet-Paket-Manager** > **NuGet-Pakete für Projektmappe verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-150">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="20eac-151">Bestätigen Sie, dass Ihre Drittanbieterabhängigkeiten (z. B. `Newtonsoft.Json`) auf Ihrem System installiert sind. Falls dies nicht der Fall ist, installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="20eac-151">Confirm that your third-party dependencies (for example, `Newtonsoft.Json`) are installed on your system and, if they aren't, install them.</span></span> <span data-ttu-id="20eac-152">Die Registerkarte **Installiert** listet NuGet-Pakete auf, die auf Ihrem System installiert sind.</span><span class="sxs-lookup"><span data-stu-id="20eac-152">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="20eac-153">Wenn `Newtonsoft.Json` hier nicht aufgelistet ist, wählen Sie die Registerkarte **Durchsuchen** aus, und geben Sie „Newtonsoft.Json“ in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="20eac-153">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="20eac-154">Wählen Sie `Newtonsoft.Json` aus, und wählen Sie im rechten Bereich Ihre Projekt, bevor Sie auf **Installieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="20eac-154">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="20eac-155">Wenn `Newtonsoft.Json` bereits auf Ihrem System installiert ist, fügen Sie es Ihrem Projekt hinzu, indem Sie Ihr Projekt im rechten Bereich der Registerkarte **Pakete für Projektmappe verwalten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="20eac-155">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="20eac-156">Eine frameworkabhängige Bereitstellung mit Drittanbieterabhängigkeiten ist nur so portierbar wie ihre Drittanbieterabhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="20eac-156">A framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="20eac-157">Falls eine Drittanbieter-Bibliothek nur macOS unterstützen sollte, so wird die Anwendung nicht auf Windows-Systeme übertragbar sein.</span><span class="sxs-lookup"><span data-stu-id="20eac-157">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="20eac-158">Dies kann geschehen, wenn die Drittanbieter-Abhängigkeit selbst vom nativen Code abhängt.</span><span class="sxs-lookup"><span data-stu-id="20eac-158">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="20eac-159">Ein gutes Beispiel dafür ist der [Kestrel-Server](/aspnet/core/fundamentals/servers/kestrel), der eine native Abhängigkeit unter [libuv](https://github.com/libuv/libuv) erfordert.</span><span class="sxs-lookup"><span data-stu-id="20eac-159">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="20eac-160">Wenn bei dieser Art von Drittanbieter-Abhängigkeit eine FDD für eine Anwendung erstellt wird, enthält die veröffentlichte Ausgabe einen Ordner für jede [Runtime-ID (RID)](../rid-catalog.md), die die native Abhängigkeit unterstützt (und im NuGet-Paket vorhanden ist).</span><span class="sxs-lookup"><span data-stu-id="20eac-160">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="self-contained-deployment-without-third-party-dependencies"></a><a name="simpleSelf"></a> <span data-ttu-id="20eac-161">Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="20eac-161">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="20eac-162">Das Bereitstellen einer eigenständigen Bereitstellung ohne Abhängigkeiten von Drittanbietern umfasst das Erstellen des Projekts, das Ändern der *CSPROJ*-Datei sowie das Erstellen, Testen und Veröffentlichen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="20eac-162">Deploying a self-contained deployment with no third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="20eac-163">Ein einfaches, in C# geschriebenes Beispiel veranschaulicht den Prozess.</span><span class="sxs-lookup"><span data-stu-id="20eac-163">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="20eac-164">Zunächst erstellen, codieren und testen Sie Ihr Projekt wie eine Framework-abhängige Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="20eac-164">You begin by creating, coding, and testing your project just as you would a framework-dependent deployment:</span></span>

1. <span data-ttu-id="20eac-165">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="20eac-165">Create the project.</span></span>

   <span data-ttu-id="20eac-166">Wählen Sie **Datei** > **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-166">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="20eac-167">Erweitern Sie im Dialogfeld **Neues Projekt** die Projektkategorien Ihrer Programmiersprache (C# oder Visual Basic) im Bereich **Installiert**, wählen Sie **.NET Core** aus, und wählen Sie dann im mittleren Bereich die Vorlage **Konsolenanwendung (.NET Core)** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-167">In the **New Project** dialog, expand your language's (C# or Visual Basic) project categories in the **Installed** project types pane, choose **.NET Core**, and then select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="20eac-168">Geben Sie im Textfeld **Name** einen Projektnamen ein, z.B. „SCD“, und klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="20eac-168">Enter a project name, such as "SCD", in the **Name** text box, and select the **OK** button.</span></span>

1. <span data-ttu-id="20eac-169">Fügen Sie den Quellcode der Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="20eac-169">Add the application's source code.</span></span>

   <span data-ttu-id="20eac-170">Öffnen Sie die Datei *Program.cs* oder *Program.vb* in Ihrem Editor, und ersetzen Sie den automatisch generierten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="20eac-170">Open the *Program.cs* or *Program.vb* file in your editor, and replace the autogenerated code with the following code.</span></span> <span data-ttu-id="20eac-171">Der Benutzer wird zur Texteingabe aufgefordert, und die einzelnen Wörter, die vom Benutzer eingegeben wurden, werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20eac-171">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="20eac-172">Der reguläre Ausdruck `\w+` wird verwendet, um Wörter im Eingabetext zu trennen.</span><span class="sxs-lookup"><span data-stu-id="20eac-172">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](~/samples/snippets/core/deploying/cs/deployment-example.cs)]
   [!code-vb[deployment#1](~/samples/snippets/core/deploying/vb/deployment-example.vb)]

1. <span data-ttu-id="20eac-173">Bestimmen Sie, ob Sie den invarianten Globalisierungsmodus verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="20eac-173">Determine whether you want to use globalization invariant mode.</span></span>

   <span data-ttu-id="20eac-174">Insbesondere, wenn Ihre Anwendung für Linux konzipiert ist, können Sie die Gesamtgröße Ihrer Bereitstellung reduzieren, indem Sie den [invarianten Globalisierungsmodus](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="20eac-174">Particularly if your app targets Linux, you can reduce the total size of your deployment by taking advantage of [globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span> <span data-ttu-id="20eac-175">Der invariante Globalisierungsmodus eignet sich für Anwendungen, die nicht für den globalen Einsatz ausgelegt sind, und Formatierungskonventionen, Groß-/Kleinschreibungskonventionen, Zeichenfolgenvergleiche und Sortierreihenfolgen der [invarianten Kultur](xref:System.Globalization.CultureInfo.InvariantCulture) verwenden können.</span><span class="sxs-lookup"><span data-stu-id="20eac-175">Globalization invariant mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span>

   <span data-ttu-id="20eac-176">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf Ihr Projekt (nicht auf die Projektmappe), und klicken Sie auf **SCD.csproj bearbeiten** oder **SCD.vbproj bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="20eac-176">To enable invariant mode, right-click on your project (not the solution) in **Solution Explorer**, and select **Edit SCD.csproj** or **Edit SCD.vbproj**.</span></span> <span data-ttu-id="20eac-177">Fügen Sie der Datei dann die folgenden hervorgehobenen Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="20eac-177">Then add the following highlighted lines to the file:</span></span>

   [!code-xml[globalization-invariant-mode](~/samples/snippets/core/deploying/xml/invariant.csproj?highlight=6-8)]

1. <span data-ttu-id="20eac-178">Erstellen Sie einen Debugbuild Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="20eac-178">Create a Debug build of your application.</span></span>

   <span data-ttu-id="20eac-179">Wählen Sie **Erstellen** > **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-179">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="20eac-180">Sie können auch das Debugbuild Ihrer Anwendung erstellen und ausführen, indem Sie **Debuggen** > **Debugging starten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="20eac-180">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span> <span data-ttu-id="20eac-181">Mit diesem Schritt können Sie beim Debuggen Probleme mit Ihrer Anwendung identifizieren, die auftreten, wenn sie auf Ihrer Hostplattform ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="20eac-181">This debugging step lets you identify problems with your application when it's running on your host platform.</span></span> <span data-ttu-id="20eac-182">Sie müssen dies dennoch auf jeder Zielplattform testen.</span><span class="sxs-lookup"><span data-stu-id="20eac-182">You still will have to test it on each of your target platforms.</span></span>

   <span data-ttu-id="20eac-183">Wenn Sie den invarianten Globalisierungsmodus aktiviert haben, stellen Sie unbedingt sicher, ob das Fehlen von kulturabhängigen Daten für die Anwendung geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="20eac-183">If you've enabled globalization invariant mode, be particularly sure to test whether the absence of culture-sensitive data is suitable for your application.</span></span>

<span data-ttu-id="20eac-184">Sobald Sie das Debuggen abgeschlossen haben, können Sie Ihre eigenständige Bereitstellung veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="20eac-184">Once you've finished debugging, you can publish your self-contained deployment:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="visual-studio-156-and-earlier"></a>[<span data-ttu-id="20eac-185">Visual Studio 15.6 und frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="20eac-185">Visual Studio 15.6 and earlier</span></span>](#tab/vs156)

<span data-ttu-id="20eac-186">Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer App für jede Zielplattform bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20eac-186">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

<span data-ttu-id="20eac-187">Um eine Veröffentlichung Ihrer App über Visual Studio durchzuführen, tun Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20eac-187">To publish your app from Visual Studio, do the following:</span></span>

1. <span data-ttu-id="20eac-188">Definieren Sie die Zielplattformen für Ihre App.</span><span class="sxs-lookup"><span data-stu-id="20eac-188">Define the platforms that your app will target.</span></span>

   1. <span data-ttu-id="20eac-189">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf Ihr Projekt (nicht auf die Projektmappe), und wählen Sie **SCD.csproj bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-189">Right-click on your project (not the solution) in **Solution Explorer** and select **Edit SCD.csproj**.</span></span>

   1. <span data-ttu-id="20eac-190">Erstellen Sie das Tag `<RuntimeIdentifiers>` im Abschnitt `<PropertyGroup>` Ihrer Datei *csproj*, der die Plattformen Ihrer Anwendungsziele definiert und die Runtime-ID jeder Zielplattform angibt.</span><span class="sxs-lookup"><span data-stu-id="20eac-190">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets, and specify the runtime identifier (RID) of each platform that you target.</span></span> <span data-ttu-id="20eac-191">Sie müssen auch ein Semikolon hinzufügen, um die RIDs trennen.</span><span class="sxs-lookup"><span data-stu-id="20eac-191">You also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="20eac-192">Sie finden eine RID-Liste im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="20eac-192">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="20eac-193">Das folgende Beispiel gibt an, dass die Anwendung unter den Betriebssystemen Windows 10 (64-Bit) und OS X 10.11 (64-Bit) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="20eac-193">For example, the following example indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

   ```xml
   <PropertyGroup>
      <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
   </PropertyGroup>
   ```

   <span data-ttu-id="20eac-194">Das Element `<RuntimeIdentifiers>` kann jedem `<PropertyGroup>`-Element in Ihrer Datei *CSPROJ* hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="20eac-194">The `<RuntimeIdentifiers>` element can go into any `<PropertyGroup>` that you have in your *csproj* file.</span></span> <span data-ttu-id="20eac-195">Eine vollständige *CSPROJ*-Beispieldatei wird später in diesem Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20eac-195">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="20eac-196">Veröffentlichen Sie die App.</span><span class="sxs-lookup"><span data-stu-id="20eac-196">Publish your app.</span></span>

   <span data-ttu-id="20eac-197">Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer App für jede Zielplattform bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20eac-197">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="20eac-198">Um eine Veröffentlichung Ihrer App über Visual Studio durchzuführen, tun Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20eac-198">To publish your app from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="20eac-199">Ändern Sie die Projektmappenkonfiguration von **Debuggen** zu **Freigabe** auf der Symbolleiste, um eine Releaseversion (anstatt eine Debugversion) Ihrer App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20eac-199">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="20eac-200">Führen Sie auf dem Projekt (nicht in der Projektmappe) im **Projektmappen-Explorer** einen Rechtsklick aus, und wählen Sie **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-200">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

      1. <span data-ttu-id="20eac-201">Wählen Sie auf der Registerkarte **Veröffentlichen** **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-201">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="20eac-202">Visual Studio schreibt die Dateien, die Ihre Anwendung enthalten, in das lokale Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="20eac-202">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="20eac-203">Die Registerkarte **Veröffentlichen** zeigt nun ein einzelnes Profil an: **FolderProfile**.</span><span class="sxs-lookup"><span data-stu-id="20eac-203">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="20eac-204">Die Konfigurationseinstellungen des Profils werden im Abschnitt **Zusammenfassung** der Registerkarte gezeigt. **Ziellaufzeit** identifiziert, welche Laufzeit veröffentlicht wurde; **Zielort** identifiziert, wo die Dateien für die eigenständige Bereitstellung geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="20eac-204">The profile's configuration settings are shown in the **Summary** section of the tab. **Target Runtime** identifies which runtime has been published, and **Target Location** identifies where the files for the self-contained deployment were written.</span></span>

      1. <span data-ttu-id="20eac-205">Visual Studio schreibt standardmäßig alle veröffentlichten Dateien in ein einzelnes Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="20eac-205">Visual Studio by default writes all published files to a single directory.</span></span> <span data-ttu-id="20eac-206">Der Einfachheit halber ist es am besten, separate Profile für jede Ziellaufzeit zu erstellen und veröffentlichte Dateien in einem plattformspezifischen Verzeichnis zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="20eac-206">For convenience, it's best to create separate profiles for each target runtime and to place published files in a platform-specific directory.</span></span> <span data-ttu-id="20eac-207">Dafür muss ein separates Veröffentlichungsprofil für jede Zielplattform erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="20eac-207">This involves creating a separate publishing profile for each target platform.</span></span> <span data-ttu-id="20eac-208">Erstellen Sie nun die Anwendung für jede Plattform neu, indem Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="20eac-208">So now rebuild the application for each platform by doing the following:</span></span>

         1. <span data-ttu-id="20eac-209">Wählen Sie **Neues Profil erstellen** im Dialogfeld **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-209">Select **Create new profile** in the **Publish** dialog.</span></span>

         1. <span data-ttu-id="20eac-210">Ändern Sie im Dialogfeld **Veröffentlichungsziel auswählen** den Speicherort **Ordner auswählen** in *bin\Release\PublishOutput\win10-x64*.</span><span class="sxs-lookup"><span data-stu-id="20eac-210">In the **Pick a publish target** dialog, change the **Choose a folder** location to *bin\Release\PublishOutput\win10-x64*.</span></span> <span data-ttu-id="20eac-211">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="20eac-211">Select **OK**.</span></span>

         1. <span data-ttu-id="20eac-212">Wählen Sie das neue Profil (**FolderProfile1**) in der Liste der Profile aus, und stellen Sie sicher, dass die **Ziellaufzeit**`win10-x64` ist.</span><span class="sxs-lookup"><span data-stu-id="20eac-212">Select the new profile (**FolderProfile1**) in the list of profiles, and make sure that the **Target Runtime** is `win10-x64`.</span></span> <span data-ttu-id="20eac-213">Falls nicht, wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-213">If it isn't, select **Settings**.</span></span> <span data-ttu-id="20eac-214">Ändern Sie im Dialogfeld **Profileinstellungen** die **Ziellaufzeit** in `win10-x64`, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="20eac-214">In the **Profile Settings** dialog, change the **Target Runtime** to `win10-x64` and select **Save**.</span></span> <span data-ttu-id="20eac-215">Wählen Sie andernfalls **Abbrechen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-215">Otherwise, select **Cancel**.</span></span>

         1. <span data-ttu-id="20eac-216">Wählen Sie **Veröffentlichen** aus, um Ihre App für 64-Bit-Windows 10-Plattformen zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="20eac-216">Select **Publish** to publish your app for 64-bit Windows 10 platforms.</span></span>

         1. <span data-ttu-id="20eac-217">Arbeiten Sie erneut die vorherigen Schritte durch, um ein Profil für die `osx.10.11-x64`-Plattform zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20eac-217">Follow the previous steps again to create a profile for the `osx.10.11-x64` platform.</span></span> <span data-ttu-id="20eac-218">Der **Zielort** ist *bin\Release\PublishOutput\osx.10.11-x64*, und die **Ziellaufzeit** ist `osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="20eac-218">The **Target Location** is *bin\Release\PublishOutput\osx.10.11-x64*, and the **Target Runtime** is `osx.10.11-x64`.</span></span> <span data-ttu-id="20eac-219">Der Name, den Visual Studio diesem Profil zuweist, ist **FolderProfile2**.</span><span class="sxs-lookup"><span data-stu-id="20eac-219">The name that Visual Studio assigns to this profile is **FolderProfile2**.</span></span>

      <span data-ttu-id="20eac-220">Jedes Ziel enthält den vollständigen Dateisatz (App-Dateien und alle .NET Core-Dateien), der zum Starten Ihrer App erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="20eac-220">Each target location contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="20eac-221">Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="20eac-221">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="20eac-222">Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich.</span><span class="sxs-lookup"><span data-stu-id="20eac-222">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="20eac-223">Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu packen.</span><span class="sxs-lookup"><span data-stu-id="20eac-223">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="20eac-224">Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="20eac-224">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="20eac-225">Stellen Sie die veröffentlichen Dateien in einer beliebigen Weise bereit.</span><span class="sxs-lookup"><span data-stu-id="20eac-225">Deploy the published files in any way you like.</span></span> <span data-ttu-id="20eac-226">Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="20eac-226">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="20eac-227">Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:</span><span class="sxs-lookup"><span data-stu-id="20eac-227">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[<span data-ttu-id="20eac-228">Visual Studio 15.7 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="20eac-228">Visual Studio 15.7 and later</span></span>](#tab/vs157)

<span data-ttu-id="20eac-229">Nachdem Sie das Programm debuggt und getestet haben, erstellen Sie die Dateien, die mit Ihrer App für jede Zielplattform bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20eac-229">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span> <span data-ttu-id="20eac-230">Dafür muss ein separates Profil für jede Zielplattform erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="20eac-230">This involves creating a separate profile for each target platform.</span></span>

<span data-ttu-id="20eac-231">Führen Sie die folgenden Schritte für jede Zielplattform der Anwendung durch:</span><span class="sxs-lookup"><span data-stu-id="20eac-231">For each platform that your application targets, do the following:</span></span>

1. <span data-ttu-id="20eac-232">Erstellen Sie ein Profil für Ihre Zielplattform.</span><span class="sxs-lookup"><span data-stu-id="20eac-232">Create a profile for your target platform.</span></span>

   <span data-ttu-id="20eac-233">Wenn dies das erste Profil ist, das Sie erstellen, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt (nicht auf die Projektmappe), und wählen Sie **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-233">If this is the first profile you've created, right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

   <span data-ttu-id="20eac-234">Wenn Sie bereits ein Profil erstellt haben, klicken Sie mit der rechten Maustaste auf das Projekt, um das Dialogfeld **Veröffentlichen** zu öffnen, sofern dies noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="20eac-234">If you've already created a profile, right-click on the project to open the **Publish** dialog if it isn't already open.</span></span> <span data-ttu-id="20eac-235">Klicken Sie dann auf **Neues Profil**.</span><span class="sxs-lookup"><span data-stu-id="20eac-235">Then select **New Profile**.</span></span>

   <span data-ttu-id="20eac-236">Das Dialogfeld **Veröffentlichungsziel auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="20eac-236">The **Pick a Publish Target** dialog box opens.</span></span>

1. <span data-ttu-id="20eac-237">Wählen Sie aus, wo Ihre Anwendung von Visual Studio veröffentlicht werden soll.</span><span class="sxs-lookup"><span data-stu-id="20eac-237">Select the location where Visual Studio publishes your application.</span></span>

   <span data-ttu-id="20eac-238">Wenn Sie die Anwendung auf einer einzigen Plattform veröffentlichen, können Sie den Standardwert im Textfeld **Ordner auswählen** übernehmen. Die frameworkabhängige Bereitstellung Ihrer Anwendung wird dann im Verzeichnis *\<Projektverzeichnis>\bin\Release\netcoreapp2.1\publish* veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="20eac-238">If you're only publishing to a single platform, you can accept the default value in the **Choose a folder** text box; this publishes the framework-dependent deployment of your application to the *\<project-directory>\bin\Release\netcoreapp2.1\publish* directory.</span></span>

   <span data-ttu-id="20eac-239">Wenn Sie die Anwendung auf mehreren Plattformen veröffentlichen, fügen Sie eine Zeichenfolge an, mit der die Zielplattform identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="20eac-239">If you're publishing to more than one platform, append a string that identifies the target platform.</span></span> <span data-ttu-id="20eac-240">Wenn Sie beispielsweise die Zeichenfolge „linux“ an den Dateipfad anfügen, veröffentlicht Visual Studio die frameworkabhängige Bereitstellung Ihrer Anwendung im Verzeichnis *\<Projektverzeichnis>\bin\Release\netcoreapp2.1\publish\linux*.</span><span class="sxs-lookup"><span data-stu-id="20eac-240">For example, if you append the string "linux" to the file path, Visual Studio publishes the framework-dependent deployment of your application to the *\<project-directory>\bin\Release\netcoreapp2.1\publish\linux* directory.</span></span>

1. <span data-ttu-id="20eac-241">Erstellen Sie das Profil, indem Sie auf das Symbol für die Dropdownliste neben der Schaltfläche **Veröffentlichen** klicken und die Option **Profil erstellen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="20eac-241">Create the profile by selecting the drop-down list icon next to the **Publish** button and selecting **Create Profile**.</span></span> <span data-ttu-id="20eac-242">Klicken Sie anschließend auf **Profil erstellen**, um das Profil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20eac-242">Then select the **Create Profile** button to create the profile.</span></span>

1. <span data-ttu-id="20eac-243">Geben Sie an, dass Sie eine eigenständige Bereitstellung veröffentlichen, und definieren Sie eine Zielplattform für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="20eac-243">Indicate that you are publishing a self-contained deployment and define a platform that your app will target.</span></span>

   1. <span data-ttu-id="20eac-244">Klicken Sie im Dialogfeld **Veröffentlichen** auf den Link **Konfigurieren**, um das Dialogfeld **Profileinstellungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20eac-244">In the **Publish** dialog, select the **Configure** link to open the **Profile Settings** dialog.</span></span>

   1. <span data-ttu-id="20eac-245">Wählen Sie **Eigenständig** im Listenfeld **Bereitstellungsmodus** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-245">Select **Self-contained** in the **Deployment Mode** list box.</span></span>

   1. <span data-ttu-id="20eac-246">Wählen Sie im Listenfeld **Ziellaufzeit** eine der Zielplattformen Ihrer Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-246">In the **Target Runtime** list box, select one of the platforms that your application targets.</span></span>

   1. <span data-ttu-id="20eac-247">Klicken Sie auf **Speichern**, um die Änderungen zu bestätigen und das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="20eac-247">Select **Save** to accept your changes and close the dialog.</span></span>

1. <span data-ttu-id="20eac-248">Benennen Sie Ihr Profil.</span><span class="sxs-lookup"><span data-stu-id="20eac-248">Name your profile.</span></span>

   1. <span data-ttu-id="20eac-249">Klicken Sie auf **Aktionen** > **Profil umbenennen**, um das Profil zu benennen.</span><span class="sxs-lookup"><span data-stu-id="20eac-249">Select **Actions** > **Rename Profile** to name your profile.</span></span>

   2. <span data-ttu-id="20eac-250">Geben Sie dem Profil einen Namen, mit dem die Zielplattform identifiziert werden kann, und klicken Sie dann auf \**Speichern*.</span><span class="sxs-lookup"><span data-stu-id="20eac-250">Assign your profile a name that identifies the target platform, then select \**Save*.</span></span>

<span data-ttu-id="20eac-251">Wiederholen Sie diese Schritte, um die zusätzlichen Zielplattformen Ihrer Anwendung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="20eac-251">Repeat these steps to define any additional target platforms that your application targets.</span></span>

<span data-ttu-id="20eac-252">Da Sie die Profile nun konfiguriert haben, können Sie Ihre Anwendung nun veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="20eac-252">You've configured your profiles and are now ready to publish your app.</span></span> <span data-ttu-id="20eac-253">Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="20eac-253">To do this:</span></span>

   1. <span data-ttu-id="20eac-254">Wenn das Fenster **Veröffentlichen** nicht geöffnet ist, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt (nicht auf die Projektmappe), und wählen Sie **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-254">If the **Publish** window isn't currently open, right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

   2. <span data-ttu-id="20eac-255">Wählen Sie das Profil aus, das Sie veröffentlichen möchten, und klicken Sie dann auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="20eac-255">Select the profile that you'd like to publish, then select **Publish**.</span></span> <span data-ttu-id="20eac-256">Wiederholen Sie diese Schritte für alle zu veröffentlichenden Profile.</span><span class="sxs-lookup"><span data-stu-id="20eac-256">Do this for each profile to be published.</span></span>

   <span data-ttu-id="20eac-257">Jedes Ziel (im Fall unseres Beispiels bin\release\netcoreapp2.1\publish\\*Profilname*) enthält den vollständigen Dateisatz (App-Dateien und alle .NET Core-Dateien), die zum Starten Ihrer App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="20eac-257">Each target location (in the case of our example, bin\release\netcoreapp2.1\publish\\*profile-name* contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="20eac-258">Der Veröffentlichungsprozess gibt zusammen mit den Dateien Ihrer Anwendung eine Programmdatenbankdatei (.pdb) aus, die Debuginformationen über Ihre Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="20eac-258">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="20eac-259">Die Datei ist vornehmlich für das Debuggen von Ausnahmen nützlich.</span><span class="sxs-lookup"><span data-stu-id="20eac-259">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="20eac-260">Sie können sich auch dazu entschließen, sie nicht mit den Dateien Ihrer Anwendung zu packen.</span><span class="sxs-lookup"><span data-stu-id="20eac-260">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="20eac-261">Jedoch sollten Sie sie für den Fall speichern, dass Sie das Releasebuild Ihrer App debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="20eac-261">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="20eac-262">Stellen Sie die veröffentlichen Dateien in einer beliebigen Weise bereit.</span><span class="sxs-lookup"><span data-stu-id="20eac-262">Deploy the published files in any way you like.</span></span> <span data-ttu-id="20eac-263">Sie können sie z.B. in einer ZIP-Datei verpacken, und einen einfachen `copy`-Befehl verwenden, oder sie mit jedem Installationspaket Ihrer Wahl bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="20eac-263">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="20eac-264">Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:</span><span class="sxs-lookup"><span data-stu-id="20eac-264">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="20eac-265">Darüber hinaus erstellt Visual Studio ein separates Veröffentlichungsprofil („\*.pubxml“) für jede Zielplattform.</span><span class="sxs-lookup"><span data-stu-id="20eac-265">In addition, Visual Studio creates a separate publishing profile (\*.pubxml) for each platform that you target.</span></span> <span data-ttu-id="20eac-266">Zum Beispiel wird die Datei für das Linux-Profil („linux.pubxml“) wie folgt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="20eac-266">For example, the file for our linux profile (linux.pubxml) appears as follows:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--
https://go.microsoft.com/fwlink/?LinkID=208121.
-->
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PublishProtocol>FileSystem</PublishProtocol>
    <Configuration>Release</Configuration>
    <Platform>Any CPU</Platform>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <PublishDir>bin\Release\netcoreapp2.1\publish\linux</PublishDir>
    <RuntimeIdentifier>win-x86</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <_IsPortable>false</_IsPortable>
  </PropertyGroup>
</Project>
```

---

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="20eac-267">Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="20eac-267">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="20eac-268">Das Bereitstellen einer eigenständigen Bereitstellung mit einer oder mehreren Drittanbieter-Abhängigkeiten umfasst das Hinzufügen der Drittanbieter-Abhängigkeit:</span><span class="sxs-lookup"><span data-stu-id="20eac-268">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="20eac-269">Die folgenden Schritte müssen noch durchgeführt werden, bevor Sie Ihre App erstellen können:</span><span class="sxs-lookup"><span data-stu-id="20eac-269">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="20eac-270">Verwenden Sie den **NuGet-Paket-Manager**, um einem NuGet-Paket einen Verweis für Ihr Projekt hinzuzufügen. Falls das Paket noch nicht auf Ihrem System verfügbar ist, installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="20eac-270">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="20eac-271">Wählen Sie zum Öffnen des Paket-Managers **Tools** > **NuGet-Paket-Manager** > **NuGet-Pakete für Projektmappe verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="20eac-271">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="20eac-272">Bestätigen Sie, dass Ihre Drittanbieterabhängigkeiten (z. B. `Newtonsoft.Json`) auf Ihrem System installiert sind. Falls dies nicht der Fall ist, installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="20eac-272">Confirm that your third-party dependencies (for example, `Newtonsoft.Json`) are installed on your system and, if they aren't, install them.</span></span> <span data-ttu-id="20eac-273">Die Registerkarte **Installiert** listet NuGet-Pakete auf, die auf Ihrem System installiert sind.</span><span class="sxs-lookup"><span data-stu-id="20eac-273">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="20eac-274">Wenn `Newtonsoft.Json` hier nicht aufgelistet ist, wählen Sie die Registerkarte **Durchsuchen** aus, und geben Sie „Newtonsoft.Json“ in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="20eac-274">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="20eac-275">Wählen Sie `Newtonsoft.Json` aus, und wählen Sie im rechten Bereich Ihre Projekt, bevor Sie auf **Installieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="20eac-275">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="20eac-276">Wenn `Newtonsoft.Json` bereits auf Ihrem System installiert ist, fügen Sie es Ihrem Projekt hinzu, indem Sie Ihr Projekt im rechten Bereich der Registerkarte **Pakete für Projektmappe verwalten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="20eac-276">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="20eac-277">Es folgt die vollständige *CSPROJ*-Datei dieses Projekts:</span><span class="sxs-lookup"><span data-stu-id="20eac-277">The following is the complete *csproj* file for this project:</span></span>

# <a name="visual-studio-156-and-earlier"></a>[<span data-ttu-id="20eac-278">Visual Studio 15.6 und frühere Versionen</span><span class="sxs-lookup"><span data-stu-id="20eac-278">Visual Studio 15.6 and earlier</span></span>](#tab/vs156)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[<span data-ttu-id="20eac-279">Visual Studio 15.7 und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="20eac-279">Visual Studio 15.7 and later</span></span>](#tab/vs157)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

---

<span data-ttu-id="20eac-280">Wenn Sie Ihre Anwendung bereitstellen, sind die Drittanbieter-Abhängigkeiten, die in Ihrer Anwendung verwendet werden, auch in Ihren Anwendungsdateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="20eac-280">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="20eac-281">Drittanbieter-Bibliotheken müssen nicht auf dem System vorhanden sein, auf dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="20eac-281">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="20eac-282">Eine eigenständige Bereitstellung mit einer Drittanbieterbibliothek kann nur auf von dieser Bibliothek unterstützten Plattformen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="20eac-282">You can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="20eac-283">Dies ist ähnlich, als wenn Sie über Drittanbieter-Abhängigkeiten mit nativen Abhängigkeiten in Ihrer Framework-abhängigen Bereitstellung verfügen, wobei die nativen Abhängigkeiten nicht auf der Zielplattform vorhanden sind, es sei denn, sie wurden dort zuvor installiert.</span><span class="sxs-lookup"><span data-stu-id="20eac-283">This is similar to having third-party dependencies with native dependencies in your framework-dependent deployment, where the native dependencies won't exist on the target platform unless they were previously installed there.</span></span>

## <a name="see-also"></a><span data-ttu-id="20eac-284">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20eac-284">See also</span></span>

- [<span data-ttu-id="20eac-285">.NET Core-Anwendungsbereitstellung</span><span class="sxs-lookup"><span data-stu-id="20eac-285">.NET Core Application Deployment</span></span>](index.md)
- [<span data-ttu-id="20eac-286">.NET Core Runtime-ID (RID)-Katalog</span><span class="sxs-lookup"><span data-stu-id="20eac-286">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
