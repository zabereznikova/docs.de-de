---
title: Neuerungen im .NET Standard
description: In diesem Artikel werden neue Features und Verbesserungen zusammengefasst, die in jeder neuen Version von .NET Standard auffindbar sind.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: ebf656c4a5499fff54cb5a70a93c4e8cc9c82d0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101757"
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="66d7d-103">Neuerungen im .NET Standard</span><span class="sxs-lookup"><span data-stu-id="66d7d-103">What's new in the .NET Standard</span></span>

<span data-ttu-id="66d7d-104">.NET Standard ist eine formale Spezifikation, die mehrere APIs mit Versionsangabe definiert, die in .NET-Implementierungen verfügbar sein müssen, die dieser Version des Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="66d7d-104">The .NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="66d7d-105">.NET Standard ist auf Bibliotheksentwickler ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="66d7d-105">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="66d7d-106">Eine Bibliothek, die auf eine .NET Standard-Version abzielt, kann in jeder .NET Framework-, .NET Core- oder Xamarin-Implementierung verwendet werden, die diese Version des Standards unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66d7d-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="66d7d-107">Die neueste Version von .NET Standard ist 2.0.</span><span class="sxs-lookup"><span data-stu-id="66d7d-107">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="66d7d-108">Diese Version ist in .NET Core 2.0 SDK und in Visual Studio 2017 Version 15.3 mit installierter .NET Core-Workload enthalten.</span><span class="sxs-lookup"><span data-stu-id="66d7d-108">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="66d7d-109">Unterstützte .NET-Implementierungen</span><span class="sxs-lookup"><span data-stu-id="66d7d-109">Supported .NET implementations</span></span>

<span data-ttu-id="66d7d-110">Der .NET Standard 2.0 wird von den folgenden .NET-Implementierungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="66d7d-110">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="66d7d-111">.NET Core 2.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="66d7d-111">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="66d7d-112">.NET Framework 4.6.1 oder höher</span><span class="sxs-lookup"><span data-stu-id="66d7d-112">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="66d7d-113">Mono 5.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="66d7d-113">Mono 5.4 or later</span></span>
- <span data-ttu-id="66d7d-114">Xamarin.iOS 10.14 oder höher</span><span class="sxs-lookup"><span data-stu-id="66d7d-114">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="66d7d-115">Xamarin.Mac 3.8 oder höher</span><span class="sxs-lookup"><span data-stu-id="66d7d-115">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="66d7d-116">Xamarin.Android 8.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="66d7d-116">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="66d7d-117">Universal Windows Platform 10.0.16299 oder höher</span><span class="sxs-lookup"><span data-stu-id="66d7d-117">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="66d7d-118">Neuerungen im .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="66d7d-118">What's new in the .NET Standard 2.0</span></span>

<span data-ttu-id="66d7d-119">Der .NET Standard 2.0 umfasst folgende neue Features:</span><span class="sxs-lookup"><span data-stu-id="66d7d-119">The .NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="66d7d-120">Ein umfassend erweiterter Satz von APIs</span><span class="sxs-lookup"><span data-stu-id="66d7d-120">A vastly expanded set of APIs</span></span>

<span data-ttu-id="66d7d-121">Bis einschließlich Version 1.6 enthielt der .NET Standard eine vergleichsweise kleine Teilmenge von APIs.</span><span class="sxs-lookup"><span data-stu-id="66d7d-121">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="66d7d-122">Nicht enthalten war eine Vielzahl von APIs, die im Allgemeinen in .NET Framework oder Xamarin verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="66d7d-122">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="66d7d-123">Dies verkompliziert die Entwicklung, da Entwickler geeigneten Ersatz für vertraute APIs finden müssen, wenn sie Anwendungen und Bibliotheken für verschiedene .NET-Implementierungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="66d7d-123">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="66d7d-124">Im .NET Standard 2.0 besteht diese Einschränkung nicht mehr, da über 20.000 weitere APIs hinzugefügt wurden, als im .NET Standard 1.6, der vorherigen Version des Standards, verfügbar waren.</span><span class="sxs-lookup"><span data-stu-id="66d7d-124">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="66d7d-125">Eine Liste der APIs, die zum .NET Standard 2.0, hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="66d7d-125">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="66d7d-126">Im Folgenden finden Sie einige der neuen Features für den <xref:System>-Namespace im .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="66d7d-126">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="66d7d-127">Unterstützung für die <xref:System.AppDomain>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="66d7d-127">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="66d7d-128">Bessere Unterstützung für die Arbeit mit Arrays dank zusätzlicher Member in der <xref:System.Array>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="66d7d-128">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="66d7d-129">Bessere Unterstützung für die Arbeit mit Attributen dank zusätzlicher Member in der <xref:System.Attribute>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="66d7d-129">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="66d7d-130">Bessere Kalenderunterstützung und zusätzliche Formatierungsoptionen für <xref:System.DateTime>-Werte.</span><span class="sxs-lookup"><span data-stu-id="66d7d-130">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="66d7d-131">Zusätzliche <xref:System.Decimal>-Rundungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="66d7d-131">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="66d7d-132">Zusätzliche Funktionen in der <xref:System.Environment>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="66d7d-132">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="66d7d-133">Erweiterte Steuerung des Garbage Collector über die <xref:System.GC>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="66d7d-133">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="66d7d-134">Erweiterte Unterstützung für Zeichenfolgenvergleich, Enumeration und Normalisierung in der <xref:System.String>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="66d7d-134">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="66d7d-135">Unterstützung für Sommerzeitanpassungen und Übergangszeiten in den Klassen <xref:System.TimeZoneInfo.AdjustmentRule> und <xref:System.TimeZoneInfo.TransitionTime>.</span><span class="sxs-lookup"><span data-stu-id="66d7d-135">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="66d7d-136">Erheblich erweiterte Funktionalität in der <xref:System.Type>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="66d7d-136">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="66d7d-137">Bessere Unterstützung für die Deserialisierung von Ausnahmeobjekten durch Hinzufügen eines Ausnahmekonstruktors mit den Parametern <xref:System.Runtime.Serialization.SerializationInfo> und <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="66d7d-137">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="66d7d-138">Unterstützung für .NET Framework-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="66d7d-138">Support for .NET Framework libraries</span></span>

<span data-ttu-id="66d7d-139">Die überwiegende Mehrheit von Bibliotheken wird eher für das .NET Framework als für den .NET Standard entworfen.</span><span class="sxs-lookup"><span data-stu-id="66d7d-139">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="66d7d-140">Die meisten Aufrufe in diesen Bibliotheken gelten jedoch für APIs, die im .NET Standard 2.0 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="66d7d-140">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="66d7d-141">Ab .NET Standard 2.0 können Sie mithilfe eines [Kompatibilitätsshims](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification) von einer .NET Standard-Bibliothek auf .NET Framework-Bibliotheken zugreifen.</span><span class="sxs-lookup"><span data-stu-id="66d7d-141">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span></span> <span data-ttu-id="66d7d-142">Diese Kompatibilitätsebene ist transparent für Entwickler – Sie müssen keine besondere Maßnahme ergreifen, um von .NET Framework-Bibliotheken zu profitieren.</span><span class="sxs-lookup"><span data-stu-id="66d7d-142">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="66d7d-143">Die einzige Anforderung besteht darin, dass die von der .NET Framework-Klassenbibliothek aufgerufenen APIs im .NET Standard 2.0 enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="66d7d-143">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="66d7d-144">Unterstützung für Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66d7d-144">Support for Visual Basic</span></span>

<span data-ttu-id="66d7d-145">Sie können jetzt .NET Standard-Bibliotheken in Visual Basic entwickeln.</span><span class="sxs-lookup"><span data-stu-id="66d7d-145">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="66d7d-146">Für Visual Basic-Entwickler, die Visual Studio 2017 Version 15.3 oder höher mit installierter .NET Core-Workload verwenden, enthält Visual Studio jetzt eine Vorlage für die .NET Standard-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="66d7d-146">For Visual Basic developers using Visual Studio 2017 version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="66d7d-147">Visual Basic-Entwickler, die andere Entwicklungstools und -umgebungen verwenden, können den Befehl [dotnet new](../../core/tools/dotnet-new.md) verwenden, um ein Projekt für die .NET Standard-Bibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="66d7d-147">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="66d7d-148">Weitere Informationen finden Sie unter [Toolunterstützung für .NET Standard-Bibliotheken](#tooling-support-for-net-standard-libraries).</span><span class="sxs-lookup"><span data-stu-id="66d7d-148">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="66d7d-149">Toolunterstützung für .NET Standard-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="66d7d-149">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="66d7d-150">Mit der Veröffentlichung von .NET Core 2.0 und .NET Standard 2.0 enthalten sowohl Visual Studio 2017 als auch die [.NET Core-Befehlszeilenschnittstelle (CLI)](../../core/tools/index.md) Toolunterstützung für die Erstellung von .NET Standard-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="66d7d-150">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="66d7d-151">Wenn Sie Visual Studio mit der Workload für die **plattformübergreifende .NET Core-Entwicklung** installieren, können Sie ein .NET Standard 2.0-Bibliotheksprojekt mithilfe einer Projektvorlage wie in der folgenden Abbildung veranschaulicht erstellen:</span><span class="sxs-lookup"><span data-stu-id="66d7d-151">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="66d7d-152">C#</span><span class="sxs-lookup"><span data-stu-id="66d7d-152">C#</span></span>](#tab/csharp)

![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-cs.png)

<span data-ttu-id="66d7d-154">Wenn Sie die .NET Core-CLI verwenden, erstellt der folgende [dotnet new](../../core/tools/dotnet-new.md)-Befehl ein Klassenbibliotheksprojekt für .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="66d7d-154">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib
```

# <a name="visual-basictabvb"></a>[<span data-ttu-id="66d7d-155">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66d7d-155">Visual Basic</span></span>](#tab/vb)

![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-vb.png)

<span data-ttu-id="66d7d-157">Wenn Sie die .NET Core-CLI verwenden, erstellt der folgende [dotnet new](../../core/tools/dotnet-new.md)-Befehl ein Klassenbibliotheksprojekt für .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="66d7d-157">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="66d7d-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66d7d-158">See also</span></span>

- [<span data-ttu-id="66d7d-159">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="66d7d-159">.NET Standard</span></span>](../net-standard.md)
- [<span data-ttu-id="66d7d-160">Introducing .NET Standard (Einführung in .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="66d7d-160">Introducing .NET Standard</span></span>](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)
