---
title: 'Breaking Change: Das NETCOREAPP3_1-Präprozessorsymbol ist nicht definiert, wenn .NET 5 als Zielversion verwendet wird'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Projekte keine Präprozessorsymbole mehr für frühere Versionen definieren.
ms.date: 09/17/2020
ms.openlocfilehash: 61a5e4fce258d2be3d584318e154bb752b88ebe1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759401"
---
# <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a><span data-ttu-id="ffffa-103">Das NETCOREAPP3_1-Präprozessorsymbol ist nicht definiert, wenn .NET 5 als Zielversion verwendet wird</span><span class="sxs-lookup"><span data-stu-id="ffffa-103">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>

<span data-ttu-id="ffffa-104">In .NET 5.0 RC2 und höher definieren Projekte keine Präprozessorsymbole mehr für frühere Versionen, sondern nur für die Zielversion.</span><span class="sxs-lookup"><span data-stu-id="ffffa-104">In .NET 5.0 RC2 and later versions, projects no longer define preprocessor symbols for earlier versions, but only for the version that they target.</span></span> <span data-ttu-id="ffffa-105">Dieses Verhalten entspricht dem von .NET Core 1.0 bis .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="ffffa-105">This is the same behavior as .NET Core 1.0 - 3.1.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ffffa-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ffffa-106">Version introduced</span></span>

<span data-ttu-id="ffffa-107">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="ffffa-107">5.0 RC2</span></span>

## <a name="change-description"></a><span data-ttu-id="ffffa-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ffffa-108">Change description</span></span>

<span data-ttu-id="ffffa-109">In .NET 5.0 Preview 7 bis .NET 5.0 RC1 definieren Projekte für `net5.0` die Präprozessorsymbole `NETCOREAPP3_1` und `NET5_0`.</span><span class="sxs-lookup"><span data-stu-id="ffffa-109">In .NET 5.0 preview 7 through RC1, projects that target `net5.0` define both `NETCOREAPP3_1` and `NET5_0` preprocessor symbols.</span></span> <span data-ttu-id="ffffa-110">Durch diesen Behavior Change sind [Symbole für die bedingte Kompilierung ab .NET 5.0 kumulativ](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span><span class="sxs-lookup"><span data-stu-id="ffffa-110">The intent behind this behavior change was that starting with .NET 5.0, conditional compilation [symbols would be cumulative](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span></span>

<span data-ttu-id="ffffa-111">Ab .NET 5.0 RC2 definieren Projekte nur Symbole für die Zielframeworkmoniker, nicht jedoch für frühere Versionen.</span><span class="sxs-lookup"><span data-stu-id="ffffa-111">In .NET 5.0 RC2 and later, projects only define symbols for the target framework monikers (TFM) that it targets and not for any earlier versions.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ffffa-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ffffa-112">Reason for change</span></span>

<span data-ttu-id="ffffa-113">Die Änderung aus Preview 7 wurde aufgrund von Kundenfeedback zurückgenommen.</span><span class="sxs-lookup"><span data-stu-id="ffffa-113">The change from preview 7 was reverted due to customer feedback.</span></span> <span data-ttu-id="ffffa-114">Kunden waren überrascht und verwirrt, dass sie Symbole für frühere Versionen definieren mussten, und einige hielten dies für einen Fehler im C#-Compiler.</span><span class="sxs-lookup"><span data-stu-id="ffffa-114">Defining symbols for earlier versions surprised and confused customers, and some assumed it was a bug in the C# compiler.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ffffa-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="ffffa-115">Recommended action</span></span>

<span data-ttu-id="ffffa-116">Stellen Sie sicher, dass Ihre `#if`-Logik nicht von einer vorhandenen `NETCOREAPP3_1`-Definition ausgeht, wenn das Projekt auf `net5.0` oder höher ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ffffa-116">Make sure that your `#if` logic doesn't assume that `NETCOREAPP3_1` is defined when the project targets `net5.0` or higher.</span></span> <span data-ttu-id="ffffa-117">Es sollte stattdessen davon ausgegangen werden, dass `NETCOREAPP3_1` nur definiert ist, wenn das Projekt explizit auf `netcoreapp3.1` ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="ffffa-117">Instead, assume that `NETCOREAPP3_1` is only defined when the project explicitly targets `netcoreapp3.1`.</span></span>

<span data-ttu-id="ffffa-118">Wenn Ihr Projekt beispielsweise .NET Core 2.1 und .NET Core 3.1 als Zielversionen verwendet und Sie APIs aufrufen, die in .NET Core 3.1 eingeführt wurden, sollte Ihre `#if`-Logik folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="ffffa-118">For example, if your project multitargets for .NET Core 2.1 and .NET Core 3.1 and you call APIs that were introduced in .NET Core 3.1, your `#if` logic should look as follows:</span></span>

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

## <a name="affected-apis"></a><span data-ttu-id="ffffa-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ffffa-119">Affected APIs</span></span>

<span data-ttu-id="ffffa-120">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="ffffa-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
