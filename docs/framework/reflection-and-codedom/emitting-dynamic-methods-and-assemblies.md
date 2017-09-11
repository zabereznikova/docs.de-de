---
title: Ausgeben von dynamischen Methoden und Assemblys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.assetid: 8e8e2631-62fd-40e7-a8ee-0039b06749bc
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c28a5b71a93ea5159adc73316771d490dbe0db87
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="b65a0-102">Ausgeben von dynamischen Methoden und Assemblys</span><span class="sxs-lookup"><span data-stu-id="b65a0-102">Emitting Dynamic Methods and Assemblies</span></span>
<span data-ttu-id="b65a0-103">In diesem Abschnitt wird ein Satz verwalteter Typen im <xref:System.Reflection.Emit>-Namespace beschrieben, mit denen ein Compiler oder ein Tool zur Laufzeit Metadaten und Microsoft Intermediate Language (MSIL) ausgeben und optional eine übertragbare ausführbare Datei (PE-Datei) auf dem Datenträger generieren kann.</span><span class="sxs-lookup"><span data-stu-id="b65a0-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="b65a0-104">Dieser Namespace wird primär von Skriptmodulen und Compilern verwendet.</span><span class="sxs-lookup"><span data-stu-id="b65a0-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="b65a0-105">Die vom <xref:System.Reflection.Emit>-Namespace bereitgestellte Funktionalität wird in diesem Abschnitt als Reflektionsausgabe bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b65a0-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
 <span data-ttu-id="b65a0-106">Die Reflektionsausgabe bietet die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="b65a0-106">Reflection emit provides the following capabilities:</span></span>  
  
-   <span data-ttu-id="b65a0-107">Sie können mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse einfache globale Methoden zur Laufzeit definieren und diese mithilfe von Delegaten ausführen.</span><span class="sxs-lookup"><span data-stu-id="b65a0-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
-   <span data-ttu-id="b65a0-108">Sie können Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.</span><span class="sxs-lookup"><span data-stu-id="b65a0-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="b65a0-109">Sie können Assemblys zur Laufzeit definieren, sie ausführen und dann entladen und der Garbage Collection ermöglichen, die zugehörigen Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="b65a0-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
-   <span data-ttu-id="b65a0-110">Sie können Module in neuen Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.</span><span class="sxs-lookup"><span data-stu-id="b65a0-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="b65a0-111">Sie können Typen in Modulen zur Laufzeit definieren, Instanzen dieser Typen erstellen und deren Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b65a0-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
-   <span data-ttu-id="b65a0-112">Sie können symbolische Informationen für definierte Module angeben, die von Tools wie Debuggern und Codeprofilern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b65a0-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
 <span data-ttu-id="b65a0-113">Neben den verwalteten Typen im <xref:System.Reflection.Emit>-Namespace sind nicht verwaltete Metadatenschnittstellen verfügbar, die in der Referenzdokumentation zu [Metadatenschnittstellen](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b65a0-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="b65a0-114">Die verwaltete Reflektionsausgabe bietet eine bessere semantische Fehlerüberprüfung und einen höheren Abstraktionsgrad für Metadaten als die nicht verwalteten Metadatenschnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b65a0-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
 <span data-ttu-id="b65a0-115">In der Common Language Infrastructure(CLI)-Dokumentation, insbesondere in den Themen "Partition II: Metadata Definition and Semantics" und "Partition III: CIL Instruction Set" finden Sie weitere hilfreiche Informationen zur Verwendung von Metadaten und MSIL.</span><span class="sxs-lookup"><span data-stu-id="b65a0-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="b65a0-116">Die Dokumentation ist online auf [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) und der [Ecma-Website](http://go.microsoft.com/fwlink/?LinkId=116487) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b65a0-116">The documentation is available online on [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](http://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b65a0-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b65a0-117">In This Section</span></span>  
 [<span data-ttu-id="b65a0-118">Sicherheitsaspekte bei der Reflektionsausgabe</span><span class="sxs-lookup"><span data-stu-id="b65a0-118">Security Issues in Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
 <span data-ttu-id="b65a0-119">Beschreibt Sicherheitsaspekte im Zusammenhang mit dem Erstellen dynamischer Assemblys mithilfe der Reflektionsausgabe.</span><span class="sxs-lookup"><span data-stu-id="b65a0-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b65a0-120">Verweis</span><span class="sxs-lookup"><span data-stu-id="b65a0-120">Reference</span></span>  
 <xref:System.Reflection.Emit.OpCodes>  
 <span data-ttu-id="b65a0-121">Hier werden die MSIL-Anweisungcodes zum Erstellen von Methodentexten katalogisiert.</span><span class="sxs-lookup"><span data-stu-id="b65a0-121">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
 <xref:System.Reflection.Emit>  
 <span data-ttu-id="b65a0-122">Hier werden verwaltete Klassen aufgeführt, die zum Ausgeben von dynamischen Methoden, Assemblys und Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b65a0-122">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
 <xref:System.Type>  
 <span data-ttu-id="b65a0-123">Hier wird die <xref:System.Type>-Klasse beschrieben, die Typen in der verwalteten Reflektion und Reflektionsausgabe darstellt. Diese Klasse ist das wichtigste Element bei der Verwendung dieser Technologien.</span><span class="sxs-lookup"><span data-stu-id="b65a0-123">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
 <xref:System.Reflection>  
 <span data-ttu-id="b65a0-124">Hier werden verwaltete Klassen aufgeführt, die zum Durchsuchen von Metadaten und verwaltetem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b65a0-124">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b65a0-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b65a0-125">Related Sections</span></span>  
 [<span data-ttu-id="b65a0-126">Reflektion</span><span class="sxs-lookup"><span data-stu-id="b65a0-126">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="b65a0-127">Erläutert das Durchsuchen von Metadaten und verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="b65a0-127">Explains how to explore metadata and managed code.</span></span>  
  
 [<span data-ttu-id="b65a0-128">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="b65a0-128">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="b65a0-129">Bietet eine Übersicht über Assemblys in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b65a0-129">Provides an overview of assemblies in the .NET Framework.</span></span>

