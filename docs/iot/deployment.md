---
title: Bereitstellen von .net-apps auf Raspberry Pi
description: Erfahren Sie, wie Sie .net-apps auf Raspberry Pi bereitstellen.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
ms.openlocfilehash: 4da558e2cdfc283d21f2a5497cb71dc746109614
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96592109"
---
# <a name="deploy-net-apps-to-raspberry-pi"></a><span data-ttu-id="ddd61-103">Bereitstellen von .net-apps auf Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="ddd61-103">Deploy .NET apps to Raspberry Pi</span></span>

<span data-ttu-id="ddd61-104">Die Bereitstellung von .net-apps auf Raspberry Pi ist identisch mit der einer beliebigen anderen Plattform.</span><span class="sxs-lookup"><span data-stu-id="ddd61-104">Deployment of .NET apps to Raspberry Pi is identical to that of any other platform.</span></span> <span data-ttu-id="ddd61-105">Ihre APP kann als *eigenständiger* oder *Framework-abhängiger* Bereitstellungs Modus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ddd61-105">Your app can run as *self-contained* or *framework-dependent* deployment modes.</span></span> <span data-ttu-id="ddd61-106">Jede Strategie bietet Vorteile.</span><span class="sxs-lookup"><span data-stu-id="ddd61-106">There are advantages to each strategy.</span></span> <span data-ttu-id="ddd61-107">Weitere Informationen finden Sie unter [Übersicht über die .NET-Anwendungs Veröffentlichung](../core/deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ddd61-107">For more information, see [.NET application publishing overview](../core/deploying/index.md).</span></span>

## <a name="deploying-a-framework-dependent-app"></a><span data-ttu-id="ddd61-108">Bereitstellen einer Framework-abhängigen App</span><span class="sxs-lookup"><span data-stu-id="ddd61-108">Deploying a framework-dependent app</span></span>

<span data-ttu-id="ddd61-109">Führen Sie die folgenden Schritte aus, um Ihre APP als Framework-abhängige App bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="ddd61-109">To deploy your app as a framework-dependent app, complete the following steps:</span></span>

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. <span data-ttu-id="ddd61-110">Installieren Sie .net auf dem Raspberry Pi mithilfe der [dotnet-install-Skripts](../core/tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="ddd61-110">Install .NET on the Raspberry Pi using the [dotnet-install scripts](../core/tools/dotnet-install-script.md).</span></span> <span data-ttu-id="ddd61-111">Führen Sie die folgenden Schritte von einer bash-Eingabeaufforderung auf dem Raspberry PI (lokal oder SSH) aus:</span><span class="sxs-lookup"><span data-stu-id="ddd61-111">Complete the following steps from a Bash prompt on the Raspberry Pi (local or SSH):</span></span>
    1. <span data-ttu-id="ddd61-112">Führen Sie den folgenden Befehl aus, um .net zu installieren:</span><span class="sxs-lookup"><span data-stu-id="ddd61-112">Run the following command to install .NET:</span></span>

        ```bash
        curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin
        ```

        > [!NOTE]
        > <span data-ttu-id="ddd61-113">So wird die aktuelle Version installiert.</span><span class="sxs-lookup"><span data-stu-id="ddd61-113">This installs the latest version.</span></span> <span data-ttu-id="ddd61-114">Wenn Sie eine bestimmte Version benötigen, fügen Sie am `--version <VERSION>` Ende hinzu, wobei `<VERSION>` die jeweilige Buildversion ist.</span><span class="sxs-lookup"><span data-stu-id="ddd61-114">If you need a specific version, add `--version <VERSION>` to the end, where `<VERSION>` is the specific build version.</span></span>

    1. <span data-ttu-id="ddd61-115">Fügen Sie zum Vereinfachen der Pfad Auflösung eine `DOTNET_ROOT` Umgebungsvariable hinzu, und fügen Sie das *. dotnet* -Verzeichnis `$PATH` mit den folgenden Befehlen hinzu:</span><span class="sxs-lookup"><span data-stu-id="ddd61-115">To simplify path resolution, add a `DOTNET_ROOT` environment variable and add the *.dotnet* directory to `$PATH` with the following commands:</span></span>

        ```bash
        echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
        echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
        source ~/.bashrc
        ```

    1. <span data-ttu-id="ddd61-116">Überprüfen Sie die .net-Installation mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ddd61-116">Verify the .NET installation with the following command:</span></span>

        ```dotnetcli
        dotnet --version
        ```

        <span data-ttu-id="ddd61-117">Vergewissern Sie sich, dass die angezeigte Version der installierten Version entspricht.</span><span class="sxs-lookup"><span data-stu-id="ddd61-117">Verify the displayed version matches the version you installed.</span></span>

1. <span data-ttu-id="ddd61-118">Veröffentlichen Sie die APP wie folgt auf dem Entwicklungs Computer, abhängig von der Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="ddd61-118">Publish the app on the development computer as follows, depending on development environment.</span></span>
    - <span data-ttu-id="ddd61-119">Wenn Sie **Visual Studio** verwenden, stellen Sie [die app in einem lokalen Ordner](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019)bereit.</span><span class="sxs-lookup"><span data-stu-id="ddd61-119">If using **Visual Studio**, [deploy the app to a local folder](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span></span> <span data-ttu-id="ddd61-120">Wählen Sie vor dem Veröffentlichen in der Zusammenfassung Veröffentlichungs Profil die Option **Bearbeiten** aus, und wählen Sie die Registerkarte **Einstellungen** Stellen Sie sicher, dass der **Bereitstellungs Modus** auf *Framework-abhängig* festgelegt ist und die **Ziel Laufzeit** *portabel* ist.</span><span class="sxs-lookup"><span data-stu-id="ddd61-120">Before publishing, select **Edit** in the publish profile summary and select the **Settings** tab. Ensure that **Deployment mode** is set to *Framework-dependent* and **Target runtime** is set to *Portable*.</span></span>
    - <span data-ttu-id="ddd61-121">Wenn Sie die **.net-CLI** verwenden, verwenden Sie den [dotnet Publish](../core/tools/dotnet-publish.md) -Befehl.</span><span class="sxs-lookup"><span data-stu-id="ddd61-121">If using the **.NET CLI**, use the [dotnet publish](../core/tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="ddd61-122">Es sind keine zusätzlichen Argumente erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ddd61-122">No additional arguments are required.</span></span>

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. <span data-ttu-id="ddd61-123">Führen Sie die APP über eine bash-Eingabeaufforderung auf dem Raspberry PI (lokal oder SSH) aus.</span><span class="sxs-lookup"><span data-stu-id="ddd61-123">From a Bash prompt on the Raspberry Pi (local or SSH), run the app.</span></span> <span data-ttu-id="ddd61-124">Legen Sie hierzu den Bereitstellungs Ordner als Aktuelles Verzeichnis fest, und führen Sie den folgenden Befehl aus (wobei *HelloWorld.dll* für den Einstiegspunkt der APP steht):</span><span class="sxs-lookup"><span data-stu-id="ddd61-124">To do this, set the deployment folder as the current directory and execute the following command (where *HelloWorld.dll* is the entry point of the app):</span></span>

    ```dotnetcli
    dotnet HelloWorld.dll
    ```

## <a name="deploying-a-self-contained-app"></a><span data-ttu-id="ddd61-125">Bereitstellen einer eigenständigen App</span><span class="sxs-lookup"><span data-stu-id="ddd61-125">Deploying a self-contained app</span></span>

<span data-ttu-id="ddd61-126">Führen Sie die folgenden Schritte aus, um Ihre APP als eigenständige App bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="ddd61-126">To deploy your app as a self-contained app, complete the following steps:</span></span>

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. <span data-ttu-id="ddd61-127">Veröffentlichen Sie die APP wie folgt auf dem Entwicklungs Computer, abhängig von der Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="ddd61-127">Publish the app on the development computer as follows, depending on development environment.</span></span>
    - <span data-ttu-id="ddd61-128">Wenn Sie **Visual Studio** verwenden, stellen Sie [die app in einem lokalen Ordner](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019)bereit.</span><span class="sxs-lookup"><span data-stu-id="ddd61-128">If using **Visual Studio**, [deploy the app to a local folder](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span></span> <span data-ttu-id="ddd61-129">Wählen Sie vor dem Veröffentlichen in der Zusammenfassung Veröffentlichungs Profil die Option **Bearbeiten** aus, und wählen Sie die Registerkarte **Einstellungen** Stellen Sie sicher, dass der **Bereitstellungs Modus** auf *eigen* ständig festgelegt ist und die **Ziel Laufzeit** auf *Linux-ARM* festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ddd61-129">Before publishing, select **Edit** in the publish profile summary and select the **Settings** tab. Ensure that **Deployment mode** is set to *Self-contained* and **Target runtime** is set to *linux-arm*.</span></span>
    - <span data-ttu-id="ddd61-130">Wenn Sie die **.net-CLI** verwenden, verwenden Sie den [dotnet Publish](../core/tools/dotnet-publish.md) -Befehl mit dem- `-r linux-arm` Argument:</span><span class="sxs-lookup"><span data-stu-id="ddd61-130">If using the **.NET CLI**, use the [dotnet publish](../core/tools/dotnet-publish.md) command with the `-r linux-arm` argument:</span></span>

        ```dotnetcli
        dotnet publish -r linux-arm
        ```

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. <span data-ttu-id="ddd61-131">Führen Sie die APP über eine bash-Eingabeaufforderung auf dem Raspberry PI (lokal oder SSH) aus.</span><span class="sxs-lookup"><span data-stu-id="ddd61-131">From a Bash prompt on the Raspberry Pi (local or SSH), run the app.</span></span> <span data-ttu-id="ddd61-132">Legen Sie zu diesem Zweck das aktuelle Verzeichnis auf den Bereitstellungs Speicherort fest, und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ddd61-132">To do this, set the current directory to the deployment location and complete the following steps:</span></span>
    1. <span data-ttu-id="ddd61-133">Erteilen Sie der ausführbaren Datei die *Ausführungs* Berechtigung (wobei `HelloWorld` der Name der ausführbaren Datei ist).</span><span class="sxs-lookup"><span data-stu-id="ddd61-133">Give the executable *execute* permission (where `HelloWorld` is the executable file name).</span></span>

        ```bash
        chmod +x HelloWorld
        ```

    1. <span data-ttu-id="ddd61-134">Führt die ausführbare Datei aus.</span><span class="sxs-lookup"><span data-stu-id="ddd61-134">Run the executable.</span></span>

        ```bash
        ./HelloWorld
        ```
