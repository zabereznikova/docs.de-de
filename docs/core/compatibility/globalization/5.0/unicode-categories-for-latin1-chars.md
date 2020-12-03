---
title: 'Breaking Change: Geänderte Unicode-Kategorie für einige Zeichen in Lateinisch-1'
description: Hier erfahren Sie mehr über den Globalisierungs-Breaking-Change in .NET 5.0, bei dem Char-Methoden nun die richtige Unicode-Kategorie für Zeichen aus dem Zeichenbereich „Latin-1“ zurückgeben.
ms.date: 04/07/2020
ms.openlocfilehash: 8bd093a89857c83921fc0bf987348b529f74ce68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759558"
---
# <a name="unicode-category-changed-for-some-latin-1-characters"></a><span data-ttu-id="ac0ba-103">Geänderte Unicode-Kategorie für einige Zeichen in Lateinisch-1</span><span class="sxs-lookup"><span data-stu-id="ac0ba-103">Unicode category changed for some Latin-1 characters</span></span>

<span data-ttu-id="ac0ba-104"><xref:System.Char>-Methoden geben nun die richtige Unicode-Kategorie für Zeichen im Bereich Lateinisch-1 zurück.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-104"><xref:System.Char> methods now return the correct Unicode category for characters in the Latin-1 range.</span></span> <span data-ttu-id="ac0ba-105">Die Kategorie entspricht der des Unicode-Standards.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-105">The category matches that of the Unicode standard.</span></span>

## <a name="change-description"></a><span data-ttu-id="ac0ba-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ac0ba-106">Change description</span></span>

<span data-ttu-id="ac0ba-107">In früheren Versionen von .NET verwendeten <xref:System.Char>-Methoden eine feste Liste mit Unicode-Kategorien für Zeichen im Bereich Lateinisch-1.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-107">In previous .NET versions, <xref:System.Char> methods used a fixed list of Unicode categories for characters in the Latin-1 range.</span></span> <span data-ttu-id="ac0ba-108">Im Unicode-Standard wurden jedoch seit der Implementierung dieser APIs die Kategorien für einige dieser Zeichen geändert, was zu Abweichungen führte.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-108">However, the Unicode standard has changed the categories of some of these characters since those APIs were implemented, creating a discrepancy.</span></span> <span data-ttu-id="ac0ba-109">Außerdem gab es Unterschiede zwischen <xref:System.Char> und <xref:System.Globalization.CharUnicodeInfo>-APIs, die dem Unicode-Standard folgen.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-109">In addition, there was also a discrepancy between <xref:System.Char> and <xref:System.Globalization.CharUnicodeInfo> APIs, which follow the Unicode standard.</span></span> <span data-ttu-id="ac0ba-110">Ab .NET 5.0 verwenden <xref:System.Char>-Methoden für alle Zeichen die dem Unicode-Standard entsprechende Unicode-Kategorie und geben auch diese zurück.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-110">In .NET 5.0 and later versions, <xref:System.Char> methods use and return the Unicode category that matches the Unicode standard for all characters.</span></span>

<span data-ttu-id="ac0ba-111">In der folgenden Tabelle sind die Zeichen aufgeführt, deren Unicode-Kategorie sich in .NET 5.0 geändert hat:</span><span class="sxs-lookup"><span data-stu-id="ac0ba-111">The following table shows the characters whose Unicode categories have changed in .NET 5.0:</span></span>

| <span data-ttu-id="ac0ba-112">Zeichen</span><span class="sxs-lookup"><span data-stu-id="ac0ba-112">Character</span></span>    | <span data-ttu-id="ac0ba-113">Unicode-Kategorie</span><span class="sxs-lookup"><span data-stu-id="ac0ba-113">Unicode category</span></span><br><span data-ttu-id="ac0ba-114">in früheren .NET-Versionen</span><span class="sxs-lookup"><span data-stu-id="ac0ba-114">in previous .NET versions</span></span> | <span data-ttu-id="ac0ba-115">Unicode-Kategorie</span><span class="sxs-lookup"><span data-stu-id="ac0ba-115">Unicode category</span></span><br><span data-ttu-id="ac0ba-116">in .NET 5.0 und höher</span><span class="sxs-lookup"><span data-stu-id="ac0ba-116">in .NET 5.0 and later versions</span></span> |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| <span data-ttu-id="ac0ba-117">§ (\u00a7)</span><span class="sxs-lookup"><span data-stu-id="ac0ba-117">§ (\u00a7)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="ac0ba-118">ª (\u00aa)</span><span class="sxs-lookup"><span data-stu-id="ac0ba-118">ª (\u00aa)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |
| <span data-ttu-id="ac0ba-119">SHY (\u00ad)</span><span class="sxs-lookup"><span data-stu-id="ac0ba-119">SHY (\u00ad)</span></span> | `DashPunctuation`                             | `Format`                                           |
| <span data-ttu-id="ac0ba-120">¶ (\u00b6)</span><span class="sxs-lookup"><span data-stu-id="ac0ba-120">¶ (\u00b6)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="ac0ba-121">º (\u00ba)</span><span class="sxs-lookup"><span data-stu-id="ac0ba-121">º (\u00ba)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |

## <a name="version-introduced"></a><span data-ttu-id="ac0ba-122">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ac0ba-122">Version introduced</span></span>

<span data-ttu-id="ac0ba-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ac0ba-123">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ac0ba-124">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="ac0ba-124">Recommended action</span></span>

<span data-ttu-id="ac0ba-125">Wenn Sie über Code verfügen, der die Unicode-Zeichenkategorie mithilfe der Klasse <xref:System.Char> abruft und davon ausgeht, dass die Kategorie sich nie ändert, müssen Sie diesen möglicherweise aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-125">If you have any code that gets the Unicode character category by using the <xref:System.Char> class and assumes the category will never change, you may need to update it.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ac0ba-126">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ac0ba-126">Reason for change</span></span>

<span data-ttu-id="ac0ba-127">Diese Änderung wurde vorgenommen, damit die vom Typ <xref:System.Char> zurückgegebenen Kategorien sowohl dem Unicode-Standard als auch dem Typ <xref:System.Globalization.CharUnicodeInfo> entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-127">This change was made so that the categories returned by the <xref:System.Char> type are consistent with both the Unicode standard and the <xref:System.Globalization.CharUnicodeInfo> type.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ac0ba-128">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ac0ba-128">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

<span data-ttu-id="ac0ba-129">Darüber hinaus sind von dieser Änderung alle Klassen betroffen, die beim Abrufen der Unicode-Zeichenkategorie von <xref:System.Char> abhängen, z. B. <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="ac0ba-129">Additionally, any class that depends on <xref:System.Char> to obtain the Unicode character category, for example, <xref:System.Text.RegularExpressions.Regex>, is affected by this change.</span></span>

<!--

### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

### Category

- Core .NET libraries
- Globalization
-
-->
