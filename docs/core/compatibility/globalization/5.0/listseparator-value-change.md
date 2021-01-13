---
title: 'Breaking Change: Änderung des TextInfo.ListSeparator-Werts'
description: Hier efahren Sie mehr über die Breaking Change bei .NET 5.0, bei der der Standardwert von TextInfo.ListSeparator zwischen den Versionen 5.0 und 5.0.1 geändert wurde.
ms.date: 12/10/2020
ms.openlocfilehash: 720d46c1908bcd70812f575a90f580470dbc7f32
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596330"
---
# <a name="textinfolistseparator-values-changed"></a><span data-ttu-id="513e3-103">Änderung der TextInfo.ListSeparator-Werte</span><span class="sxs-lookup"><span data-stu-id="513e3-103">TextInfo.ListSeparator values changed</span></span>

<span data-ttu-id="513e3-104">Die <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Standardwerte für verschiedene Kulturen haben sich bei allen Betriebssystemen geändert.</span><span class="sxs-lookup"><span data-stu-id="513e3-104">The default <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for different cultures have changed on all operating systems.</span></span>

## <a name="change-description"></a><span data-ttu-id="513e3-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="513e3-105">Change description</span></span>

<span data-ttu-id="513e3-106">Im Rahmen der [Umstellung von NLS- auf ICU-Bibliotheken](icu-globalization-api.md) wurden in .NET 5.0.0 die Standardwerte für <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> für verschiedene Kulturen unter Windows geändert.</span><span class="sxs-lookup"><span data-stu-id="513e3-106">In .NET 5.0.0, as part of the [switch from NLS to ICU libraries](icu-globalization-api.md), the default <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for different cultures changed on Windows.</span></span> <span data-ttu-id="513e3-107">Dezimaltrennzeichenwerte, die von International Components for Unicode (ICU) abgerufen wurden, wurden als <xref:System.Globalization.TextInfo.ListSeparator>-Werte verwendet.</span><span class="sxs-lookup"><span data-stu-id="513e3-107">Decimal separator values, obtained from International Components for Unicode (ICU), were used as the <xref:System.Globalization.TextInfo.ListSeparator> values.</span></span> <span data-ttu-id="513e3-108">Unter Linux und macOS wurden keine Änderungen an <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werten vorgenommen, d. h. sie verwenden weiterhin Dezimaltrennzeichenwerte.</span><span class="sxs-lookup"><span data-stu-id="513e3-108">On Linux and macOS, there was no change in <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values; that is, they continued to use decimal separator values.</span></span>

<span data-ttu-id="513e3-109">Für alle Betriebssysteme in .NET 5.0.1 und höheren Versionen entsprechen die Werte für <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> den Werten, die von NLS abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="513e3-109">For all operating systems in .NET 5.0.1 and later versions, the values for <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> are equivalent to the values that would be obtained from NLS.</span></span> <span data-ttu-id="513e3-110">Für Windows bedeutet dies, dass die Werte den Werten in .NET Framework und .NET Core 1.0–3.1 entsprechen.</span><span class="sxs-lookup"><span data-stu-id="513e3-110">For Windows, this means the values are equivalent to what they were in .NET Framework and .NET Core 1.0 - 3.1.</span></span> <span data-ttu-id="513e3-111">Für Linux und macOS stimmen die <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werte nun mit den <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werten für Windows überein.</span><span class="sxs-lookup"><span data-stu-id="513e3-111">For Linux and macOS, the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values now match the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for Windows.</span></span>

<span data-ttu-id="513e3-112">Die folgende Tabelle enthält die Änderungen für <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werte.</span><span class="sxs-lookup"><span data-stu-id="513e3-112">The following table summarizes the changes for <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values.</span></span>

| | <span data-ttu-id="513e3-113">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="513e3-113">.NET Framework</span></span><br/><span data-ttu-id="513e3-114">.NET Core 1.0–3.1</span><span class="sxs-lookup"><span data-stu-id="513e3-114">.NET Core 1.0 - 3.1</span></span> | <span data-ttu-id="513e3-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="513e3-115">.NET 5.0</span></span> | <span data-ttu-id="513e3-116">.NET 5.0.1</span><span class="sxs-lookup"><span data-stu-id="513e3-116">.NET 5.0.1</span></span> |
-|-|-|-
| <span data-ttu-id="513e3-117">**Windows**</span><span class="sxs-lookup"><span data-stu-id="513e3-117">**Windows**</span></span> | <span data-ttu-id="513e3-118">Aus NLS abrufen</span><span class="sxs-lookup"><span data-stu-id="513e3-118">Obtain from NLS</span></span> | <span data-ttu-id="513e3-119">Dezimaltrennzeichen aus ICU</span><span class="sxs-lookup"><span data-stu-id="513e3-119">Decimal separator from ICU.</span></span><br/><span data-ttu-id="513e3-120">Kann zurück zu NLS wechseln</span><span class="sxs-lookup"><span data-stu-id="513e3-120">Can switch back to NLS.</span></span> | <span data-ttu-id="513e3-121">Entspricht NLS</span><span class="sxs-lookup"><span data-stu-id="513e3-121">Equivalent to NLS</span></span> |
| <span data-ttu-id="513e3-122">**Linux und macOS**</span><span class="sxs-lookup"><span data-stu-id="513e3-122">**Linux and macOS**</span></span> | <span data-ttu-id="513e3-123">Dezimaltrennzeichen aus ICU</span><span class="sxs-lookup"><span data-stu-id="513e3-123">Decimal separator from ICU</span></span> | <span data-ttu-id="513e3-124">Dezimaltrennzeichen aus ICU</span><span class="sxs-lookup"><span data-stu-id="513e3-124">Decimal separator from ICU</span></span> | <span data-ttu-id="513e3-125">Entspricht NLS</span><span class="sxs-lookup"><span data-stu-id="513e3-125">Equivalent to NLS</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="513e3-126">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="513e3-126">Version introduced</span></span>

<span data-ttu-id="513e3-127">5.0.1</span><span class="sxs-lookup"><span data-stu-id="513e3-127">5.0.1</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="513e3-128">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="513e3-128">Reason for change</span></span>

<span data-ttu-id="513e3-129">Entwickler haben gemeldet, dass sie die <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Eigenschaft beim Parsen von durch Trennzeichen getrennte Dateien (CSV) verwenden und die neuen <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werte diesen Parservorgang unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="513e3-129">Developers reported that they use the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> property when parsing comma-separated value (CSV) files, and the new <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values broke that parsing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="513e3-130">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="513e3-130">Recommended action</span></span>

<span data-ttu-id="513e3-131">Wenn Ihr Code auf den vorherigen Dezimaltrennzeichen basiert, können Sie die gewünschten <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werte hartkodieren.</span><span class="sxs-lookup"><span data-stu-id="513e3-131">If your code relies on the previous decimal separator values, you can hardcode the desired <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="513e3-132">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="513e3-132">Affected APIs</span></span>

- <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=fullName>

<!--

#### Category

- Globalization

### Affected APIs

- `P:System.Globalization.TextInfo.ListSeparator`

-->
