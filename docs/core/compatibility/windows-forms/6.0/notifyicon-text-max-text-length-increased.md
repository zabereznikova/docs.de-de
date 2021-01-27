---
title: 'Breaking Change: Maximale Textlänge für NotifyIcon.Text erhöht'
description: Erfahren Sie mehr über den Breaking Change in .NET 6.0, wo die maximale Textlänge für die Eigenschaft „NotifyIcon.Text“ zugenommen hat.
ms.date: 01/19/2021
ms.openlocfilehash: 0029556f3ec2795fb079575b329e7fbd187d486f
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98617976"
---
# <a name="notifyicontext-maximum-text-length-increased"></a><span data-ttu-id="b50d0-103">Maximale Textlänge für NotifyIcon.Text erhöht</span><span class="sxs-lookup"><span data-stu-id="b50d0-103">NotifyIcon.Text maximum text length increased</span></span>

<span data-ttu-id="b50d0-104">Die maximal zulässige Textlänge für die <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType>-Eigenschaft wurde von 63 auf 127 Zeichen angehoben.</span><span class="sxs-lookup"><span data-stu-id="b50d0-104">The maximum text length allowed for the <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> property increased from 63 to 127.</span></span>

## <a name="change-description"></a><span data-ttu-id="b50d0-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="b50d0-105">Change description</span></span>

<span data-ttu-id="b50d0-106">In früheren .NET-Versionen betrug die maximal zulässige Textlänge für die <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType>-Eigenschaft 63 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b50d0-106">In previous .NET versions, the maximum text length allowed for the <xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=nameWithType> property is 63 characters.</span></span> <span data-ttu-id="b50d0-107">Ab .NET 6.0 beträgt die maximal zulässige Textlänge 127 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b50d0-107">Starting in .NET 6.0, the maximum allowed text length is 127 characters.</span></span> <span data-ttu-id="b50d0-108">In jeder Version wird eine <xref:System.ArgumentException>-Klasse ausgelöst, wenn Sie versuchen, einen Wert festzulegen, der den Grenzwert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="b50d0-108">In any version, an <xref:System.ArgumentException> is thrown when you attempt to set a value that's longer than the limit.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b50d0-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b50d0-109">Reason for change</span></span>

<span data-ttu-id="b50d0-110">Die maximal zulässige Textlänge wurde in Übereinstimmung mit der [zugrunde liegenden Windows-API](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080) erweitert.</span><span class="sxs-lookup"><span data-stu-id="b50d0-110">The maximum allowed text length was increased to be in line with the [underlying Windows API](/windows/win32/api/shellapi/ns-shellapi-notifyicondataw#nif_showtip-0x00000080).</span></span> <span data-ttu-id="b50d0-111">Die Windows-API wurde in Windows 2000 aktualisiert, aber aufgrund von Kompatibilitätsgründen wurde die Größenbeschränkung für diese Eigenschaft in .NET Framework nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b50d0-111">The Windows API was updated in Windows 2000, but due to compatibility reasons, the size limit for this property wasn't updated in .NET Framework.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b50d0-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b50d0-112">Version introduced</span></span>

<span data-ttu-id="b50d0-113">.NET Core 6.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="b50d0-113">.NET 6.0 Preview 1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b50d0-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="b50d0-114">Recommended action</span></span>

<span data-ttu-id="b50d0-115">Überprüfen Sie Ihren Code, und lockern Sie ggf. vorhandene Wächterbedingungen.</span><span class="sxs-lookup"><span data-stu-id="b50d0-115">Review your code and relax any existing guard conditions, if necessary.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b50d0-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b50d0-116">Affected APIs</span></span>

<xref:System.Windows.Forms.NotifyIcon.Text?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.NotifyIcon.Text`

### Category

Windows Forms

-->
