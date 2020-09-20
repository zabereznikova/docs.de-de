---
ms.openlocfilehash: 48d2f1b5fa2eced30d3c9fb65804268904f11ab8
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065062"
---
### <a name="unicode-category-changed-for-some-latin-1-characters"></a><span data-ttu-id="4551c-101">Geänderte Unicode-Kategorie für einige Zeichen in Lateinisch-1</span><span class="sxs-lookup"><span data-stu-id="4551c-101">Unicode category changed for some Latin-1 characters</span></span>

<span data-ttu-id="4551c-102"><xref:System.Char>-Methoden geben nun die richtige Unicode-Kategorie für Zeichen im Bereich Lateinisch-1 zurück.</span><span class="sxs-lookup"><span data-stu-id="4551c-102"><xref:System.Char> methods now return the correct Unicode category for characters in the Latin-1 range.</span></span> <span data-ttu-id="4551c-103">Die Kategorie entspricht der des Unicode-Standards.</span><span class="sxs-lookup"><span data-stu-id="4551c-103">The category matches that of the Unicode standard.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4551c-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4551c-104">Change description</span></span>

<span data-ttu-id="4551c-105">In früheren Versionen von .NET verwendeten <xref:System.Char>-Methoden eine feste Liste mit Unicode-Kategorien für Zeichen im Bereich Lateinisch-1.</span><span class="sxs-lookup"><span data-stu-id="4551c-105">In previous .NET versions, <xref:System.Char> methods used a fixed list of Unicode categories for characters in the Latin-1 range.</span></span> <span data-ttu-id="4551c-106">Im Unicode-Standard wurden jedoch seit der Implementierung dieser APIs die Kategorien für einige dieser Zeichen geändert, was zu Abweichungen führte.</span><span class="sxs-lookup"><span data-stu-id="4551c-106">However, the Unicode standard has changed the categories of some of these characters since those APIs were implemented, creating a discrepancy.</span></span> <span data-ttu-id="4551c-107">Außerdem gab es Unterschiede zwischen <xref:System.Char> und <xref:System.Globalization.CharUnicodeInfo>-APIs, die dem Unicode-Standard folgen.</span><span class="sxs-lookup"><span data-stu-id="4551c-107">In addition, there was also a discrepancy between <xref:System.Char> and <xref:System.Globalization.CharUnicodeInfo> APIs, which follow the Unicode standard.</span></span> <span data-ttu-id="4551c-108">Ab .NET 5.0 verwenden <xref:System.Char>-Methoden für alle Zeichen die dem Unicode-Standard entsprechende Unicode-Kategorie und geben auch diese zurück.</span><span class="sxs-lookup"><span data-stu-id="4551c-108">In .NET 5.0 and later versions, <xref:System.Char> methods use and return the Unicode category that matches the Unicode standard for all characters.</span></span>

<span data-ttu-id="4551c-109">In der folgenden Tabelle sind die Zeichen aufgeführt, deren Unicode-Kategorie sich in .NET 5.0 geändert hat:</span><span class="sxs-lookup"><span data-stu-id="4551c-109">The following table shows the characters whose Unicode categories have changed in .NET 5.0:</span></span>

| <span data-ttu-id="4551c-110">Zeichen</span><span class="sxs-lookup"><span data-stu-id="4551c-110">Character</span></span>    | <span data-ttu-id="4551c-111">Unicode-Kategorie</span><span class="sxs-lookup"><span data-stu-id="4551c-111">Unicode category</span></span><br><span data-ttu-id="4551c-112">in früheren .NET-Versionen</span><span class="sxs-lookup"><span data-stu-id="4551c-112">in previous .NET versions</span></span> | <span data-ttu-id="4551c-113">Unicode-Kategorie</span><span class="sxs-lookup"><span data-stu-id="4551c-113">Unicode category</span></span><br><span data-ttu-id="4551c-114">in .NET 5.0 und höher</span><span class="sxs-lookup"><span data-stu-id="4551c-114">in .NET 5.0 and later versions</span></span> |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| <span data-ttu-id="4551c-115">§ (\u00a7)</span><span class="sxs-lookup"><span data-stu-id="4551c-115">§ (\u00a7)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="4551c-116">ª (\u00aa)</span><span class="sxs-lookup"><span data-stu-id="4551c-116">ª (\u00aa)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |
| <span data-ttu-id="4551c-117">SHY (\u00ad)</span><span class="sxs-lookup"><span data-stu-id="4551c-117">SHY (\u00ad)</span></span> | `DashPunctuation`                             | `Format`                                           |
| <span data-ttu-id="4551c-118">¶ (\u00b6)</span><span class="sxs-lookup"><span data-stu-id="4551c-118">¶ (\u00b6)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="4551c-119">º (\u00ba)</span><span class="sxs-lookup"><span data-stu-id="4551c-119">º (\u00ba)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |

#### <a name="version-introduced"></a><span data-ttu-id="4551c-120">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="4551c-120">Version introduced</span></span>

<span data-ttu-id="4551c-121">.NET 5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="4551c-121">.NET 5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4551c-122">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="4551c-122">Recommended action</span></span>

<span data-ttu-id="4551c-123">Wenn Sie über Code verfügen, der die Unicode-Zeichenkategorie mithilfe der Klasse <xref:System.Char> abruft und davon ausgeht, dass die Kategorie sich nie ändert, müssen Sie diesen möglicherweise aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4551c-123">If you have any code that gets the Unicode character category by using the <xref:System.Char> class and assumes the category will never change, you may need to update it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4551c-124">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="4551c-124">Reason for change</span></span>

<span data-ttu-id="4551c-125">Diese Änderung wurde vorgenommen, damit die vom Typ <xref:System.Char> zurückgegebenen Kategorien sowohl dem Unicode-Standard als auch dem Typ <xref:System.Globalization.CharUnicodeInfo> entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4551c-125">This change was made so that the categories returned by the <xref:System.Char> type are consistent with both the Unicode standard and the <xref:System.Globalization.CharUnicodeInfo> type.</span></span>

#### <a name="category"></a><span data-ttu-id="4551c-126">Kategorie</span><span class="sxs-lookup"><span data-stu-id="4551c-126">Category</span></span>

- <span data-ttu-id="4551c-127">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="4551c-127">Core .NET libraries</span></span>
- <span data-ttu-id="4551c-128">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="4551c-128">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4551c-129">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4551c-129">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

<span data-ttu-id="4551c-130">Darüber hinaus sind von dieser Änderung alle Klassen betroffen, die beim Abrufen der Unicode-Zeichenkategorie von <xref:System.Char> abhängen, z. B. <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="4551c-130">Additionally, any class that depends on <xref:System.Char> to obtain the Unicode character category, for example, <xref:System.Text.RegularExpressions.Regex>, is affected by this change.</span></span>

<!--

#### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

-->
