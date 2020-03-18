---
ms.openlocfilehash: 3272dc562981269b868df4ca9d3a5806918aba5f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937053"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="66878-101">Kompatibilitätsoption DontSupportReentrantFilterMessage wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="66878-101">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="66878-102">Der mit .NET Framework 4.6.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66878-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="66878-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="66878-103">Change description</span></span>

<span data-ttu-id="66878-104">Ab .NET Framework 4.6.1 werden mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` mögliche <xref:System.IndexOutOfRangeException>-Ausnahmen behandelt, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>-Nachricht mit einer benutzerdefinierten <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="66878-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="66878-105">Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span><span class="sxs-lookup"><span data-stu-id="66878-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="66878-106">In .NET Core wird der Switch `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66878-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="66878-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="66878-107">Version introduced</span></span>

<span data-ttu-id="66878-108">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="66878-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="66878-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="66878-109">Recommended action</span></span>

<span data-ttu-id="66878-110">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="66878-110">Remove the switch.</span></span> <span data-ttu-id="66878-111">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="66878-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="66878-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="66878-112">Category</span></span>

<span data-ttu-id="66878-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66878-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="66878-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="66878-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
