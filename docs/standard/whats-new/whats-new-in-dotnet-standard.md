---
title: Neuerungen im .NET Standard
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3a5833bdfcf1e3433ea82403908e9a06a88cde27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="8fd61-102">Neuerungen im .NET Standard</span><span class="sxs-lookup"><span data-stu-id="8fd61-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="8fd61-103">Der .NET Standard ist eine formale Spezifikation. Sie definiert einen Satz von APIs mit Versionsangabe, die in .NET Implementierungen verfügbar sein müssen, die dieser Version des Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8fd61-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="8fd61-104">.NET Standard ist auf Bibliotheksentwickler ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="8fd61-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="8fd61-105">Eine Bibliothek, die auf eine .NET Standard-Version abzielt, kann in jeder .NET Framework-, .NET Core- oder Xamarin-Implementierung verwendet werden, die diese Version des Standards unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8fd61-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="8fd61-106">Die neueste Version von .NET Standard ist 2.0.</span><span class="sxs-lookup"><span data-stu-id="8fd61-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="8fd61-107">Diese Version ist im .NET Core 2.0 SDK und in der Visual Studio 2017-Version 15.3 mit installierter .NET Core-Workload enthalten.</span><span class="sxs-lookup"><span data-stu-id="8fd61-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="8fd61-108">Unterstützte .NET-Implementierungen</span><span class="sxs-lookup"><span data-stu-id="8fd61-108">Supported .NET implementations</span></span>

<span data-ttu-id="8fd61-109">Der .NET Standard 2.0 wird von den folgenden .NET-Implementierungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="8fd61-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="8fd61-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8fd61-110">.NET Core 2.0</span></span>
- <span data-ttu-id="8fd61-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8fd61-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="8fd61-112">Mono 5.4</span><span class="sxs-lookup"><span data-stu-id="8fd61-112">Mono 5.4</span></span>
- <span data-ttu-id="8fd61-113">Xamarin.iOS 10.14</span><span class="sxs-lookup"><span data-stu-id="8fd61-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="8fd61-114">Xamarin.Mac 3.8</span><span class="sxs-lookup"><span data-stu-id="8fd61-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="8fd61-115">Xamarin.Android 8.0</span><span class="sxs-lookup"><span data-stu-id="8fd61-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="8fd61-116">Universelle Windows-Plattform 10.0.16299</span><span class="sxs-lookup"><span data-stu-id="8fd61-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="8fd61-117">Neuerungen im .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="8fd61-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="8fd61-118">Der .NET Standard 2.0 umfasst folgende neue Features:</span><span class="sxs-lookup"><span data-stu-id="8fd61-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="8fd61-119">**Ein umfassend erweiterter Satz von APIs**</span><span class="sxs-lookup"><span data-stu-id="8fd61-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="8fd61-120">Bis einschließlich Version 1.6 enthielt der .NET Standard eine vergleichsweise kleine Teilmenge von APIs.</span><span class="sxs-lookup"><span data-stu-id="8fd61-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="8fd61-121">Nicht enthalten war eine Vielzahl von APIs, die im Allgemeinen in .NET Framework oder Xamarin verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="8fd61-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="8fd61-122">Dies verkompliziert die Entwicklung, da Entwickler geeigneten Ersatz für vertraute APIs finden müssen, wenn sie Anwendungen und Bibliotheken für verschiedene .NET-Implementierungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="8fd61-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="8fd61-123">Im .NET Standard 2.0 besteht diese Einschränkung nicht mehr, da über 20.000 weitere APIs hinzugefügt wurden, als im .NET Standard 1.6, der vorherigen Version des Standards, verfügbar waren.</span><span class="sxs-lookup"><span data-stu-id="8fd61-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="8fd61-124">Eine Liste der APIs, die zum .NET Standard 2.0, hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="8fd61-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="8fd61-125">Im Folgenden finden Sie einige der neuen Features für den <xref:System>-Namespace im .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="8fd61-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="8fd61-126">Unterstützung für die <xref:System.AppDomain>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fd61-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="8fd61-127">Bessere Unterstützung für die Arbeit mit Arrays dank zusätzlicher Member in der <xref:System.Array>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fd61-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="8fd61-128">Bessere Unterstützung für die Arbeit mit Attributen dank zusätzlicher Member in der <xref:System.Attribute>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fd61-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="8fd61-129">Bessere Kalenderunterstützung und zusätzliche Formatierungsoptionen für <xref:System.DateTime>-Werte.</span><span class="sxs-lookup"><span data-stu-id="8fd61-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="8fd61-130">Zusätzliche <xref:System.Decimal>-Rundungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="8fd61-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="8fd61-131">Zusätzliche Funktionen in der <xref:System.Environment>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fd61-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="8fd61-132">Erweiterte Steuerung des Garbage Collector über die <xref:System.GC>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fd61-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="8fd61-133">Erweiterte Unterstützung für Zeichenfolgenvergleich, Enumeration und Normalisierung in der <xref:System.String>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fd61-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="8fd61-134">Unterstützung für Sommerzeitanpassungen und Übergangszeiten in den Klassen <xref:System.TimeZoneInfo.AdjustmentRule> und <xref:System.TimeZoneInfo.TransitionTime>.</span><span class="sxs-lookup"><span data-stu-id="8fd61-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="8fd61-135">Erheblich erweiterte Funktionalität in der <xref:System.Type>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fd61-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="8fd61-136">Bessere Unterstützung für die Deserialisierung von Ausnahmeobjekten durch Hinzufügen eines Ausnahmekonstruktors mit den Parametern <xref:System.Runtime.Serialization.SerializationInfo> und <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="8fd61-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="8fd61-137">**Unterstützung für .NET Framework-Bibliotheken**</span><span class="sxs-lookup"><span data-stu-id="8fd61-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="8fd61-138">Die überwiegende Mehrheit von Bibliotheken wird eher für das .NET Framework als für den .NET Standard entworfen.</span><span class="sxs-lookup"><span data-stu-id="8fd61-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="8fd61-139">Die meisten Aufrufe in diesen Bibliotheken gelten jedoch für APIs, die im .NET Standard 2.0 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="8fd61-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="8fd61-140">Ab .NET Standard 2.0 können Sie mithilfe eines [Kompatibilitätsshims](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification) von einer .NET Standard-Bibliothek auf .NET Framework-Bibliotheken zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8fd61-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="8fd61-141">Diese Kompatibilitätsebene ist transparent für Entwickler – Sie müssen keine besondere Maßnahme ergreifen, um von .NET Framework-Bibliotheken zu profitieren.</span><span class="sxs-lookup"><span data-stu-id="8fd61-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="8fd61-142">Die einzige Anforderung besteht darin, dass die von der .NET Framework-Klassenbibliothek aufgerufenen APIs im .NET Standard 2.0 enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="8fd61-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="8fd61-143">**Unterstützung für Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="8fd61-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="8fd61-144">Sie können jetzt .NET Standard-Bibliotheken in Visual Basic entwickeln.</span><span class="sxs-lookup"><span data-stu-id="8fd61-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="8fd61-145">Für Visual Basic-Entwickler, die Visual Studio 2017 Version 15.3 oder höher mit installierter .NET Core-Workload verwenden, enthält Visual Studio jetzt eine Vorlage für die .NET Standard-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="8fd61-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="8fd61-146">Visual Basic-Entwickler, die andere Entwicklungstools und -umgebungen verwenden, können den Befehl [dotnet new](../../core/tools/dotnet-new.md) verwenden, um ein Projekt für die .NET Standard-Bibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8fd61-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="8fd61-147">Weitere Informationen finden Sie unter [Toolunterstützung für .NET Standard-Bibliotheken](#tooling).</span><span class="sxs-lookup"><span data-stu-id="8fd61-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="8fd61-148"><a name="tooling" />**Toolunterstützung für .NET Standard-Bibliotheken**</span><span class="sxs-lookup"><span data-stu-id="8fd61-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="8fd61-149">Mit der Veröffentlichung von .NET Core 2.0 und .NET Standard 2.0 enthalten sowohl Visual Studio 2017 als auch die [.NET Core-Befehlszeilenschnittstelle (CLI)](../../core/tools/index.md) Toolunterstützung für die Erstellung von .NET Standard-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="8fd61-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="8fd61-150">Wenn Sie Visual Studio mit der Workload für die **plattformübergreifende .NET Core-Entwicklung** installieren, können Sie ein .NET Standard 2.0-Bibliotheksprojekt mithilfe einer Projektvorlage erstellen, wie in der folgenden Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8fd61-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="8fd61-151">C#</span><span class="sxs-lookup"><span data-stu-id="8fd61-151">C#</span></span>](#tab/csharp)
![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="8fd61-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8fd61-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-vb.png)
---

<span data-ttu-id="8fd61-155">Wenn Sie die .NET Core-CLI verwenden, erstellt der folgende [dotnet new](../../core/tools/dotnet-new.md)-Befehl ein Klassenbibliotheksprojekt mit .NET Standard 2.0 als Ziel.</span><span class="sxs-lookup"><span data-stu-id="8fd61-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="8fd61-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fd61-156">See Also</span></span>
<span data-ttu-id="8fd61-157">[.NET Standard](../net-standard.md)
[Einführung in .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span><span class="sxs-lookup"><span data-stu-id="8fd61-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
