---
title: Was ist neu in .NET Standard
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="ff60c-102">Was ist neu in .NET Standard</span><span class="sxs-lookup"><span data-stu-id="ff60c-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="ff60c-103">.NET Standard ist eine formale Spezifikation, die einen mit Versionsangabe Satz von APIs definiert, der Implementierungen von .NET verfügbar sein müssen, die mit dieser Version des Standards zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ff60c-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="ff60c-104">.NET Standard ist auf Bibliotheksentwickler ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="ff60c-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="ff60c-105">Eine Bibliothek, die auf eine .NET Standardversion kann auf die Implementierung einer .NET Framework, die .NET Core oder Xamarin verwendet werden, diese Version des Standards unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff60c-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="ff60c-106">Die neueste Version von .NET Standard lautet 2.0.</span><span class="sxs-lookup"><span data-stu-id="ff60c-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="ff60c-107">Es ist mit dem .NET Core 2.0 SDK sowie mit Visual Studio 2017 Version 15.3 Arbeitslast .NET Core installiert.</span><span class="sxs-lookup"><span data-stu-id="ff60c-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="ff60c-108">Unterstützte .NET Implementierungen</span><span class="sxs-lookup"><span data-stu-id="ff60c-108">Supported .NET implementations</span></span>

<span data-ttu-id="ff60c-109">Der standardmäßige .NET 2.0 wird durch folgenden Implementierungen .NET unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ff60c-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="ff60c-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ff60c-110">.NET Core 2.0</span></span>
- <span data-ttu-id="ff60c-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="ff60c-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="ff60c-112">Mono 5.4</span><span class="sxs-lookup"><span data-stu-id="ff60c-112">Mono 5.4</span></span>
- <span data-ttu-id="ff60c-113">Xamarin.iOS 10.14</span><span class="sxs-lookup"><span data-stu-id="ff60c-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="ff60c-114">Xamarin.Mac 3.8</span><span class="sxs-lookup"><span data-stu-id="ff60c-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="ff60c-115">Xamarin.Android 8.0</span><span class="sxs-lookup"><span data-stu-id="ff60c-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="ff60c-116">Universelle Windows-Plattform 10.0.16299</span><span class="sxs-lookup"><span data-stu-id="ff60c-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="ff60c-117">Was ist neu in .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="ff60c-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="ff60c-118">Der standardmäßige .NET 2.0 umfasst die folgenden neuen Features:</span><span class="sxs-lookup"><span data-stu-id="ff60c-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="ff60c-119">**Ein völlig erweiterten Satz von APIs**</span><span class="sxs-lookup"><span data-stu-id="ff60c-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="ff60c-120">Bis Version 1.6 enthalten den standardmäßigen .NET eine vergleichsweise kleine Teilmenge von APIs.</span><span class="sxs-lookup"><span data-stu-id="ff60c-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="ff60c-121">Zu den ausgeschlossen wurden Sie viele APIs, die häufig in .NET Framework oder Xamarin verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ff60c-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="ff60c-122">Dadurch wird die Entwicklung, komplizierter, da sie erfordert, dass Entwickler geeigneter Ersatz für vertraut APIs, finden Wenn sie entwickeln Anwendungen und Bibliotheken, die auf mehrere Implementierungen von .NET abzielen.</span><span class="sxs-lookup"><span data-stu-id="ff60c-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="ff60c-123">Der standardmäßige .NET 2.0 für Kennwortfilter durch Hinzufügen von mehr als 20.000 weitere APIs, die als in standardmäßigen .NET 1.6, die die vorherige Version des Standards verfügbar waren.</span><span class="sxs-lookup"><span data-stu-id="ff60c-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="ff60c-124">Eine Liste der APIs, die den standardmäßigen .NET 2.0 hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 Vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="ff60c-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="ff60c-125">Einige der Virtual Machine Additions auf dem <xref:System> Namespace in .NET 2.0-Standard enthalten:</span><span class="sxs-lookup"><span data-stu-id="ff60c-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="ff60c-126">Unterstützung für die <xref:System.AppDomain> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff60c-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="ff60c-127">Bessere Unterstützung für das Arbeiten mit Arrays von zusätzliche Elemente in der <xref:System.Array> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff60c-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="ff60c-128">Bessere Unterstützung für das Arbeiten mit Attributen aus zusätzliche Elemente in der <xref:System.Attribute> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff60c-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="ff60c-129">Eine bessere Leistung "Kalender" Support und weitere Formatierungsoptionen für <xref:System.DateTime> Werte.</span><span class="sxs-lookup"><span data-stu-id="ff60c-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="ff60c-130">Zusätzliche <xref:System.Decimal> Rundung Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="ff60c-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="ff60c-131">Zusätzliche Funktionen in der <xref:System.Environment> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff60c-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="ff60c-132">Erweiterte Kontrolle über die Garbage Collection durch die <xref:System.GC> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff60c-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="ff60c-133">Erweiterte Unterstützung für den Vergleich von Zeichenfolgen, Enumeration und Normalisierung in die <xref:System.String> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff60c-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="ff60c-134">Unterstützung für die Sommerzeit Anpassungen und Übergangszeiten in der <xref:System.TimeZoneInfo.AdjustmentRule> und <xref:System.TimeZoneInfo.TransitionTime> Klassen.</span><span class="sxs-lookup"><span data-stu-id="ff60c-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="ff60c-135">Funktionalität in erheblich verbessert die <xref:System.Type> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff60c-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="ff60c-136">Bessere Unterstützung für die Deserialisierung von Ausnahmeobjekten durch Hinzufügen eines Ausnahme Konstruktors mit <xref:System.Runtime.Serialization.SerializationInfo> und <xref:System.Runtime.Serialization.StreamingContext> Parameter.</span><span class="sxs-lookup"><span data-stu-id="ff60c-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="ff60c-137">**Unterstützung für .NET Framework-Bibliotheken**</span><span class="sxs-lookup"><span data-stu-id="ff60c-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="ff60c-138">Der überwiegende Teil der Bibliotheken als Ziel .NET Framework, sondern die .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ff60c-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="ff60c-139">Allerdings sind die meisten Aufrufe in diesen Bibliotheken APIs, die in standardmäßigen .NET 2.0 enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ff60c-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="ff60c-140">Beginnend mit .NET Standard 2.0, können Sie .NET Framework-Bibliotheken aus einer .NET Standard-Bibliothek zugreifen, mithilfe einer [Kompatibilität Shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span><span class="sxs-lookup"><span data-stu-id="ff60c-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="ff60c-141">Dieser Kompatibilitätsebene ist für Entwickler transparent; Sie müssen nichts Unternehmen, um .NET Framework-Bibliotheken zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="ff60c-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="ff60c-142">Die einzige Anforderung ist, dass die APIs, die von der .NET Framework-Klassenbibliothek aufgerufen in standardmäßigen .NET 2.0 enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="ff60c-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="ff60c-143">**Unterstützung für Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="ff60c-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="ff60c-144">Sie können jetzt .NET Standardbibliotheken in Visual Basic entwickeln.</span><span class="sxs-lookup"><span data-stu-id="ff60c-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="ff60c-145">Für Visual Basic-Entwickler, die mit Visual Studio 2017 Version 15.3 oder später mit der .NET Core-arbeitsauslastung installiert enthält Visual Studio nun eine Vorlage für die Klassenbibliothek von .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ff60c-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="ff60c-146">Für Visual Basic-Entwickler, die andere Entwicklungstools und -Umgebungen verwenden, können Sie die [Dotnet neue](../../core/tools/dotnet-new.md) Befehl zum Erstellen eines Projekts für .NET-Standardbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ff60c-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="ff60c-147">Weitere Informationen finden Sie unter der [Toolunterstützung ist für .NET Standardbibliotheken](#tooling).</span><span class="sxs-lookup"><span data-stu-id="ff60c-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="ff60c-148"><a name="tooling" />**Tools zur Unterstützung für .NET-Standardbibliotheken**</span><span class="sxs-lookup"><span data-stu-id="ff60c-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="ff60c-149">Mit der Version von .NET Core 2.0 und .NET Standard 2.0, sowohl Visual Studio 2017 und [.NET Core Befehlszeilenschnittstelle (CLI)](../../core/tools/index.md) tooling-Unterstützung für das Erstellen von .NET Standardbibliotheken enthalten.</span><span class="sxs-lookup"><span data-stu-id="ff60c-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="ff60c-150">Bei der Installation von Visual Studio mit der **.NET Core plattformübergreifende Entwicklung** arbeitsauslastung können Sie ein Klassenbibliotheksprojekt .NET Standard 2.0 erstellen, indem Sie mithilfe einer Projektvorlage, wie die folgende Abbildung zeigt.</span><span class="sxs-lookup"><span data-stu-id="ff60c-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="ff60c-151">C#</span><span class="sxs-lookup"><span data-stu-id="ff60c-151">C#</span></span>](#tab/csharp)
![Fügen Sie neue .NET Standard-Bibliotheksprojekt hinzu.](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="ff60c-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff60c-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Fügen Sie neue .NET Standard-Bibliotheksprojekt hinzu.](./media/std-project-vb.png)
---

<span data-ttu-id="ff60c-155">Bei Verwendung der .NET Core CLI Folgendes [Dotnet neue](../../core/tools/dotnet-new.md) Befehl erstellt ein Klassenbibliotheksprojekt, das standardmäßige .NET 2.0 ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ff60c-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="ff60c-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff60c-156">See Also</span></span>
<span data-ttu-id="ff60c-157">[.NET Standard](../net-standard.md)
[Einführung in .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span><span class="sxs-lookup"><span data-stu-id="ff60c-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
