---
title: Ausgeben von dynamischen Methoden und Assemblys
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: fda5a20eb7798086ec10415889454b4a8beba5f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180526"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="fb0be-102">Ausgeben von dynamischen Methoden und Assemblys</span><span class="sxs-lookup"><span data-stu-id="fb0be-102">Emitting Dynamic Methods and Assemblies</span></span>

<span data-ttu-id="fb0be-103">In diesem Abschnitt wird ein Satz verwalteter Typen im <xref:System.Reflection.Emit>-Namespace beschrieben, mit denen ein Compiler oder ein Tool zur Laufzeit Metadaten und Microsoft Intermediate Language (MSIL) ausgeben und optional eine übertragbare ausführbare Datei (PE-Datei) auf dem Datenträger generieren kann.</span><span class="sxs-lookup"><span data-stu-id="fb0be-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="fb0be-104">Dieser Namespace wird primär von Skript-Engines und Compilern verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb0be-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="fb0be-105">Die vom <xref:System.Reflection.Emit>-Namespace bereitgestellte Funktionalität wird in diesem Abschnitt als Reflektionsausgabe bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fb0be-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
<span data-ttu-id="fb0be-106">Die Reflektionsausgabe bietet die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="fb0be-106">Reflection emit provides the following capabilities:</span></span>  
  
- <span data-ttu-id="fb0be-107">Sie können mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse einfache globale Methoden zur Laufzeit definieren und diese mithilfe von Delegaten ausführen.</span><span class="sxs-lookup"><span data-stu-id="fb0be-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
- <span data-ttu-id="fb0be-108">Sie können Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.</span><span class="sxs-lookup"><span data-stu-id="fb0be-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
- <span data-ttu-id="fb0be-109">Sie können Assemblys zur Laufzeit definieren, sie ausführen und dann entladen und der Garbage Collection ermöglichen, die zugehörigen Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="fb0be-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
- <span data-ttu-id="fb0be-110">Sie können Module in neuen Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.</span><span class="sxs-lookup"><span data-stu-id="fb0be-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
- <span data-ttu-id="fb0be-111">Sie können Typen in Modulen zur Laufzeit definieren, Instanzen dieser Typen erstellen und deren Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fb0be-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
- <span data-ttu-id="fb0be-112">Sie können symbolische Informationen für definierte Module angeben, die von Tools wie Debuggern und Codeprofilern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fb0be-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
<span data-ttu-id="fb0be-113">Neben den verwalteten Typen im <xref:System.Reflection.Emit>-Namespace sind nicht verwaltete Metadatenschnittstellen verfügbar, die in der Referenzdokumentation zu [Metadatenschnittstellen](../unmanaged-api/metadata/metadata-interfaces.md) beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fb0be-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="fb0be-114">Die verwaltete Reflektionsausgabe bietet eine bessere semantische Fehlerüberprüfung und einen höheren Abstraktionsgrad für Metadaten als die nicht verwalteten Metadatenschnittstellen.</span><span class="sxs-lookup"><span data-stu-id="fb0be-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
<span data-ttu-id="fb0be-115">In der Common Language Infrastructure(CLI)-Dokumentation, insbesondere in den Themen "Partition II: Metadata Definition and Semantics" und "Partition III: CIL Instruction Set" finden Sie weitere hilfreiche Informationen zur Verwendung von Metadaten und MSIL.</span><span class="sxs-lookup"><span data-stu-id="fb0be-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="fb0be-116">Die Dokumentation ist online auf der [Ecma-Website](https://www.ecma-international.org/publications/standards/Ecma-335.htm)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fb0be-116">The documentation is available online at the [Ecma Web site](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb0be-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fb0be-117">In This Section</span></span>
  
[<span data-ttu-id="fb0be-118">Sicherheitsprobleme in der Reflexion emittieren</span><span class="sxs-lookup"><span data-stu-id="fb0be-118">Security issues in reflection emit</span></span>](security-issues-in-reflection-emit.md)  
<span data-ttu-id="fb0be-119">Beschreibt Sicherheitsaspekte im Zusammenhang mit dem Erstellen dynamischer Assemblys mithilfe der Reflektionsausgabe.</span><span class="sxs-lookup"><span data-stu-id="fb0be-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="fb0be-120">[Gewusst wie: Definieren und Ausführen dynamischer Methoden](how-to-define-and-execute-dynamic-methods.md) Zeigt, wie eine einfache dynamische Methode und eine dynamische Methode ausgeführt werden, die an eine Instanz einer Klasse gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="fb0be-120">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="fb0be-121">[Gewusst wie: Definieren eines generischen Typs mit Reflexionsee](how-to-define-a-generic-type-with-reflection-emit.md) Zeigt, wie sie einen einfachen generischen Typ mit zwei Typparametern erstellen, Klassen-, Schnittstellen- und Sondereinschränkungen auf die Typparameter anwenden und wie Member erstellt werden, die die Typparameter der Klasse als Parametertypen und Rückgabetypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb0be-121">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="fb0be-122">[Gewusst wie: Definieren einer generischen Methode mit Reflexionsee](how-to-define-a-generic-method-with-reflection-emit.md) Zeigt, wie eine einfache generische Methode erstellt, ausgesendet und aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fb0be-122">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="fb0be-123">[Sammelbaugruppen für die dynamische Typgenerierung](collectible-assemblies.md) Führt Sammelassemblys ein, bei denen es sich um dynamische Assemblys handelt, die entladen werden können, ohne die Anwendungsdomäne zu entladen, in der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="fb0be-123">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="fb0be-124">Verweis</span><span class="sxs-lookup"><span data-stu-id="fb0be-124">Reference</span></span>  

<xref:System.Reflection.Emit.OpCodes>  
<span data-ttu-id="fb0be-125">Hier werden die MSIL-Anweisungcodes zum Erstellen von Methodentexten katalogisiert.</span><span class="sxs-lookup"><span data-stu-id="fb0be-125">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
<xref:System.Reflection.Emit>  
<span data-ttu-id="fb0be-126">Hier werden verwaltete Klassen aufgeführt, die zum Ausgeben von dynamischen Methoden, Assemblys und Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb0be-126">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
<xref:System.Type>  
<span data-ttu-id="fb0be-127">Hier wird die <xref:System.Type>-Klasse beschrieben, die Typen in der verwalteten Reflektion und Reflektionsausgabe darstellt. Diese Klasse ist das wichtigste Element bei der Verwendung dieser Technologien.</span><span class="sxs-lookup"><span data-stu-id="fb0be-127">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
<xref:System.Reflection>  
<span data-ttu-id="fb0be-128">Hier werden verwaltete Klassen aufgeführt, die zum Durchsuchen von Metadaten und verwaltetem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb0be-128">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fb0be-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="fb0be-129">Related Sections</span></span>  

[<span data-ttu-id="fb0be-130">Reflexion</span><span class="sxs-lookup"><span data-stu-id="fb0be-130">Reflection</span></span>](reflection.md)  
<span data-ttu-id="fb0be-131">Erläutert das Durchsuchen von Metadaten und verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="fb0be-131">Explains how to explore metadata and managed code.</span></span>  
  
[<span data-ttu-id="fb0be-132">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="fb0be-132">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="fb0be-133">Bietet eine Übersicht über Assemblys in .NET-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="fb0be-133">Provides an overview of assemblies in .NET implementations.</span></span>
