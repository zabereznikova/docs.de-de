---
title: Ausgeben von dynamischen Methoden und Assemblys
description: Hier erfahren Sie, wie Sie dynamische Methoden und Assemblys mithilfe des Namespace „System.Reflection.Emit“ ausgeben. So können ein Compiler oder ein Tool Metadaten und MSIL-Code zur Laufzeit ausgeben.
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: 76d2a83943d9df06cc66cf86c6869f18fac2a12c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475046"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="4b2cd-103">Ausgeben von dynamischen Methoden und Assemblys</span><span class="sxs-lookup"><span data-stu-id="4b2cd-103">Emitting Dynamic Methods and Assemblies</span></span>

<span data-ttu-id="4b2cd-104">In diesem Abschnitt wird ein Satz verwalteter Typen im <xref:System.Reflection.Emit>-Namespace beschrieben, mit denen ein Compiler oder ein Tool zur Laufzeit Metadaten und Microsoft Intermediate Language (MSIL) ausgeben und optional eine übertragbare ausführbare Datei (PE-Datei) auf dem Datenträger generieren kann.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-104">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="4b2cd-105">Dieser Namespace wird primär von Skript-Engines und Compilern verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-105">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="4b2cd-106">Die vom <xref:System.Reflection.Emit>-Namespace bereitgestellte Funktionalität wird in diesem Abschnitt als Reflektionsausgabe bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-106">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
<span data-ttu-id="4b2cd-107">Die Reflektionsausgabe bietet die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="4b2cd-107">Reflection emit provides the following capabilities:</span></span>  
  
- <span data-ttu-id="4b2cd-108">Sie können mithilfe der <xref:System.Reflection.Emit.DynamicMethod>-Klasse einfache globale Methoden zur Laufzeit definieren und diese mithilfe von Delegaten ausführen.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-108">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
- <span data-ttu-id="4b2cd-109">Sie können Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-109">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
- <span data-ttu-id="4b2cd-110">Sie können Assemblys zur Laufzeit definieren, sie ausführen und dann entladen und der Garbage Collection ermöglichen, die zugehörigen Ressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-110">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
- <span data-ttu-id="4b2cd-111">Sie können Module in neuen Assemblys zur Laufzeit definieren und anschließend ausführen und/oder auf dem Datenträger speichern.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-111">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
- <span data-ttu-id="4b2cd-112">Sie können Typen in Modulen zur Laufzeit definieren, Instanzen dieser Typen erstellen und deren Methoden aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-112">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
- <span data-ttu-id="4b2cd-113">Sie können symbolische Informationen für definierte Module angeben, die von Tools wie Debuggern und Codeprofilern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-113">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
<span data-ttu-id="4b2cd-114">Neben den verwalteten Typen im <xref:System.Reflection.Emit>-Namespace sind nicht verwaltete Metadatenschnittstellen verfügbar, die in der Referenzdokumentation zu [Metadatenschnittstellen](../unmanaged-api/metadata/metadata-interfaces.md) beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-114">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="4b2cd-115">Die verwaltete Reflektionsausgabe bietet eine bessere semantische Fehlerüberprüfung und einen höheren Abstraktionsgrad für Metadaten als die nicht verwalteten Metadatenschnittstellen.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-115">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
<span data-ttu-id="4b2cd-116">In der Common Language Infrastructure(CLI)-Dokumentation, insbesondere in den Themen "Partition II: Metadatendefinition und Semantik) und „Partition III: CIL Instruction Set“ (Partition III: CIL-Anweisungen).</span><span class="sxs-lookup"><span data-stu-id="4b2cd-116">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="4b2cd-117">Die Dokumentation ist online auf der [Ecma-Website](https://www.ecma-international.org/publications/standards/Ecma-335.htm) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-117">The documentation is available online at the [Ecma Web site](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b2cd-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4b2cd-118">In This Section</span></span>
  
[<span data-ttu-id="4b2cd-119">Sicherheitsaspekte bei der Reflektionsausgabe</span><span class="sxs-lookup"><span data-stu-id="4b2cd-119">Security issues in reflection emit</span></span>](security-issues-in-reflection-emit.md)  
<span data-ttu-id="4b2cd-120">Beschreibt Sicherheitsaspekte im Zusammenhang mit dem Erstellen dynamischer Assemblys mithilfe der Reflektionsausgabe.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-120">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="4b2cd-121">[How to: Definieren und Ausführen von dynamischen Methoden:](how-to-define-and-execute-dynamic-methods.md) Zeigt, wie eine einfache dynamische Methode sowie eine dynamische Methode, die an eine Instanz einer Klasse gebunden ist, ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="4b2cd-121">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="4b2cd-122">[How to: Definieren eines generischen Typs mit Reflexionsausgabe:](how-to-define-a-generic-type-with-reflection-emit.md) Zeigt, wie ein einfacher generischer Typ mit zwei Typparametern erstellt wird, wie Klasseneinschränkungen, Schnittstelleneinschränkungen und bestimmte Einschränkungen für Typparameter angewandt werden und wie Member erstellt werden, die die Typparameter der Klasse als Parameter- und Rückgabetypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="4b2cd-123">[How to: Definieren einer generischen Methode mit Reflexionsausgabe:](how-to-define-a-generic-method-with-reflection-emit.md) Zeigt, wie eine einfache generische Methode erstellt, ausgegeben und aufgerufen wird</span><span class="sxs-lookup"><span data-stu-id="4b2cd-123">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="4b2cd-124">[Entladbare Assemblys für die dynamische Typgenerierung:](collectible-assemblies.md) Führt entladbare Assemblys ein. Dabei handelt es sich um dynamische Assemblys, die entladen werden können, ohne gleichzeitig auch die Anwendungsdomäne zu entladen, in der sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-124">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="4b2cd-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="4b2cd-125">Reference</span></span>  

<xref:System.Reflection.Emit.OpCodes>  
<span data-ttu-id="4b2cd-126">Hier werden die MSIL-Anweisungcodes zum Erstellen von Methodentexten katalogisiert.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-126">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
<xref:System.Reflection.Emit>  
<span data-ttu-id="4b2cd-127">Hier werden verwaltete Klassen aufgeführt, die zum Ausgeben von dynamischen Methoden, Assemblys und Typen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-127">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
<xref:System.Type>  
<span data-ttu-id="4b2cd-128">Hier wird die <xref:System.Type>-Klasse beschrieben, die Typen in der verwalteten Reflektion und Reflektionsausgabe darstellt. Diese Klasse ist das wichtigste Element bei der Verwendung dieser Technologien.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-128">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
<xref:System.Reflection>  
<span data-ttu-id="4b2cd-129">Hier werden verwaltete Klassen aufgeführt, die zum Durchsuchen von Metadaten und verwaltetem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-129">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4b2cd-130">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4b2cd-130">Related Sections</span></span>  

[<span data-ttu-id="4b2cd-131">Reflexion</span><span class="sxs-lookup"><span data-stu-id="4b2cd-131">Reflection</span></span>](reflection.md)  
<span data-ttu-id="4b2cd-132">Erläutert das Durchsuchen von Metadaten und verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-132">Explains how to explore metadata and managed code.</span></span>  
  
[<span data-ttu-id="4b2cd-133">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="4b2cd-133">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="4b2cd-134">Bietet eine Übersicht über Assemblys in .NET-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="4b2cd-134">Provides an overview of assemblies in .NET implementations.</span></span>
