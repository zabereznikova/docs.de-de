---
title: Neuerungen in .NET Standard
description: In diesem Artikel werden neue Features und Verbesserungen zusammengefasst, die in jeder neuen Version von .NET Standard auffindbar sind.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 419988901923b890aaf0a540d155775214e62c52
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282099"
---
# <a name="whats-new-in-net-standard"></a><span data-ttu-id="c994c-103">Neuerungen in .NET Standard</span><span class="sxs-lookup"><span data-stu-id="c994c-103">What's new in .NET Standard</span></span>

<span data-ttu-id="c994c-104">.NET Standard ist eine formale Spezifikation, die mehrere APIs mit Versionsangabe definiert, die in .NET-Implementierungen verfügbar sein müssen, die dieser Version des Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c994c-104">.NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="c994c-105">.NET Standard ist auf Bibliotheksentwickler ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="c994c-105">.NET Standard is targeted at library developers.</span></span> <span data-ttu-id="c994c-106">Eine Bibliothek, die auf eine .NET Standard-Version abzielt, kann in jeder .NET Framework-, .NET Core- oder Xamarin-Implementierung verwendet werden, die diese Version des Standards unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c994c-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="c994c-107">.NET Standard ist in .NET Core SDK und auch in Visual Studio enthalten, wenn Sie die .NET Core-Workload wählen.</span><span class="sxs-lookup"><span data-stu-id="c994c-107">.NET Standard is included with the .NET Core SDK, as well as with Visual Studio when you select the .NET Core workload.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="c994c-108">Unterstützte .NET-Implementierungen</span><span class="sxs-lookup"><span data-stu-id="c994c-108">Supported .NET implementations</span></span>

<span data-ttu-id="c994c-109">.NET Standard 2.0 wird von den folgenden .NET-Implementierungen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c994c-109">.NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="c994c-110">.NET Core 2.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="c994c-110">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="c994c-111">.NET Framework 4.6.1 oder höher</span><span class="sxs-lookup"><span data-stu-id="c994c-111">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="c994c-112">Mono 5.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="c994c-112">Mono 5.4 or later</span></span>
- <span data-ttu-id="c994c-113">Xamarin.iOS 10.14 oder höher</span><span class="sxs-lookup"><span data-stu-id="c994c-113">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="c994c-114">Xamarin.Mac 3.8 oder höher</span><span class="sxs-lookup"><span data-stu-id="c994c-114">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="c994c-115">Xamarin.Android 8.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="c994c-115">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="c994c-116">Universal Windows Platform 10.0.16299 oder höher</span><span class="sxs-lookup"><span data-stu-id="c994c-116">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-net-standard-20"></a><span data-ttu-id="c994c-117">Neuerungen in .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="c994c-117">What's new in .NET Standard 2.0</span></span>

<span data-ttu-id="c994c-118">.NET Standard 2.0 umfasst folgende neue Features:</span><span class="sxs-lookup"><span data-stu-id="c994c-118">.NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="c994c-119">Ein umfassend erweiterter Satz von APIs</span><span class="sxs-lookup"><span data-stu-id="c994c-119">A vastly expanded set of APIs</span></span>

<span data-ttu-id="c994c-120">Bis einschließlich Version 1.6 enthielt .NET Standard eine vergleichsweise kleine Teilmenge von APIs.</span><span class="sxs-lookup"><span data-stu-id="c994c-120">Through version 1.6, .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="c994c-121">Nicht enthalten war eine Vielzahl von APIs, die häufig in .NET Framework oder Xamarin verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="c994c-121">Among those excluded were many APIs that were commonly used in .NET Framework or Xamarin.</span></span> <span data-ttu-id="c994c-122">Dies verkompliziert die Entwicklung, da Entwickler geeigneten Ersatz für vertraute APIs finden müssen, wenn sie Anwendungen und Bibliotheken für verschiedene .NET-Implementierungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c994c-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="c994c-123">In .NET Standard 2.0 besteht diese Einschränkung nicht mehr, da über 20.000 mehr APIs hinzugefügt wurden, als in .NET Standard 1.6, der vorherigen Version, verfügbar waren.</span><span class="sxs-lookup"><span data-stu-id="c994c-123">.NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="c994c-124">Eine Liste der APIs, die zu .NET Standard 2.0 hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="c994c-124">For a list of the APIs that have been added to .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="c994c-125">Im Folgenden finden Sie einige der neuen Features für den <xref:System>-Namespace im .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="c994c-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="c994c-126">Unterstützung für die <xref:System.AppDomain>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c994c-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="c994c-127">Bessere Unterstützung für die Arbeit mit Arrays dank zusätzlicher Member in der <xref:System.Array>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c994c-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="c994c-128">Bessere Unterstützung für die Arbeit mit Attributen dank zusätzlicher Member in der <xref:System.Attribute>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c994c-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="c994c-129">Bessere Kalenderunterstützung und zusätzliche Formatierungsoptionen für <xref:System.DateTime>-Werte.</span><span class="sxs-lookup"><span data-stu-id="c994c-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="c994c-130">Zusätzliche <xref:System.Decimal>-Rundungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="c994c-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="c994c-131">Zusätzliche Funktionen in der <xref:System.Environment>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c994c-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="c994c-132">Erweiterte Steuerung des Garbage Collector über die <xref:System.GC>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c994c-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="c994c-133">Erweiterte Unterstützung für Zeichenfolgenvergleich, Enumeration und Normalisierung in der <xref:System.String>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c994c-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="c994c-134">Unterstützung für Sommerzeitanpassungen und Übergangszeiten in den Klassen <xref:System.TimeZoneInfo.AdjustmentRule> und <xref:System.TimeZoneInfo.TransitionTime>.</span><span class="sxs-lookup"><span data-stu-id="c994c-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="c994c-135">Erheblich erweiterte Funktionalität in der <xref:System.Type>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c994c-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="c994c-136">Bessere Unterstützung für die Deserialisierung von Ausnahmeobjekten durch Hinzufügen eines Ausnahmekonstruktors mit den Parametern <xref:System.Runtime.Serialization.SerializationInfo> und <xref:System.Runtime.Serialization.StreamingContext>.</span><span class="sxs-lookup"><span data-stu-id="c994c-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="c994c-137">Unterstützung für .NET Framework-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="c994c-137">Support for .NET Framework libraries</span></span>

<span data-ttu-id="c994c-138">Viele Bibliotheken haben .NET Framework statt .NET Standard als Ziel.</span><span class="sxs-lookup"><span data-stu-id="c994c-138">Many libraries target .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="c994c-139">Die meisten Aufrufe in diesen Bibliotheken gelten jedoch für APIs, die in .NET Standard 2.0 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c994c-139">However, most of the calls in those libraries are to APIs that are included in .NET Standard 2.0.</span></span> <span data-ttu-id="c994c-140">Ab .NET Standard 2.0 können Sie mithilfe eines [Kompatibilitätsshims](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification) von einer .NET Standard-Bibliothek auf .NET Framework-Bibliotheken zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c994c-140">Starting with .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span></span> <span data-ttu-id="c994c-141">Diese Kompatibilitätsebene ist transparent für Entwickler – Sie müssen keine besondere Maßnahme ergreifen, um von .NET Framework-Bibliotheken zu profitieren.</span><span class="sxs-lookup"><span data-stu-id="c994c-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="c994c-142">Die einzige Anforderung besteht darin, dass die von der .NET Framework-Klassenbibliothek aufgerufenen APIs in .NET Standard 2.0 enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="c994c-142">The single requirement is that the APIs called by the .NET Framework class library must be included in .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="c994c-143">Unterstützung für Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c994c-143">Support for Visual Basic</span></span>

<span data-ttu-id="c994c-144">Sie können jetzt .NET Standard-Bibliotheken in Visual Basic entwickeln.</span><span class="sxs-lookup"><span data-stu-id="c994c-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="c994c-145">Visual Studio 2019 und Visual Studio 2017, Version 15.3 oder höher, mit installierter .NET Core-Workload enthalten jetzt eine Vorlage für die .NET Standard-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c994c-145">Visual Studio 2019 and Visual Studio 2017 version 15.3 or later with the .NET Core workload installed include a .NET Standard Class Library template.</span></span> <span data-ttu-id="c994c-146">Visual Basic-Entwickler, die andere Entwicklungstools und -umgebungen verwenden, können den Befehl [dotnet new](../../core/tools/dotnet-new.md) verwenden, um ein Projekt für die .NET Standard-Bibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c994c-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="c994c-147">Weitere Informationen finden Sie unter [Toolunterstützung für .NET Standard-Bibliotheken](#tooling-support-for-net-standard-libraries).</span><span class="sxs-lookup"><span data-stu-id="c994c-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="c994c-148">Toolunterstützung für .NET Standard-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="c994c-148">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="c994c-149">Mit der Veröffentlichung von .NET Core 2.0 und .NET Standard 2.0 enthalten sowohl Visual Studio 2017 als auch die [.NET Core-CLI](../../core/tools/index.md) Toolunterstützung für die Erstellung von .NET Standard-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="c994c-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core CLI](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="c994c-150">Wenn Sie Visual Studio mit der Workload für die **plattformübergreifende .NET Core-Entwicklung** installieren, können Sie ein .NET Standard 2.0-Bibliotheksprojekt mithilfe einer Projektvorlage wie in der folgenden Abbildung veranschaulicht erstellen:</span><span class="sxs-lookup"><span data-stu-id="c994c-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="c994c-151">C#</span><span class="sxs-lookup"><span data-stu-id="c994c-151">C#</span></span>](#tab/csharp)

![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-cs.png)

<span data-ttu-id="c994c-153">Wenn Sie die .NET Core-CLI verwenden, erstellt der folgende [dotnet new](../../core/tools/dotnet-new.md)-Befehl ein Klassenbibliotheksprojekt für .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="c994c-153">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib
```

# <a name="visual-basic"></a>[<span data-ttu-id="c994c-154">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c994c-154">Visual Basic</span></span>](#tab/vb)

![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-vb.png)

<span data-ttu-id="c994c-156">Wenn Sie die .NET Core-CLI verwenden, erstellt der folgende [dotnet new](../../core/tools/dotnet-new.md)-Befehl ein Klassenbibliotheksprojekt für .NET Standard 2.0:</span><span class="sxs-lookup"><span data-stu-id="c994c-156">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets .NET Standard 2.0:</span></span>

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="c994c-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c994c-157">See also</span></span>

- [<span data-ttu-id="c994c-158">.NET-Standard</span><span class="sxs-lookup"><span data-stu-id="c994c-158">.NET Standard</span></span>](../net-standard.md)
- [<span data-ttu-id="c994c-159">Introducing .NET Standard (Einführung in .NET Standard)</span><span class="sxs-lookup"><span data-stu-id="c994c-159">Introducing .NET Standard</span></span>](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)
