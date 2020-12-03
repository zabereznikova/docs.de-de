---
title: 'Breaking Change: IntPtr und UIntPtr implementieren IFormattable'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den IntPtr und UIntPtr nun IFormattable implementieren.
ms.date: 11/01/2020
ms.openlocfilehash: 0684652cdc2b8cf1d237074263bf0809082b0dcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759526"
---
# <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="ed434-103">IntPtr und UIntPtr implementieren IFormattable</span><span class="sxs-lookup"><span data-stu-id="ed434-103">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="ed434-104"><xref:System.IntPtr> und <xref:System.UIntPtr> implementieren jetzt <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="ed434-104"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="ed434-105">Funktionen, die auf <xref:System.IFormattable>-Unterstützung überprüfen, können nun unterschiedliche Ergebnisse für diese Typen zurückgeben, da sie einen Formatbezeichner und eine Kultur übergeben können.</span><span class="sxs-lookup"><span data-stu-id="ed434-105">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

## <a name="change-description"></a><span data-ttu-id="ed434-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ed434-106">Change description</span></span>

<span data-ttu-id="ed434-107">In früheren Versionen von .NET haben <xref:System.IntPtr> und <xref:System.UIntPtr> <xref:System.IFormattable> nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="ed434-107">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="ed434-108">Funktionen, die auf <xref:System.IFormattable> überprüfen, können auf das einfache Aufrufen von <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> oder <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType> zurückfallen, was bedeutet, dass Formatbezeichner und Kulturen nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="ed434-108">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="ed434-109">In .NET 5.0 und höheren Versionen implementieren <xref:System.IntPtr> und <xref:System.UIntPtr> <xref:System.IFormattable>.</span><span class="sxs-lookup"><span data-stu-id="ed434-109">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="ed434-110">Funktionen, die auf <xref:System.IFormattable>-Unterstützung überprüfen, können nun unterschiedliche Ergebnisse für diese Typen zurückgeben, da sie einen Formatbezeichner und eine Kultur übergeben können.</span><span class="sxs-lookup"><span data-stu-id="ed434-110">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="ed434-111">Diese Änderung wirkt sich z. B. auf Szenarien wie interpolierte Zeichenfolgen und <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> aus.</span><span class="sxs-lookup"><span data-stu-id="ed434-111">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ed434-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ed434-112">Reason for change</span></span>

<span data-ttu-id="ed434-113"><xref:System.IntPtr> und <xref:System.UIntPtr> weisen jetzt Sprachunterstützung in C# durch die Schlüsselwörter `nint` und `nuint` auf.</span><span class="sxs-lookup"><span data-stu-id="ed434-113"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="ed434-114">Die Unterstützungstypen wurden aktualisiert, um Nähe der Parität (sofern möglich) mit Funktionen bereitzustellen, die von anderen primitiven Typen wie <xref:System.Int32?displayProperty=nameWithType> zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ed434-114">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ed434-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ed434-115">Version introduced</span></span>

<span data-ttu-id="ed434-116">5.0</span><span class="sxs-lookup"><span data-stu-id="ed434-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ed434-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="ed434-117">Recommended action</span></span>

<span data-ttu-id="ed434-118">Wenn Sie nicht möchten, dass bei der Anzeige von Werten dieser Art ein Formatbezeichner oder eine benutzerdefinierte Kultur verwendet wird, können Sie die <xref:System.IntPtr.ToString?displayProperty=nameWithType>- und <xref:System.UIntPtr.ToString?displayProperty=nameWithType>-Überladungen von `ToString()` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ed434-118">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ed434-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ed434-119">Affected APIs</span></span>

<span data-ttu-id="ed434-120">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="ed434-120">Not detectable via API analysis.</span></span>

<!--

### Category

Core .NET libraries

### Affected APIs

Not detectable via API analysis.

-->
