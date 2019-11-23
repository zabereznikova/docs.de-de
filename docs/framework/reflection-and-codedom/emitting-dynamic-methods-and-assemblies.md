---
title: Ausgeben von dynamischen Methoden und Assemblys
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: 4578b708b10e93a7f5def5b9dc040eeb646bdc8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130238"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="d4c63-102">Ausgeben von dynamischen Methoden und Assemblys</span><span class="sxs-lookup"><span data-stu-id="d4c63-102">Emitting Dynamic Methods and Assemblies</span></span>

<span data-ttu-id="d4c63-103">In diesem Abschnitt wird ein Satz verwalteter Typen im <xref:System.Reflection.Emit>-Namespace beschrieben, mit denen ein Compiler oder ein Tool zur Laufzeit Metadaten und Microsoft Intermediate Language (MSIL) ausgeben und optional eine übertragbare ausführbare Datei (PE-Datei) auf dem Datenträger generieren kann.</span><span class="sxs-lookup"><span data-stu-id="d4c63-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="d4c63-104">Dieser Namespace wird primär von Skript-Engines und Compilern verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4c63-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="d4c63-105">Die vom <xref:System.Reflection.Emit>-Namespace bereitgestellte Funktionalität wird in diesem Abschnitt als Reflektionsausgabe bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d4c63-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
<span data-ttu-id="d4c63-106">Die Reflektionsausgabe bietet die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="d4c63-106">Reflection emit provides the following capabilities:</span></span>  
  
- <span data-ttu-id="d4c63-107">Sie können mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse einfache globale Methoden zur Laufzeit definieren und diese mithilfe von Delegaten ausführen.</span><span class="sxs-lookup"><span data-stu-id="d4c63-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
- <span data-ttu-id="d4c63-108">Sie können Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.</span><span class="sxs-lookup"><span data-stu-id="d4c63-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
- <span data-ttu-id="d4c63-109">Sie können Assemblys zur Laufzeit definieren, sie ausführen und dann entladen und der Garbage Collection ermöglichen, die zugehörigen Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="d4c63-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
- <span data-ttu-id="d4c63-110">Sie können Module in neuen Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.</span><span class="sxs-lookup"><span data-stu-id="d4c63-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
- <span data-ttu-id="d4c63-111">Sie können Typen in Modulen zur Laufzeit definieren, Instanzen dieser Typen erstellen und deren Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d4c63-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
- <span data-ttu-id="d4c63-112">Sie können symbolische Informationen für definierte Module angeben, die von Tools wie Debuggern und Codeprofilern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d4c63-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
<span data-ttu-id="d4c63-113">Neben den verwalteten Typen im <xref:System.Reflection.Emit>-Namespace sind nicht verwaltete Metadatenschnittstellen verfügbar, die in der Referenzdokumentation zu [Metadatenschnittstellen](../unmanaged-api/metadata/metadata-interfaces.md) beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d4c63-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="d4c63-114">Die verwaltete Reflektionsausgabe bietet eine bessere semantische Fehlerüberprüfung und einen höheren Abstraktionsgrad für Metadaten als die nicht verwalteten Metadatenschnittstellen.</span><span class="sxs-lookup"><span data-stu-id="d4c63-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
<span data-ttu-id="d4c63-115">In der Common Language Infrastructure(CLI)-Dokumentation, insbesondere in den Themen "Partition II: Metadata Definition and Semantics" und "Partition III: CIL Instruction Set" finden Sie weitere hilfreiche Informationen zur Verwendung von Metadaten und MSIL.</span><span class="sxs-lookup"><span data-stu-id="d4c63-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="d4c63-116">Die Dokumentation ist online auf [MSDN](https://go.microsoft.com/fwlink/?LinkID=65555) und der [Ecma-Website](https://go.microsoft.com/fwlink/?LinkId=116487) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d4c63-116">The documentation is available online on [MSDN](https://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](https://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4c63-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d4c63-117">In This Section</span></span>
  
[<span data-ttu-id="d4c63-118">Sicherheitsaspekte bei der Reflektionsausgabe</span><span class="sxs-lookup"><span data-stu-id="d4c63-118">Security issues in reflection emit</span></span>](security-issues-in-reflection-emit.md)  
<span data-ttu-id="d4c63-119">Beschreibt Sicherheitsaspekte im Zusammenhang mit dem Erstellen dynamischer Assemblys mithilfe der Reflektionsausgabe.</span><span class="sxs-lookup"><span data-stu-id="d4c63-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="d4c63-120">[Vorgehensweise: Definieren und Ausführen von dynamischen Methoden](how-to-define-and-execute-dynamic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="d4c63-120">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) </span></span>  
<span data-ttu-id="d4c63-121">Zeigt, wie eine einfache dynamische Methode sowie eine dynamische Methode, die an eine Instanz einer Klasse gebunden ist, ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d4c63-121">Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="d4c63-122">[Vorgehensweise: Definieren eines generischen Typs mit Reflektionsausgabe](how-to-define-a-generic-type-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="d4c63-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) </span></span>  
<span data-ttu-id="d4c63-123">Zeigt, wie ein einfacher generischer Typ mit zwei Typparametern erstellt wird, wie Klasseneinschränkungen, Schnittstellen und bestimmte Einschränkungen für Typparameter angewandt werden und wie Member erstellt werden, die die Typparameter der Klasse als Parametertypen und Rückgabetypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4c63-123">Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="d4c63-124">[Vorgehensweise: Definieren einer generischen Methode mit Reflektionsausgabe](how-to-define-a-generic-method-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="d4c63-124">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) </span></span>  
<span data-ttu-id="d4c63-125">Zeigt, wie einfache generische Methoden erstellt, ausgegeben und aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d4c63-125">Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="d4c63-126">[Entladbare Assemblys für die dynamische Typgenerierung](collectible-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="d4c63-126">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) </span></span>  
<span data-ttu-id="d4c63-127">Führt in das Thema „entladbare Assemblys“ ein. Dabei handelt es sich um dynamische Assemblys, die entladen werden können, ohne gleichzeitig auch die Anwendungsdomäne zu entladen, in der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d4c63-127">Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="d4c63-128">Verweis</span><span class="sxs-lookup"><span data-stu-id="d4c63-128">Reference</span></span>  

<xref:System.Reflection.Emit.OpCodes>  
<span data-ttu-id="d4c63-129">Hier werden die MSIL-Anweisungcodes zum Erstellen von Methodentexten katalogisiert.</span><span class="sxs-lookup"><span data-stu-id="d4c63-129">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
<xref:System.Reflection.Emit>  
<span data-ttu-id="d4c63-130">Hier werden verwaltete Klassen aufgeführt, die zum Ausgeben von dynamischen Methoden, Assemblys und Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4c63-130">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
<xref:System.Type>  
<span data-ttu-id="d4c63-131">Hier wird die <xref:System.Type>-Klasse beschrieben, die Typen in der verwalteten Reflektion und Reflektionsausgabe darstellt. Diese Klasse ist das wichtigste Element bei der Verwendung dieser Technologien.</span><span class="sxs-lookup"><span data-stu-id="d4c63-131">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
<xref:System.Reflection>  
<span data-ttu-id="d4c63-132">Hier werden verwaltete Klassen aufgeführt, die zum Durchsuchen von Metadaten und verwaltetem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4c63-132">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d4c63-133">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d4c63-133">Related Sections</span></span>  

[<span data-ttu-id="d4c63-134">Reflektion</span><span class="sxs-lookup"><span data-stu-id="d4c63-134">Reflection</span></span>](reflection.md)  
<span data-ttu-id="d4c63-135">Erläutert das Durchsuchen von Metadaten und verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="d4c63-135">Explains how to explore metadata and managed code.</span></span>  
  
[<span data-ttu-id="d4c63-136">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="d4c63-136">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="d4c63-137">Bietet eine Übersicht über Assemblys in .NET-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="d4c63-137">Provides an overview of assemblies in .NET implementations.</span></span>
