---
title: Portieren auf .NET Core - verwenden das Windows Compatibility Pack
description: "Erfahren Sie mehr über das Windows Compatibility Pack und wie können sie vorhandene .NET Framework-Code Portieren zu .NET Core"
keywords: ".NET, .NET Core, Windows, Kompatibilität"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 5094baee77aba4d1e148f807d842a4a2d3405cf7
ms.sourcegitcommit: 86cf9b4c7104485a9870645705b9a1a4b6ca8e2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="b2fc4-104">Verwenden das Windows Compatibility Pack</span><span class="sxs-lookup"><span data-stu-id="b2fc4-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="b2fc4-105">Eine der am häufigsten auftretenden Probleme, die Entwickler stoßen, wenn Sie ihren vorhandenen Code zu .NET Core Portieren ist, dass sie hängen von APIs und -Technologien, die nur in .NET Framework vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="b2fc4-106">Die *Windows Compatibility Pack* wird zum Bereitstellen von viele dieser Technologien so, dass .NET Core-Anwendungen als auch .NET Standardbibliotheken erstellen größerer für vorhandenen Code gültig wird.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="b2fc4-107">Dieses Paket ist eine logische [Erweiterung der Standard 2.0 .NET](../whats-new/index.md#api-changes-and-library-support) , dass erheblich erhöht API-Satz und den vorhandenen Code mit fast keine Änderungen kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="b2fc4-108">Aber um das Versprechen der standardmäßigen .NET halten ("Es ist der Satz von APIs, die alle .NET Implementierungen bereitstellen"), dazu haben nicht Technologien, die auf allen Plattformen, wie z. B. der Registrierung, Windows Management Instrumentation (WMI), nicht funktionieren oder Reflektionsausgabe APIs.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="b2fc4-109">Die *Windows Compatibility Pack* befindet sich auf .NET Standard und bietet Zugriff auf Technologien, die nur Windows sind.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="b2fc4-110">Er ist besonders nützlich für Kunden, die zu .NET Core jedoch Plan auf Windows als ersten Schritt bleiben verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="b2fc4-111">In diesem Szenario ist nicht nur-Windows-Technologien verwenden nur eine Migration Hürde mit 0 (null) architektonische Vorteile.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="b2fc4-112">Paketinhalt</span><span class="sxs-lookup"><span data-stu-id="b2fc4-112">Package contents</span></span>

<span data-ttu-id="b2fc4-113">Die *Windows Compatibility Pack* wird bereitgestellt, über das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) von Projekten für .NET Core "oder" Standard ".NET verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="b2fc4-114">Es stellt ca. 20.000 APIs, die nur für Windows als auch über Plattformen hinweg APIs aus den folgenden Technologiebereichen einschließlich:</span><span class="sxs-lookup"><span data-stu-id="b2fc4-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="b2fc4-115">Codepages</span><span class="sxs-lookup"><span data-stu-id="b2fc4-115">Code Pages</span></span>
* <span data-ttu-id="b2fc4-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="b2fc4-116">CodeDom</span></span>
* <span data-ttu-id="b2fc4-117">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b2fc4-117">Configuration</span></span>
* <span data-ttu-id="b2fc4-118">Verzeichnisdienste</span><span class="sxs-lookup"><span data-stu-id="b2fc4-118">Directory Services</span></span>
* <span data-ttu-id="b2fc4-119">Zeichnen</span><span class="sxs-lookup"><span data-stu-id="b2fc4-119">Drawing</span></span>
* <span data-ttu-id="b2fc4-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="b2fc4-120">ODBC</span></span>
* <span data-ttu-id="b2fc4-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b2fc4-121">Permissions</span></span>
* <span data-ttu-id="b2fc4-122">Ports</span><span class="sxs-lookup"><span data-stu-id="b2fc4-122">Ports</span></span>
* <span data-ttu-id="b2fc4-123">Windows-Zugriffssteuerungslisten (ACL)</span><span class="sxs-lookup"><span data-stu-id="b2fc4-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="b2fc4-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="b2fc4-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="b2fc4-125">Windows-Kryptografie</span><span class="sxs-lookup"><span data-stu-id="b2fc4-125">Windows Cryptography</span></span>
* <span data-ttu-id="b2fc4-126">Windows-Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="b2fc4-126">Windows EventLog</span></span>
* <span data-ttu-id="b2fc4-127">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="b2fc4-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="b2fc4-128">Windows-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="b2fc4-128">Windows Performance Counters</span></span>
* <span data-ttu-id="b2fc4-129">Windows-Registrierung</span><span class="sxs-lookup"><span data-stu-id="b2fc4-129">Windows Registry</span></span>
* <span data-ttu-id="b2fc4-130">Zwischenspeichern von Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="b2fc4-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="b2fc4-131">Windows-Dienste</span><span class="sxs-lookup"><span data-stu-id="b2fc4-131">Windows Services</span></span>

<span data-ttu-id="b2fc4-132">Weitere Informationen finden Sie unter der [des Compatibility Pack Spec](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b2fc4-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="b2fc4-133">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="b2fc4-133">Get started</span></span>

1. <span data-ttu-id="b2fc4-134">Vor dem portieren, sollten Sie einen Blick auf die [Portieren Prozess](index.md).</span><span class="sxs-lookup"><span data-stu-id="b2fc4-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="b2fc4-135">Beim Portieren von vorhandenen Codes zu .NET Core "oder" Standard ".NET installiert das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="b2fc4-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="b2fc4-136">Wenn Sie auf Windows bleiben möchten, sind alle festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="b2fc4-137">Wenn Sie die .NET Core-Anwendung oder .NET Standardbibliothek unter Linux oder MacOS ausführen möchten, verwenden Sie die [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) Verwendung von APIs zu suchen, die plattformübergreifende funktioniert nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="b2fc4-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="b2fc4-138">Entfernen Sie die Verwendung dieser APIs, plattformübergreifende alternativen ersetzt, oder schützen Sie sie mithilfe einer Platform-Überprüfung, wie:</span><span class="sxs-lookup"><span data-stu-id="b2fc4-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="b2fc4-139">Sehen Sie sich für eine Demo der [Channel 9-Video Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="b2fc4-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

