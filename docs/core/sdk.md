---
title: ".NET Core SDK – Übersicht"
description: "Erfahren Sie mehr über das .NET Core SDK, das ein Set von Bibliotheken und Tools zum Erstellen von .NET Core-Projekten ist."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 26bc9822-e42b-48ec-b0d6-499dc604add7
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8f3d0f5b3bccdd1ca25fa1202c2c727e402fe668
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-sdk-overview"></a><span data-ttu-id="72655-104">.NET Core SDK – Übersicht</span><span class="sxs-lookup"><span data-stu-id="72655-104">.NET Core SDK Overview</span></span> 

## <a name="introduction"></a><span data-ttu-id="72655-105">Einführung</span><span class="sxs-lookup"><span data-stu-id="72655-105">Introduction</span></span>
<span data-ttu-id="72655-106">.NET Core Software Development Kit (SDK) ist eine Sammlung von Bibliotheken und Tools, mit der Entwickler .NET Core-Anwendungen und -Bibliotheken erstellen können.</span><span class="sxs-lookup"><span data-stu-id="72655-106">.NET Core Software Development Kit (SDK) is a set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="72655-107">Dieses Paket wird von den meisten Entwicklern erworben.</span><span class="sxs-lookup"><span data-stu-id="72655-107">This is the package that developers will most likely acquire.</span></span> 

<span data-ttu-id="72655-108">Es enthält die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="72655-108">It contains the following components:</span></span>

1. <span data-ttu-id="72655-109">Die .NET Core-Befehlszeilentools zum Erstellen von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="72655-109">The .NET Core Command Line Tools that are used to build applications</span></span>
2. <span data-ttu-id="72655-110">.NET Core (Bibliotheken und Runtime) zum Erstellen sowie zum Ausführen von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="72655-110">.NET Core (libraries and runtime) that allow applications to both be built and run</span></span>
3. <span data-ttu-id="72655-111">Der `dotnet`-Treiber für das Ausführen der [CLI-Befehle](tools/index.md) sowie von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="72655-111">The `dotnet` driver for running the [CLI commands](tools/index.md) as well as running applications</span></span>


## <a name="acquiring-the-net-core-sdk"></a><span data-ttu-id="72655-112">.NET Core SDK erwerben</span><span class="sxs-lookup"><span data-stu-id="72655-112">Acquiring the .NET Core SDK</span></span>
<span data-ttu-id="72655-113">Wie bei allen Tools ist der erste Schritt, diese auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="72655-113">As with any tooling, the first thing is to get the tools to your machine.</span></span> <span data-ttu-id="72655-114">Je nach Szenario können Sie entweder den nativen Installer oder das Shellskript verwenden, um das SDK zu installieren.</span><span class="sxs-lookup"><span data-stu-id="72655-114">Depending on your scenario, you can either use the native installers to install the SDK or use the installation shell script.</span></span>

<span data-ttu-id="72655-115">Der native Installer ist in erster Linie für Entwicklercomputer vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="72655-115">The native installers are primarily meant for developer's machines.</span></span> <span data-ttu-id="72655-116">Das SDK wird mithilfe des nativen Installationsmechanismus der jeweils unterstützten Plattform verteilt, z.B. Debian-Pakete unter Ubuntu oder MSI-Bündel unter Windows.</span><span class="sxs-lookup"><span data-stu-id="72655-116">The SDK is distributed using each supported platform's native install mechanism, for instance DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="72655-117">Diese Installer installieren und richten die Umgebung je nach Bedarf des Nutzers ein, sodass das SDK sofort nach der Installation genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="72655-117">These installers will install and set up the environment as needed for the user to use the SDK immediately after the install.</span></span> <span data-ttu-id="72655-118">Jedoch benötigen sie auch Administratorrechte auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="72655-118">However, they also require administrative privileges on the machine.</span></span> <span data-ttu-id="72655-119">Die Installationsanweisungen finden Sie im [.NET Core-Installationshandbuch](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="72655-119">You can view the installation instructions on the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>

<span data-ttu-id="72655-120">Installationsskripts hingegen erfordern keine Administratorrechte.</span><span class="sxs-lookup"><span data-stu-id="72655-120">Install scripts, on the other hand, do not require administrative privileges.</span></span> <span data-ttu-id="72655-121">Allerdings installieren diese auch keine erforderlichen Komponenten auf dem Computer, sodass Sie alle erforderlichen Komponenten manuell installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="72655-121">However, they will also not install any prerequisites on the machine; you need to install all of the prerequisites manually.</span></span> <span data-ttu-id="72655-122">Die Skripts werden hauptsächlich für das Einrichten von Buildservern verwendet oder in dem Fall, dass Sie die Tools ohne Administratorrechte installieren möchten (beachten Sie hierzu die oben genannten Einschränkungen hinsichtlich der erforderlichen Komponenten).</span><span class="sxs-lookup"><span data-stu-id="72655-122">The scripts are meant mostly for setting up build servers or when you wish to install the tools without admin privileges (do note the prerequisites caveat above).</span></span> <span data-ttu-id="72655-123">Weitere Informationen finden Sie unter [dotnet-install scripts reference (Referenz zu dotnet-Installationsskripts)](tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="72655-123">You can find more information on the [install script reference topic](tools/dotnet-install-script.md).</span></span> <span data-ttu-id="72655-124">Informationen dazu, wie Sie ein SDK auf Ihrem CI-Buildserver einrichten können, finden Sie in dem Dokument [Using .NET Core SDK and tools in Continuous Integration (CI) (Verwendung von .NET Core-SDK und Tools in der Fortlaufenden Integration (CI))](tools/using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="72655-124">If you are interested in how to set up SDK on your CI build server you can take a look at the [SDK with CI servers](tools/using-ci-with-cli.md) document.</span></span> 

<span data-ttu-id="72655-125">Das SDK wird standardmäßig parallel installiert (SxS).</span><span class="sxs-lookup"><span data-stu-id="72655-125">By default, the SDK will install in a "side-by-side" (SxS) manner.</span></span> <span data-ttu-id="72655-126">Das bedeutet, dass auf einem Computer jederzeit mehrere Versionen der CLI-Tools nebeneinander verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="72655-126">This means that multiple versions of the CLI tools can coexist at any given time on a single machine.</span></span> <span data-ttu-id="72655-127">Ausführlichere Erklärungen dazu, wie die korrekte Version verwendet wird, finden Sie auf der Seite „.NET Core Command-Line Interface Tools“ (Tools für die .NET Core-Befehlszeilenschnittstelle) im Abschnitt [Driver (Treiber)](tools/index.md#driver).</span><span class="sxs-lookup"><span data-stu-id="72655-127">How the correct version gets used is explained in more detail in the [driver section](tools/index.md#driver) of .NET Core Command Line Tools topic.</span></span>

