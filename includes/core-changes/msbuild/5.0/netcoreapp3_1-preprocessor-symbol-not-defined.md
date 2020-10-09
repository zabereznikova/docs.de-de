---
ms.openlocfilehash: de35df21d1887bc95a3106edba312c53daad8b68
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654736"
---
### <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a><span data-ttu-id="f83f1-101">Das NETCOREAPP3_1-Präprozessorsymbol ist nicht definiert, wenn .NET 5 als Zielversion verwendet wird</span><span class="sxs-lookup"><span data-stu-id="f83f1-101">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>

<span data-ttu-id="f83f1-102">In .NET 5.0 RC2 und höher definieren Projekte keine Präprozessorsymbole mehr für frühere Versionen, sondern nur für die Zielversion.</span><span class="sxs-lookup"><span data-stu-id="f83f1-102">In .NET 5.0 RC2 and later versions, projects no longer define preprocessor symbols for earlier versions, but only for the version that they target.</span></span> <span data-ttu-id="f83f1-103">Dieses Verhalten entspricht dem von .NET Core 1.0 bis .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f83f1-103">This is the same behavior as .NET Core 1.0 - 3.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f83f1-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f83f1-104">Version introduced</span></span>

<span data-ttu-id="f83f1-105">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="f83f1-105">5.0 RC2</span></span>

#### <a name="change-description"></a><span data-ttu-id="f83f1-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="f83f1-106">Change description</span></span>

<span data-ttu-id="f83f1-107">In .NET 5.0 Preview 7 bis .NET 5.0 RC1 definieren Projekte für `net5.0` die Präprozessorsymbole `NETCOREAPP3_1` und `NET5_0`.</span><span class="sxs-lookup"><span data-stu-id="f83f1-107">In .NET 5.0 preview 7 through RC1, projects that target `net5.0` define both `NETCOREAPP3_1` and `NET5_0` preprocessor symbols.</span></span> <span data-ttu-id="f83f1-108">Durch diesen Behavior Change sind [Symbole für die bedingte Kompilierung ab .NET 5.0 kumulativ](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span><span class="sxs-lookup"><span data-stu-id="f83f1-108">The intent behind this behavior change was that starting with .NET 5.0, conditional compilation [symbols would be cumulative](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).</span></span>

<span data-ttu-id="f83f1-109">Ab .NET 5.0 RC2 definieren Projekte nur Symbole für die Zielframeworkmoniker, nicht jedoch für frühere Versionen.</span><span class="sxs-lookup"><span data-stu-id="f83f1-109">In .NET 5.0 RC2 and later, projects only define symbols for the target framework monikers (TFM) that it targets and not for any earlier versions.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f83f1-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="f83f1-110">Reason for change</span></span>

<span data-ttu-id="f83f1-111">Die Änderung aus Preview 7 wurde aufgrund von Kundenfeedback zurückgenommen.</span><span class="sxs-lookup"><span data-stu-id="f83f1-111">The change from preview 7 was reverted due to customer feedback.</span></span> <span data-ttu-id="f83f1-112">Kunden waren überrascht und verwirrt, dass sie Symbole für frühere Versionen definieren mussten, und einige hielten dies für einen Fehler im C#-Compiler.</span><span class="sxs-lookup"><span data-stu-id="f83f1-112">Defining symbols for earlier versions surprised and confused customers, and some assumed it was a bug in the C# compiler.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f83f1-113">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="f83f1-113">Recommended action</span></span>

<span data-ttu-id="f83f1-114">Stellen Sie sicher, dass Ihre `#if`-Logik nicht von einer vorhandenen `NETCOREAPP3_1`-Definition ausgeht, wenn das Projekt auf `net5.0` oder höher ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="f83f1-114">Make sure that your `#if` logic doesn't assume that `NETCOREAPP3_1` is defined when the project targets `net5.0` or higher.</span></span> <span data-ttu-id="f83f1-115">Es sollte stattdessen davon ausgegangen werden, dass `NETCOREAPP3_1` nur definiert ist, wenn das Projekt explizit auf `netcoreapp3.1` ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="f83f1-115">Instead, assume that `NETCOREAPP3_1` is only defined when the project explicitly targets `netcoreapp3.1`.</span></span>

<span data-ttu-id="f83f1-116">Wenn Ihr Projekt beispielsweise .NET Core 2.1 und .NET Core 3.1 als Zielversionen verwendet und Sie APIs aufrufen, die in .NET Core 3.1 eingeführt wurden, sollte Ihre `#if`-Logik folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="f83f1-116">For example, if your project multitargets for .NET Core 2.1 and .NET Core 3.1 and you call APIs that were introduced in .NET Core 3.1, your `#if` logic should look as follows:</span></span>

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

#### <a name="category"></a><span data-ttu-id="f83f1-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="f83f1-117">Category</span></span>

<span data-ttu-id="f83f1-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="f83f1-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f83f1-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f83f1-119">Affected APIs</span></span>

<span data-ttu-id="f83f1-120">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="f83f1-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
