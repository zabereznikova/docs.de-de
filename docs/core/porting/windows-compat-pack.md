---
title: 'Portieren auf .NET Core: Verwenden von Windows Compatibility Pack'
description: "Erfahren Sie mehr über Windows Compatibility Pack und die Verwendungsmöglichkeiten, um vorhandenen .NET Framework-Code auf .NET Core zu portieren"
keywords: ".NET, .NET Core, Windows, Kompatibilität"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 3b1fe02aad4f78499158ecb7fa9b8521cb7d992e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="d563a-104">Verwenden von Windows Compatibility Pack</span><span class="sxs-lookup"><span data-stu-id="d563a-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="d563a-105">Zu den häufigsten Problemen, auf die Entwickler beim Portieren von vorhandenem Code zu .NET Core stoßen, zählt die Abhängigkeit von APIs und Technologien, die nur in .NET Framework vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d563a-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="d563a-106">Durch *Windows Compatibility Pack* werden viele dieser Technologien bereitgestellt, sodass das Erstellen von .NET Core-Anwendungen und .NET Standard-Bibliotheken für vorhandenen Code besser umsetzbar ist.</span><span class="sxs-lookup"><span data-stu-id="d563a-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="d563a-107">Bei diesem Paket handelt es sich um eine logische [Erweiterung von .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support), durch die der API-Satz erheblich erhöht wird und vorhandener Code nahezu ohne Änderungen kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="d563a-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="d563a-108">Damit das Versprechen von .NET Standard („der API-Satz, den alle .NET-Implementierungen bereitstellen“) eingehalten werden kann, gilt dies nicht für Technologien, die nicht auf allen Plattformen funktionieren können, z.B. die Registrierung, Windows-Verwaltungsinstrumentation (WMI) oder APIs für die Reflektionsausgabe.</span><span class="sxs-lookup"><span data-stu-id="d563a-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="d563a-109">*Windows Compatibility Pack* basiert auf .NET Standard und stellt Technologien bereit, die nur unter Windows verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d563a-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="d563a-110">Für Kunden, die zu .NET Core wechseln, aber Windows beibehalten möchten, ist dies ein nützlicher erster Schritt.</span><span class="sxs-lookup"><span data-stu-id="d563a-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="d563a-111">In diesem Szenario stellt es bei der Migration eine Hürde ohne architektonische Vorteile dar, wenn Windows-Technologien nicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d563a-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="d563a-112">Paketinhalt</span><span class="sxs-lookup"><span data-stu-id="d563a-112">Package contents</span></span>

<span data-ttu-id="d563a-113">*Windows Compatibility Pack* wird über das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) bereitgestellt werden, und Projekte, die .NET Core oder .NET Standard anzielen, können darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="d563a-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="d563a-114">Es werden über 20.000 APIs aus folgenden Technologiebereichen bereitgestellt, darunter befinden sich sowohl Windows-APIs als auch plattformübergreifende APIs:</span><span class="sxs-lookup"><span data-stu-id="d563a-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="d563a-115">Codepages</span><span class="sxs-lookup"><span data-stu-id="d563a-115">Code Pages</span></span>
* <span data-ttu-id="d563a-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="d563a-116">CodeDom</span></span>
* <span data-ttu-id="d563a-117">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d563a-117">Configuration</span></span>
* <span data-ttu-id="d563a-118">Verzeichnisdienste</span><span class="sxs-lookup"><span data-stu-id="d563a-118">Directory Services</span></span>
* <span data-ttu-id="d563a-119">Zeichnung</span><span class="sxs-lookup"><span data-stu-id="d563a-119">Drawing</span></span>
* <span data-ttu-id="d563a-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="d563a-120">ODBC</span></span>
* <span data-ttu-id="d563a-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d563a-121">Permissions</span></span>
* <span data-ttu-id="d563a-122">Ports</span><span class="sxs-lookup"><span data-stu-id="d563a-122">Ports</span></span>
* <span data-ttu-id="d563a-123">Windows-Zugriffssteuerungslisten (Access Control List, ACL)</span><span class="sxs-lookup"><span data-stu-id="d563a-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="d563a-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="d563a-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="d563a-125">Windows-Kryptografie</span><span class="sxs-lookup"><span data-stu-id="d563a-125">Windows Cryptography</span></span>
* <span data-ttu-id="d563a-126">Windows-EventLog</span><span class="sxs-lookup"><span data-stu-id="d563a-126">Windows EventLog</span></span>
* <span data-ttu-id="d563a-127">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="d563a-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="d563a-128">Windows-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="d563a-128">Windows Performance Counters</span></span>
* <span data-ttu-id="d563a-129">Windows-Registrierung</span><span class="sxs-lookup"><span data-stu-id="d563a-129">Windows Registry</span></span>
* <span data-ttu-id="d563a-130">Zwischenspeichern von Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="d563a-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="d563a-131">Windows-Dienste</span><span class="sxs-lookup"><span data-stu-id="d563a-131">Windows Services</span></span>

<span data-ttu-id="d563a-132">Weitere Informationen finden Sie unter [Windows Compatibility Pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d563a-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="d563a-133">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="d563a-133">Get started</span></span>

1. <span data-ttu-id="d563a-134">Machen Sie sich vor dem Portieren mit dem [Portiervorgang](index.md) vertraut.</span><span class="sxs-lookup"><span data-stu-id="d563a-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="d563a-135">Wenn Sie vorhandenen Code zu .NET Core oder .NET Standard portieren, installieren Sie das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="d563a-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="d563a-136">Wenn Sie Windows beibehalten möchten, können Sie sofort beginnen.</span><span class="sxs-lookup"><span data-stu-id="d563a-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="d563a-137">Wenn Sie die .NET Core-Anwendung oder die .NET Standard-Bibliothek unter Linux oder macOS ausführen möchten, verwenden Sie [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/), um die Verwendungen der APIs zu ermitteln, die nicht plattformübergreifend funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d563a-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="d563a-138">Entfernen Sie die Verwendungen dieser APIs, ersetzen Sie diese durch plattformübergreifende Alternativen, oder schützen Sie diese folgendermaßen mithilfe einer Plattformüberprüfung:</span><span class="sxs-lookup"><span data-stu-id="d563a-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="d563a-139">Eine Demo finden Sie in diesem [Channel 9 video of the Windows Compatibility Pack (Video von Channel 9 über Windows Compatibility Pack)](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="d563a-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

