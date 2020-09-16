---
title: Kompilieren von Anwendungen mit .NET Native
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
ms.openlocfilehash: 7601a6d5e7f49b6d8fc434ef772e2e69740f02cf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543932"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="f6798-102">Kompilieren von Anwendungen mit .NET Native</span><span class="sxs-lookup"><span data-stu-id="f6798-102">Compiling Apps with .NET Native</span></span>

<span data-ttu-id="f6798-103">.Net Native ist eine vorkompilierungs Technologie zum entwickeln und Bereitstellen von Windows-apps, die in Visual Studio 2015 und höheren Versionen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f6798-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="f6798-104">Die in verwaltetem Code (C# oder Visual Basic) geschriebene Releaseversion von Apps mit .NET Framework und Windows 10 als Ziel für systemeigenen Code werden automatisch kompiliert.</span><span class="sxs-lookup"><span data-stu-id="f6798-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>

<span data-ttu-id="f6798-105">In der Regel werden Anwendungen, die auf .NET Framework ausgerichtet sind, in Intermediate Language (IL) kompiliert.</span><span class="sxs-lookup"><span data-stu-id="f6798-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="f6798-106">Zur Laufzeit übersetzt ein JIT-Compiler (Just-In-Time) die IL in systemeigenen Code.</span><span class="sxs-lookup"><span data-stu-id="f6798-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="f6798-107">Im Gegensatz dazu werden von .net Native Windows-apps direkt in systemeigenen Code kompiliert.</span><span class="sxs-lookup"><span data-stu-id="f6798-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="f6798-108">Für Entwickler bedeutet das Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f6798-108">For developers, this means:</span></span>

- <span data-ttu-id="f6798-109">Ihre apps verfügen über die Leistung von System eigenem Code.</span><span class="sxs-lookup"><span data-stu-id="f6798-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="f6798-110">In der Regel ist die Leistung für Code, der zuerst in IL kompiliert und dann vom JIT-Compiler in systemeigenen Code kompiliert wird, übergeordneter.</span><span class="sxs-lookup"><span data-stu-id="f6798-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span>

- <span data-ttu-id="f6798-111">Sie können weiterhin in C# oder Visual Basic programmieren.</span><span class="sxs-lookup"><span data-stu-id="f6798-111">You can continue to program in C# or Visual Basic.</span></span>

- <span data-ttu-id="f6798-112">Sie können weiterhin die vom .NET Framework bereitgestellten Ressourcen nutzen, einschließlich Klassenbibliothek, automatische Speicherverwaltung und Garbage Collection sowie Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="f6798-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>

<span data-ttu-id="f6798-113">Für Benutzer Ihrer Apps bietet .net Native folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="f6798-113">For users of your apps, .NET Native offers these advantages:</span></span>

- <span data-ttu-id="f6798-114">Schnellere Ausführungszeiten für die Mehrzahl der apps und Szenarios.</span><span class="sxs-lookup"><span data-stu-id="f6798-114">Faster execution times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="f6798-115">Schnellere Startzeiten für die Mehrzahl der apps und Szenarios.</span><span class="sxs-lookup"><span data-stu-id="f6798-115">Faster startup times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="f6798-116">Niedrige Kosten für Bereitstellung und Update.</span><span class="sxs-lookup"><span data-stu-id="f6798-116">Low deployment and update costs.</span></span>

- <span data-ttu-id="f6798-117">Optimierte App-Speicherauslastung.</span><span class="sxs-lookup"><span data-stu-id="f6798-117">Optimized app memory usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6798-118">Bei den meisten apps und Szenarien bietet .net Native deutlich schnellere Startzeiten und eine bessere Leistung im Vergleich zu einer in Il kompilierten APP oder zu einem NGen-Image.</span><span class="sxs-lookup"><span data-stu-id="f6798-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="f6798-119">Ihre Ergebnisse können jedoch variieren.</span><span class="sxs-lookup"><span data-stu-id="f6798-119">However, your results may vary.</span></span> <span data-ttu-id="f6798-120">Um sicherzustellen, dass Ihre APP von den Leistungsverbesserungen .net Native profitiert, sollten Sie die Leistung mit der Non-.net nativen Version Ihrer APP vergleichen.</span><span class="sxs-lookup"><span data-stu-id="f6798-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="f6798-121">Weitere Informationen finden Sie unter [Übersicht über die Leistungs Sitzung](/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="f6798-121">For more information, see [Performance Session Overview](/visualstudio/profiling/performance-session-overview).</span></span>

<span data-ttu-id="f6798-122">.Net Native umfasst jedoch mehr als eine Kompilierung in nativem Code.</span><span class="sxs-lookup"><span data-stu-id="f6798-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="f6798-123">Es ändert die Art und Weise, in der .NET Framework-Anwendungen erstellt und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f6798-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="f6798-124">Dies gilt insbesondere für:</span><span class="sxs-lookup"><span data-stu-id="f6798-124">In particular:</span></span>

- <span data-ttu-id="f6798-125">Bei der Vorkompilierung werden erforderlichen Bestandteile von .NET Framework statisch mit Ihrer App verknüpft.</span><span class="sxs-lookup"><span data-stu-id="f6798-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="f6798-126">Dadurch kann die Anwendung mit lokalen Appbibliotheken von .NET Framework ausgeführt werden, und der Compiler kann eine globale Analyse ausführen, um Leistungszuwächse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f6798-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="f6798-127">Daher starten Anwendungen konsistent schneller – sogar nach .NET Framework-Updates.</span><span class="sxs-lookup"><span data-stu-id="f6798-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>

- <span data-ttu-id="f6798-128">Die .net Native-Laufzeit ist für die statische Vorkompilierung optimiert, und in der Mehrzahl der Fälle bietet eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="f6798-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="f6798-129">Gleichzeitig werden aber die zentralen Reflektionsfeatures beibehalten, die Entwickler so produktiv finden.</span><span class="sxs-lookup"><span data-stu-id="f6798-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>

- <span data-ttu-id="f6798-130">.Net Native verwendet das gleiche Back-End wie der C++-Compiler, der für statische vorkompilierungs Szenarios optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="f6798-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>

<span data-ttu-id="f6798-131">.Net Native ist in der Lage, die Leistungsvorteile von C++ für Entwickler von verwaltetem Code zu nutzen, da Sie die gleichen oder ähnliche Tools wie C++ im Hintergrund verwendet, wie in dieser Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f6798-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>

||<span data-ttu-id="f6798-132">.NET systemeigen</span><span class="sxs-lookup"><span data-stu-id="f6798-132">.NET Native</span></span>|<span data-ttu-id="f6798-133">C++</span><span class="sxs-lookup"><span data-stu-id="f6798-133">C++</span></span>|
|-|----------------------------------------------------------------|-----------|
|<span data-ttu-id="f6798-134">Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="f6798-134">Libraries</span></span>|<span data-ttu-id="f6798-135">.NET Framework + Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="f6798-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="f6798-136">Win32 + Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="f6798-136">Win32 + Windows Runtime</span></span>|
|<span data-ttu-id="f6798-137">Compiler</span><span class="sxs-lookup"><span data-stu-id="f6798-137">Compiler</span></span>|<span data-ttu-id="f6798-138">UTC-Optimierungscompiler</span><span class="sxs-lookup"><span data-stu-id="f6798-138">UTC optimizing compiler</span></span>|<span data-ttu-id="f6798-139">UTC-Optimierungscompiler</span><span class="sxs-lookup"><span data-stu-id="f6798-139">UTC optimizing compiler</span></span>|
|<span data-ttu-id="f6798-140">Bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="f6798-140">Deployed</span></span>|<span data-ttu-id="f6798-141">Sofort ausführbare Binärdateien</span><span class="sxs-lookup"><span data-stu-id="f6798-141">Ready-to-run binaries</span></span>|<span data-ttu-id="f6798-142">Sofort ausführbare Binärdateien (ASM)</span><span class="sxs-lookup"><span data-stu-id="f6798-142">Ready-to-run binaries (ASM)</span></span>|
|<span data-ttu-id="f6798-143">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f6798-143">Runtime</span></span>|<span data-ttu-id="f6798-144">MRT.dll (minimale CLR-Laufzeit)</span><span class="sxs-lookup"><span data-stu-id="f6798-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="f6798-145">CRT.dll (C-Laufzeit)</span><span class="sxs-lookup"><span data-stu-id="f6798-145">CRT.dll (C Runtime)</span></span>|

<span data-ttu-id="f6798-146">Für Windows-Apps für Windows 10 laden Sie Binärdateien für die Kompilierung von systemeigenem .NET-Code in App-Paketen (APPX-Dateien) in den Windows Store hoch.</span><span class="sxs-lookup"><span data-stu-id="f6798-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f6798-147">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f6798-147">In This Section</span></span>

<span data-ttu-id="f6798-148">Weitere Informationen zum Entwickeln von Anwendungen mit der .NET Native-Codekompilierung finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f6798-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>

- [<span data-ttu-id="f6798-149">Erste Schritte mit der .NET Native-Codekompilierung: exemplarische Vorgehensweise für Entwickler</span><span class="sxs-lookup"><span data-stu-id="f6798-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](getting-started-with-net-native.md)

- <span data-ttu-id="f6798-150">[.NET Native und Kompilierung:](net-native-and-compilation.md) So kompiliert .NET Native Ihr Projekt in systemeigenen Code.</span><span class="sxs-lookup"><span data-stu-id="f6798-150">[.NET Native and Compilation:](net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>

- [<span data-ttu-id="f6798-151">Reflektion und .NET Native</span><span class="sxs-lookup"><span data-stu-id="f6798-151">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

  - [<span data-ttu-id="f6798-152">APIs, die auf Refelktion beruhen</span><span class="sxs-lookup"><span data-stu-id="f6798-152">APIs That Rely on Reflection</span></span>](apis-that-rely-on-reflection.md)

  - [<span data-ttu-id="f6798-153">Reflektions-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="f6798-153">Reflection API Reference</span></span>](net-native-reflection-api-reference.md)

  - [<span data-ttu-id="f6798-154">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="f6798-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)

- [<span data-ttu-id="f6798-155">Serialisierung und Metadaten</span><span class="sxs-lookup"><span data-stu-id="f6798-155">Serialization and Metadata</span></span>](serialization-and-metadata.md)

- [<span data-ttu-id="f6798-156">Migrieren der Windows Store-App auf .NET Native</span><span class="sxs-lookup"><span data-stu-id="f6798-156">Migrating Your Windows Store App to .NET Native</span></span>](migrating-your-windows-store-app-to-net-native.md)

- [<span data-ttu-id="f6798-157">.NET Native Allgemeine Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f6798-157">.NET Native General Troubleshooting</span></span>](net-native-general-troubleshooting.md)
