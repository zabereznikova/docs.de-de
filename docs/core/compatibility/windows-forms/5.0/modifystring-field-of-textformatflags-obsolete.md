---
title: 'Breaking Change: TextFormatFlags.ModifyString ist veraltet'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den das Feld „TextFormatFlags.ModifyString“ als Warnung als veraltet gilt.
ms.date: 11/05/2020
ms.openlocfilehash: 83dca65a770ccdcd5ce48bb669f5122dc2d5ad77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759377"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="4e76c-103">TextFormatFlags.ModifyString ist veraltet</span><span class="sxs-lookup"><span data-stu-id="4e76c-103">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="4e76c-104">Das Feld <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> ist als Warnung veraltet und kann in einer zukünftigen .NET-Version entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="4e76c-104">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

## <a name="change-description"></a><span data-ttu-id="4e76c-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4e76c-105">Change description</span></span>

<span data-ttu-id="4e76c-106">In früheren .NET-Versionen ist das Enumerationsfeld <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> nicht als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4e76c-106">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="4e76c-107">In .NET 5.0 oder höher ist es als Warnung als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4e76c-107">In .NET 5.0 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="4e76c-108">Dieses Feld kann in einer zukünftigen .NET-Version entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="4e76c-108">This field may be removed in a future .NET version.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4e76c-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="4e76c-109">Reason for change</span></span>

<span data-ttu-id="4e76c-110">Durch die Übergabe einer Zeichenfolge an <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> mit <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> wird die Zeichenfolge in einigen Situationen geändert.</span><span class="sxs-lookup"><span data-stu-id="4e76c-110">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="4e76c-111">Dieses Verhalten unterbricht die Unveränderlichkeitszusage der Zeichenfolge und kann zu einer schwerwiegenden Beschädigung des Runtimestatus von .NET führen.</span><span class="sxs-lookup"><span data-stu-id="4e76c-111">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4e76c-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="4e76c-112">Version introduced</span></span>

<span data-ttu-id="4e76c-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="4e76c-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4e76c-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="4e76c-114">Recommended action</span></span>

<span data-ttu-id="4e76c-115">Aktualisieren Sie Code, der auf <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> basiert.</span><span class="sxs-lookup"><span data-stu-id="4e76c-115">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4e76c-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4e76c-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->
