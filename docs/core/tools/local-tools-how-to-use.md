---
title: 'Tutorial: Installieren und Verwenden lokaler .NET-Tools'
description: Erfahren Sie, wie Sie ein .NET-Tool als lokales Tool installieren und verwenden.
ms.topic: tutorial
ms.date: 02/12/2020
ms.openlocfilehash: 2cb25443706293b66325d43136afcd3fd886294d
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633880"
---
# <a name="tutorial-install-and-use-a-net-local-tool-using-the-net-cli"></a><span data-ttu-id="42b3d-103">Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="42b3d-103">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>

<span data-ttu-id="42b3d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="42b3d-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="42b3d-105">In diesem Tutorial erfahren Sie, wie ein lokales Tools installiert und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="42b3d-105">This tutorial teaches you how to install and use a local tool.</span></span> <span data-ttu-id="42b3d-106">Sie verwenden ein Tool, das Sie im [ersten Tutorial dieser Reihe](global-tools-how-to-create.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="42b3d-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42b3d-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="42b3d-107">Prerequisites</span></span>

* <span data-ttu-id="42b3d-108">Absolvieren Sie das [erste Tutorial dieser Reihe](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="42b3d-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>
* <span data-ttu-id="42b3d-109">Installieren Sie die .NET Core 2.1-Runtime.</span><span class="sxs-lookup"><span data-stu-id="42b3d-109">Install the .NET Core 2.1 runtime.</span></span>

  <span data-ttu-id="42b3d-110">Für dieses Tutorial installieren und verwenden Sie ein Tool, das für .NET Core 2.1 vorgesehen ist, weshalb diese Runtime auf Ihrem Computer installiert sein muss.</span><span class="sxs-lookup"><span data-stu-id="42b3d-110">For this tutorial you install and use a tool that targets .NET Core 2.1, so you need to have that runtime installed on your machine.</span></span> <span data-ttu-id="42b3d-111">Um die 2.1-Runtime zu installieren, besuchen Sie die [Seite zum Herunterladen von .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1). Den Link zur Installation der Runtime finden Sie in der Spalte **Run apps - Runtime**.</span><span class="sxs-lookup"><span data-stu-id="42b3d-111">To install the 2.1 runtime, go to the [.NET Core 2.1 download page](https://dotnet.microsoft.com/download/dotnet-core/2.1) and find the runtime installation link in the **Run apps - Runtime** column.</span></span>

## <a name="create-a-manifest-file"></a><span data-ttu-id="42b3d-112">So erstellen Sie eine Manifestdatei</span><span class="sxs-lookup"><span data-stu-id="42b3d-112">Create a manifest file</span></span>

<span data-ttu-id="42b3d-113">Um ein Tool nur für den lokalen Zugriff (für das aktuelle Verzeichnis und Unterverzeichnisse) zu installieren, muss es der Manifestdatei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="42b3d-113">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a manifest file.</span></span>

<span data-ttu-id="42b3d-114">Navigieren Sie im Ordner *microsoft.botsay* einen Schritt zurück zum Ordner *Repository*:</span><span class="sxs-lookup"><span data-stu-id="42b3d-114">From the *microsoft.botsay* folder, navigate up one level to the *repository* folder:</span></span>

```console
cd ..
```

<span data-ttu-id="42b3d-115">Erstellen Sie eine Manifestdatei, indem Sie den Befehl [dotnet new](dotnet-new.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="42b3d-115">Create a manifest file by running the [dotnet new](dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="42b3d-116">Die Ausgabe gibt an, dass die Datei erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="42b3d-116">The output indicates successful creation of the file.</span></span>

```console
The template "Dotnet local tool manifest file" was created successfully.
```

<span data-ttu-id="42b3d-117">Die Datei *.config/dotnet-tools.json* enthält noch keine Tools:</span><span class="sxs-lookup"><span data-stu-id="42b3d-117">The *.config/dotnet-tools.json* file has no tools in it yet:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="42b3d-118">Die in einer Manifestdatei aufgeführten Tools stehen im aktuellen Verzeichnis und in dessen Unterverzeichnissen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="42b3d-118">The tools listed in a manifest file are available to the current directory and subdirectories.</span></span> <span data-ttu-id="42b3d-119">Das aktuelle Verzeichnis ist dasjenige, das das Verzeichnis *. config* mit der Manifestdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="42b3d-119">The current directory is the one that contains the *.config* directory with the manifest file.</span></span>

<span data-ttu-id="42b3d-120">Wenn Sie einen CLI-Befehl verwenden, der ein lokales Tool referenziert, sucht das SDK im aktuellen Verzeichnis und in übergeordneten Verzeichnissen nach einer Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="42b3d-120">When you use a CLI command that refers to a local tool, the SDK searches for a manifest file in the current directory and parent directories.</span></span> <span data-ttu-id="42b3d-121">Wenn eine Manifestdatei gefunden wird, die Datei aber nicht das referenzierte Tool enthält, wird die Suche in übergeordneten Verzeichnissen fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="42b3d-121">If it finds a manifest file, but the file doesn't include the referenced tool, it continues the search up through parent directories.</span></span> <span data-ttu-id="42b3d-122">Die Suche endet, wenn das referenzierte Tool oder eine Manifestdatei gefunden wird, bei der `isRoot` auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="42b3d-122">The search ends when it finds the referenced tool or it finds a manifest file with `isRoot` set to `true`.</span></span>

## <a name="install-botsay-as-a-local-tool"></a><span data-ttu-id="42b3d-123">Installieren von botsay als lokales Tool</span><span class="sxs-lookup"><span data-stu-id="42b3d-123">Install botsay as a local tool</span></span>

<span data-ttu-id="42b3d-124">Installieren Sie das Tool aus dem Paket, das Sie im ersten Tutorial erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="42b3d-124">Install the tool from the package that you created in the first tutorial:</span></span>

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

<span data-ttu-id="42b3d-125">Dieser Befehl fügt das Tool der Manifestdatei hinzu, die Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="42b3d-125">This command adds the tool to the manifest file that you created in the preceding step.</span></span> <span data-ttu-id="42b3d-126">Die Befehlsausgabe zeigt, in welcher Manifestdatei sich das neu installierte Tool befindet:</span><span class="sxs-lookup"><span data-stu-id="42b3d-126">The command output shows which manifest file the newly installed tool is in:</span></span>

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

<span data-ttu-id="42b3d-127">Die Datei *.config/dotnet-tools.json* enthält nun ein Tool:</span><span class="sxs-lookup"><span data-stu-id="42b3d-127">The *.config/dotnet-tools.json* file now has one tool:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "microsoft.botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a><span data-ttu-id="42b3d-128">Verwenden des Tools</span><span class="sxs-lookup"><span data-stu-id="42b3d-128">Use the tool</span></span>

<span data-ttu-id="42b3d-129">Rufen Sie das Tool auf, indem Sie im Ordner *repository* den Befehl `dotnet tool run` ausführen:</span><span class="sxs-lookup"><span data-stu-id="42b3d-129">Invoke the tool by running the `dotnet tool run` command from the *repository* folder:</span></span>

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a><span data-ttu-id="42b3d-130">Wiederherstellen eines von anderen installierten lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="42b3d-130">Restore a local tool installed by others</span></span>

<span data-ttu-id="42b3d-131">Normalerweise installieren Sie ein lokales Tool im Stammverzeichnis des Repositorys.</span><span class="sxs-lookup"><span data-stu-id="42b3d-131">You typically install a local tool in the root directory of the repository.</span></span> <span data-ttu-id="42b3d-132">Nach Einchecken der Manifestdatei im Repository können andere Entwickler die neueste Manifestdatei erhalten.</span><span class="sxs-lookup"><span data-stu-id="42b3d-132">After you check in the manifest file to the repository, other developers can get the latest manifest file.</span></span> <span data-ttu-id="42b3d-133">Um alle in der Manifestdatei aufgeführten Tools zu installieren, können sie einen einzelnen `dotnet tool restore`-Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="42b3d-133">To install all of the tools listed in the manifest file, they can run a single `dotnet tool restore` command.</span></span>

1. <span data-ttu-id="42b3d-134">Öffnen Sie die Datei *.config/dotnet-tools.json*, und ersetzen Sie den Inhalt durch den folgenden JSON-Code:</span><span class="sxs-lookup"><span data-stu-id="42b3d-134">Open the *.config/dotnet-tools.json* file, and replace the contents with the following JSON:</span></span>

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "microsoft.botsay": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. <span data-ttu-id="42b3d-135">Ersetzen Sie `<name>` durch den Namen, den Sie bei der Erstellung des Projekts verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="42b3d-135">Replace `<name>` with the name you used to create the project.</span></span>

1. <span data-ttu-id="42b3d-136">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="42b3d-136">Save your changes.</span></span>

   <span data-ttu-id="42b3d-137">Diese Änderung entspricht dem Abrufen der neuesten Version aus dem Repository, nachdem eine andere Person das Paket `dotnetsay` im Projektverzeichnis installiert hat.</span><span class="sxs-lookup"><span data-stu-id="42b3d-137">Making this change is the same as getting the latest version from the repository after someone else installed the package `dotnetsay` for the project directory.</span></span>

1. <span data-ttu-id="42b3d-138">Führen Sie den Befehl `dotnet tool restore` aus.</span><span class="sxs-lookup"><span data-stu-id="42b3d-138">Run the `dotnet tool restore` command.</span></span>

   ```dotnetcli
   dotnet tool restore
   ```

   <span data-ttu-id="42b3d-139">Der Befehl erzeugt eine Ausgabe ähnlich dem folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="42b3d-139">The command produces output like the following example:</span></span>

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. <span data-ttu-id="42b3d-140">Überprüfen Sie, ob die Tools verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="42b3d-140">Verify that the tools are available:</span></span>

   ```dotnetcli
   dotnet tool list
   ```

   <span data-ttu-id="42b3d-141">Die Ausgabe ist eine Liste von Paketen und Befehlen, ähnlich wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="42b3d-141">The output is a list of packages and commands, similar to the following example:</span></span>

   ```console
   Package Id      Version      Commands       Manifest
   --------------------------------------------------------------------------------------------
   microsoft.botsay 1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay        2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. <span data-ttu-id="42b3d-142">Testen Sie die Tools:</span><span class="sxs-lookup"><span data-stu-id="42b3d-142">Test the tools:</span></span>

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a><span data-ttu-id="42b3d-143">Aktualisieren eines lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="42b3d-143">Update a local tool</span></span>

<span data-ttu-id="42b3d-144">Die installierte Version des lokalen Tools `dotnetsay` ist 2.1.3.</span><span class="sxs-lookup"><span data-stu-id="42b3d-144">The installed version of local tool `dotnetsay` is 2.1.3.</span></span>  <span data-ttu-id="42b3d-145">Die neueste Version ist 2.1.4.</span><span class="sxs-lookup"><span data-stu-id="42b3d-145">The latest version is 2.1.4.</span></span> <span data-ttu-id="42b3d-146">Verwenden Sie den Befehl [dotnet tool update](dotnet-tool-update.md), um das Tool auf die neueste Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="42b3d-146">Use the [dotnet tool update](dotnet-tool-update.md) command to update the tool to the latest version.</span></span>

```dotnetcli
dotnet tool update dotnetsay
```

<span data-ttu-id="42b3d-147">Die Ausgabe gibt die neue Versionsnummer an:</span><span class="sxs-lookup"><span data-stu-id="42b3d-147">The output indicates the new version number:</span></span>

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

<span data-ttu-id="42b3d-148">Der Aktualisierungsbefehl findet die erste Manifestdatei, die die Paket-ID enthält, und aktualisiert sie.</span><span class="sxs-lookup"><span data-stu-id="42b3d-148">The update command finds the first manifest file that contains the package ID and updates it.</span></span> <span data-ttu-id="42b3d-149">Wenn es in keiner Manifestdatei im Geltungsbereich der Suche eine solche Paket-ID gibt, fügt das SDK der nächstgelegenen Manifestdatei einen neuen Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="42b3d-149">If there is no such package ID in any manifest file that is in the scope of the search, the SDK adds a new entry to the closest manifest file.</span></span> <span data-ttu-id="42b3d-150">Der Suchbereich erstreckt sich über übergeordnete Verzeichnisse, bis eine Manifestdatei mit `isRoot = true` gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="42b3d-150">The search scope is up through parent directories until a manifest file with `isRoot = true` is found.</span></span>

## <a name="remove-local-tools"></a><span data-ttu-id="42b3d-151">Entfernen lokaler Tools</span><span class="sxs-lookup"><span data-stu-id="42b3d-151">Remove local tools</span></span>

<span data-ttu-id="42b3d-152">Entfernen Sie die installierten Tools, indem Sie den Befehl [dotnet tool uninstall](dotnet-tool-uninstall.md) ausführen:</span><span class="sxs-lookup"><span data-stu-id="42b3d-152">Remove the installed tools by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a><span data-ttu-id="42b3d-153">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="42b3d-153">Troubleshoot</span></span>

<span data-ttu-id="42b3d-154">Falls im Verlauf des Tutorials eine Fehlermeldung angezeigt wird, finden Sie unter [Behandlung von Problemen bei der Nutzung von .NET-Tools](troubleshoot-usage-issues.md) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="42b3d-154">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="42b3d-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42b3d-155">See also</span></span>

<span data-ttu-id="42b3d-156">Weitere Informationen finden Sie unter [.NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="42b3d-156">For more information, see [.NET Core tools](global-tools.md)</span></span>
