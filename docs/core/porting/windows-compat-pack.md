---
title: Verwenden des Windows Compatibility Pack zum Portieren auf .NET Core
description: Erfahren Sie mehr über Windows Compatibility Pack und die Verwendungsmöglichkeiten, um vorhandenen .NET Framework-Code in .NET Core zu portieren.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 65530987a3cded941b6a292118ed9bfdb6f5b86c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715469"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a><span data-ttu-id="3f1ac-103">Verwenden des Windows Compatibility Pack zum Portieren auf .NET Core</span><span class="sxs-lookup"><span data-stu-id="3f1ac-103">Use the Windows Compatibility Pack to port code to .NET Core</span></span>

<span data-ttu-id="3f1ac-104">Einige der beim Portieren von vorhandenem Code in .NET Core am häufigsten auftretenden Probleme sind Abhängigkeiten von APIs und Technologien, die nur in .NET Framework vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-104">Some of the most common issues found when porting existing code to .NET Core are dependencies on APIs and technologies that are only found in .NET Framework.</span></span> <span data-ttu-id="3f1ac-105">Das *Windows Compatibility Pack* bietet viele dieser Technologien, daher ist es viel einfacher, .NET Core-Anwendungen und .NET Standard-Bibliotheken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-105">The *Windows Compatibility Pack* provides many of these technologies, so it's much easier to build .NET Core applications and .NET Standard libraries.</span></span>

<span data-ttu-id="3f1ac-106">Bei diesem Paket handelt es sich um eine logische [Erweiterung von .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support), durch die der API-Satz erheblich erhöht wird und vorhandener Code nahezu ohne Änderungen kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-106">This package is a logical [extension of .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="3f1ac-107">Damit das Versprechen von .NET Standard („der API-Satz, den alle .NET-Implementierungen bereitstellen“) eingehalten werden kann, enthält das Paket keine Technologien, die nicht auf allen Plattformen funktionieren, z. B. die Registrierung, Windows-Verwaltungsinstrumentation (WMI) oder APIs für die Reflektionsausgabe.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-107">In order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), the pack doesn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="3f1ac-108">Windows Compatibility Pack basiert auf .NET Standard und stellt Technologien bereit, die nur unter Windows verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-108">The Windows Compatibility Pack sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="3f1ac-109">Für Kunden, die zu .NET Core wechseln, aber Windows beibehalten möchten, ist dies ein nützlicher erster Schritt.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-109">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="3f1ac-110">In diesem Szenario ist der Verzicht auf reine Windows-Technologien nur eine Migrationshürde ohne architektonische Vorteile.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-110">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with no architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="3f1ac-111">Paketinhalt</span><span class="sxs-lookup"><span data-stu-id="3f1ac-111">Package contents</span></span>

<span data-ttu-id="3f1ac-112">Windows Compatibility Pack wird über das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) bereitgestellt. Projekte, die .NET Core oder .NET Standard als Ziel verwenden, können darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-112">The Windows Compatibility Pack is provided via the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects that target .NET Core or .NET Standard.</span></span>

<span data-ttu-id="3f1ac-113">Es werden über 20.000 APIs aus folgenden Technologiebereichen bereitgestellt, darunter befinden sich sowohl Windows-APIs als auch plattformübergreifende APIs:</span><span class="sxs-lookup"><span data-stu-id="3f1ac-113">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

- <span data-ttu-id="3f1ac-114">Codepages</span><span class="sxs-lookup"><span data-stu-id="3f1ac-114">Code Pages</span></span>
- <span data-ttu-id="3f1ac-115">CodeDom</span><span class="sxs-lookup"><span data-stu-id="3f1ac-115">CodeDom</span></span>
- <span data-ttu-id="3f1ac-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3f1ac-116">Configuration</span></span>
- <span data-ttu-id="3f1ac-117">Verzeichnisdienste</span><span class="sxs-lookup"><span data-stu-id="3f1ac-117">Directory Services</span></span>
- <span data-ttu-id="3f1ac-118">Zeichnung</span><span class="sxs-lookup"><span data-stu-id="3f1ac-118">Drawing</span></span>
- <span data-ttu-id="3f1ac-119">ODBC</span><span class="sxs-lookup"><span data-stu-id="3f1ac-119">ODBC</span></span>
- <span data-ttu-id="3f1ac-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3f1ac-120">Permissions</span></span>
- <span data-ttu-id="3f1ac-121">Ports</span><span class="sxs-lookup"><span data-stu-id="3f1ac-121">Ports</span></span>
- <span data-ttu-id="3f1ac-122">Windows-Zugriffssteuerungslisten (Access Control List, ACL)</span><span class="sxs-lookup"><span data-stu-id="3f1ac-122">Windows Access Control Lists (ACL)</span></span>
- <span data-ttu-id="3f1ac-123">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="3f1ac-123">Windows Communication Foundation (WCF)</span></span>
- <span data-ttu-id="3f1ac-124">Windows-Kryptografie</span><span class="sxs-lookup"><span data-stu-id="3f1ac-124">Windows Cryptography</span></span>
- <span data-ttu-id="3f1ac-125">Windows-EventLog</span><span class="sxs-lookup"><span data-stu-id="3f1ac-125">Windows EventLog</span></span>
- <span data-ttu-id="3f1ac-126">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="3f1ac-126">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="3f1ac-127">Windows-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="3f1ac-127">Windows Performance Counters</span></span>
- <span data-ttu-id="3f1ac-128">Windows-Registrierung</span><span class="sxs-lookup"><span data-stu-id="3f1ac-128">Windows Registry</span></span>
- <span data-ttu-id="3f1ac-129">Zwischenspeichern von Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="3f1ac-129">Windows Runtime Caching</span></span>
- <span data-ttu-id="3f1ac-130">Windows-Dienste</span><span class="sxs-lookup"><span data-stu-id="3f1ac-130">Windows Services</span></span>

<span data-ttu-id="3f1ac-131">Weitere Informationen finden Sie in den Angaben zum [Windows Compatibility Pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="3f1ac-131">For more information, see the [specification of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="3f1ac-132">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="3f1ac-132">Get started</span></span>

1. <span data-ttu-id="3f1ac-133">Machen Sie sich vor dem Portieren mit dem [Portiervorgang](index.md) vertraut.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-133">Before porting, make sure to take a look at the [Porting process](index.md).</span></span>

2. <span data-ttu-id="3f1ac-134">Wenn Sie vorhandenen Code in .NET Core oder .NET Standard portieren, installieren Sie das NuGet-Paket [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="3f1ac-134">When porting existing code to .NET Core or .NET Standard, install the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

   <span data-ttu-id="3f1ac-135">Wenn Sie Windows beibehalten möchten, können Sie sofort beginnen.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-135">If you want to stay on Windows, you're all set.</span></span>

3. <span data-ttu-id="3f1ac-136">Wenn Sie die .NET Core-Anwendung oder die .NET Standard-Bibliothek unter Linux oder macOS ausführen möchten, verwenden Sie [API Analyzer](../../standard/analyzers/api-analyzer.md), um die Verwendungen der APIs zu ermitteln, die nicht plattformübergreifend funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3f1ac-136">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](../../standard/analyzers/api-analyzer.md) to find usage of APIs that won't work cross-platform.</span></span>

4. <span data-ttu-id="3f1ac-137">Entfernen Sie die Verwendungen dieser APIs, ersetzen Sie diese durch plattformübergreifende Alternativen, oder schützen Sie diese folgendermaßen mithilfe einer Plattformüberprüfung:</span><span class="sxs-lookup"><span data-stu-id="3f1ac-137">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="3f1ac-138">Eine Demo finden Sie in diesem [Channel 9 video of the Windows Compatibility Pack (Video von Channel 9 über Windows Compatibility Pack)](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="3f1ac-138">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>
