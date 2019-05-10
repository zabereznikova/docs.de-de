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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3c845cefad451c608f5c095e4941c3368dc9975
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650546"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="8db79-102">Kompilieren von Anwendungen mit .NET Native</span><span class="sxs-lookup"><span data-stu-id="8db79-102">Compiling Apps with .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="8db79-103">ist eine vorkompilierungstechnologie für die Erstellung und Bereitstellung von Windows-apps, die mit Visual Studio 2015 und späteren Versionen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="8db79-103">is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="8db79-104">Die in verwaltetem Code (C# oder Visual Basic) geschriebene Releaseversion von Apps mit .NET Framework und Windows 10 als Ziel für systemeigenen Code werden automatisch kompiliert.</span><span class="sxs-lookup"><span data-stu-id="8db79-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="8db79-105">In der Regel werden Anwendungen, die auf .NET Framework ausgerichtet sind, in Intermediate Language (IL) kompiliert.</span><span class="sxs-lookup"><span data-stu-id="8db79-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="8db79-106">Zur Laufzeit übersetzt ein JIT-Compiler (Just-In-Time) die IL in systemeigenen Code.</span><span class="sxs-lookup"><span data-stu-id="8db79-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="8db79-107">Im Gegensatz dazu kompiliert [!INCLUDE[net_native](../../../includes/net-native-md.md)] Windows-Apps direkt in systemeigenen Code.</span><span class="sxs-lookup"><span data-stu-id="8db79-107">In contrast, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiles Windows apps directly to native code.</span></span> <span data-ttu-id="8db79-108">Für Entwickler bedeutet das Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8db79-108">For developers, this means:</span></span>  
  
- <span data-ttu-id="8db79-109">Ihre apps bieten die Leistungsfähigkeit von systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="8db79-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="8db79-110">In der Regel werden besser als Code, die zuerst in der IL kompiliert und dann vom JIT-Compiler in nativen Code kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="8db79-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
- <span data-ttu-id="8db79-111">Sie können weiterhin in C# oder Visual Basic programmieren.</span><span class="sxs-lookup"><span data-stu-id="8db79-111">You can continue to program in C# or Visual Basic.</span></span>  
  
- <span data-ttu-id="8db79-112">Sie können weiterhin die vom .NET Framework bereitgestellten Ressourcen nutzen, einschließlich Klassenbibliothek, automatische Speicherverwaltung und Garbage Collection sowie Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="8db79-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="8db79-113">Für Benutzer Ihrer Anwendungen bietet [!INCLUDE[net_native](../../../includes/net-native-md.md)] die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="8db79-113">For users of your apps, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offers these advantages:</span></span>  
  
- <span data-ttu-id="8db79-114">Für die Mehrzahl der App- und szenariotypen, schnellere Ausführungszeiten.</span><span class="sxs-lookup"><span data-stu-id="8db79-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
- <span data-ttu-id="8db79-115">Für die Mehrzahl der App- und szenariotypen, schnellere Startzeiten.</span><span class="sxs-lookup"><span data-stu-id="8db79-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
- <span data-ttu-id="8db79-116">Niedrige Kosten für Bereitstellung und Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="8db79-116">Low deployment and update costs.</span></span>  
  
- <span data-ttu-id="8db79-117">Optimierte anwendungsspeichernutzung.</span><span class="sxs-lookup"><span data-stu-id="8db79-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="8db79-118">Für die überwiegende Mehrheit der App- und szenariotypen bietet .NET Native, deutlich schnellere Startzeiten und eine bessere Leistung im Vergleich zu einer app, die kompilierte IL oder ein NGEN-Image.</span><span class="sxs-lookup"><span data-stu-id="8db79-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="8db79-119">Allerdings können die Ergebnisse variieren.</span><span class="sxs-lookup"><span data-stu-id="8db79-119">However, your results may vary.</span></span> <span data-ttu-id="8db79-120">Um sicherzustellen, dass Ihre app über die leistungsverbesserungen von .NET Native profitiert hat, sollten Sie die Leistung, der ohne .NET Native-Version Ihrer App vergleichen.</span><span class="sxs-lookup"><span data-stu-id="8db79-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="8db79-121">Weitere Informationen finden Sie unter [Übersicht über Leistungssitzungen](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="8db79-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="8db79-122">Aber [!INCLUDE[net_native](../../../includes/net-native-md.md)] umfasst mehr als nur eine Kompilierung in systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="8db79-122">But [!INCLUDE[net_native](../../../includes/net-native-md.md)] involves more than a compilation to native code.</span></span> <span data-ttu-id="8db79-123">Es ändert die Art und Weise, in der .NET Framework-Anwendungen erstellt und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8db79-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="8db79-124">Insbesondere:</span><span class="sxs-lookup"><span data-stu-id="8db79-124">In particular:</span></span>  
  
- <span data-ttu-id="8db79-125">Bei der Vorkompilierung werden erforderlichen Bestandteile von .NET Framework statisch mit Ihrer App verknüpft.</span><span class="sxs-lookup"><span data-stu-id="8db79-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="8db79-126">Dadurch kann die Anwendung mit lokalen Appbibliotheken von .NET Framework ausgeführt werden, und der Compiler kann eine globale Analyse ausführen, um Leistungszuwächse bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8db79-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="8db79-127">Daher starten Anwendungen konsistent schneller – sogar nach .NET Framework-Updates.</span><span class="sxs-lookup"><span data-stu-id="8db79-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
- <span data-ttu-id="8db79-128">Die [!INCLUDE[net_native](../../../includes/net-native-md.md)] Runtime ist für die statische Vorkompilierung optimiert und bietet eine bessere Leistung in der Mehrzahl der Fälle.</span><span class="sxs-lookup"><span data-stu-id="8db79-128">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="8db79-129">Gleichzeitig werden aber die zentralen Reflektionsfeatures beibehalten, die Entwickler so produktiv finden.</span><span class="sxs-lookup"><span data-stu-id="8db79-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
- [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="8db79-130">verwendet das gleiche Back-End wie der C++-Compiler, der für statische Vorkompilierungsszenarios optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="8db79-130">uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="8db79-131">kann die Leistungsvorteile von C++ auf Entwickler von verwaltetem Code übertragen, da im Endeffekt die gleichen oder ähnliche Tools wie für C++ verwendet werden, wie in dieser Tabelle gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8db79-131">is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|<span data-ttu-id="8db79-132">C++</span><span class="sxs-lookup"><span data-stu-id="8db79-132">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="8db79-133">Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="8db79-133">Libraries</span></span>|<span data-ttu-id="8db79-134">.NET Framework + Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="8db79-134">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="8db79-135">Win32 + Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="8db79-135">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="8db79-136">Compiler</span><span class="sxs-lookup"><span data-stu-id="8db79-136">Compiler</span></span>|<span data-ttu-id="8db79-137">UTC-Optimierungscompiler</span><span class="sxs-lookup"><span data-stu-id="8db79-137">UTC optimizing compiler</span></span>|<span data-ttu-id="8db79-138">UTC-Optimierungscompiler</span><span class="sxs-lookup"><span data-stu-id="8db79-138">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="8db79-139">Bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="8db79-139">Deployed</span></span>|<span data-ttu-id="8db79-140">Sofort ausführbare Binärdateien</span><span class="sxs-lookup"><span data-stu-id="8db79-140">Ready-to-run binaries</span></span>|<span data-ttu-id="8db79-141">Sofort ausführbare Binärdateien (ASM)</span><span class="sxs-lookup"><span data-stu-id="8db79-141">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="8db79-142">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8db79-142">Runtime</span></span>|<span data-ttu-id="8db79-143">MRT.dll (minimale CLR-Laufzeit)</span><span class="sxs-lookup"><span data-stu-id="8db79-143">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="8db79-144">CRT.dll (C-Laufzeit)</span><span class="sxs-lookup"><span data-stu-id="8db79-144">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="8db79-145">Für Windows-Apps für Windows 10 laden Sie Binärdateien für die Kompilierung von systemeigenem .NET-Code in App-Paketen (APPX-Dateien) in den Windows Store hoch.</span><span class="sxs-lookup"><span data-stu-id="8db79-145">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8db79-146">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8db79-146">In This Section</span></span>  
 <span data-ttu-id="8db79-147">Weitere Informationen zum Entwickeln von Anwendungen mit der .NET Native-Codekompilierung finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="8db79-147">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
- [<span data-ttu-id="8db79-148">Erste Schritte mit .NET Native-Codekompilierung: Die exemplarische Vorgehensweise für Entwickler</span><span class="sxs-lookup"><span data-stu-id="8db79-148">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- <span data-ttu-id="8db79-149">[.NET Native und Kompilierung:](../../../docs/framework/net-native/net-native-and-compilation.md) Wie .NET Native Ihr Projekt in systemeigenen Code kompiliert.</span><span class="sxs-lookup"><span data-stu-id="8db79-149">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
- [<span data-ttu-id="8db79-150">Reflection and .NET Native (Reflektion und .NET Native)</span><span class="sxs-lookup"><span data-stu-id="8db79-150">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [<span data-ttu-id="8db79-151">APIs That Rely on Reflection (APIs, die die Reflektion benötigen)</span><span class="sxs-lookup"><span data-stu-id="8db79-151">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [<span data-ttu-id="8db79-152">Reflektions-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="8db79-152">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [<span data-ttu-id="8db79-153">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="8db79-153">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- [<span data-ttu-id="8db79-154">Serialization and Metadata (Serialisierung und Metadaten)</span><span class="sxs-lookup"><span data-stu-id="8db79-154">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
- [<span data-ttu-id="8db79-155">Migrating Your Windows Store App to .NET Native (Migrieren der Windows Store-App auf .NET Native)</span><span class="sxs-lookup"><span data-stu-id="8db79-155">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
- [<span data-ttu-id="8db79-156">.NET Native General Troubleshooting (Allgemeine Problembehandlung für .NET Native)</span><span class="sxs-lookup"><span data-stu-id="8db79-156">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
