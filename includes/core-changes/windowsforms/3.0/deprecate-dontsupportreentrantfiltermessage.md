---
ms.openlocfilehash: 95aa243a5790d4201c7871e617dbe4ccafb7c1a1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556180"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="e0b5c-101">Kompatibilitätsoption DontSupportReentrantFilterMessage wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="e0b5c-101">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="e0b5c-102">Der mit .NET Framework 4.6.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` wird in Windows Forms unter .NET Core und .NET 5.0 oder höher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core and .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e0b5c-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e0b5c-103">Change description</span></span>

<span data-ttu-id="e0b5c-104">Ab .NET Framework 4.6.1 werden mit dem Kompatibilitätsswitch `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` mögliche <xref:System.IndexOutOfRangeException>-Ausnahmen behandelt, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>-Nachricht mit einer benutzerdefinierten <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>-Implementierung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="e0b5c-105">Weitere Informationen finden Sie unter [Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span><span class="sxs-lookup"><span data-stu-id="e0b5c-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="e0b5c-106">In .NET Core und .NET 5.0 oder höher wird der `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`-Switch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-106">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e0b5c-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e0b5c-107">Version introduced</span></span>

<span data-ttu-id="e0b5c-108">3.0</span><span class="sxs-lookup"><span data-stu-id="e0b5c-108">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e0b5c-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="e0b5c-109">Recommended action</span></span>

<span data-ttu-id="e0b5c-110">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-110">Remove the switch.</span></span> <span data-ttu-id="e0b5c-111">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="e0b5c-112">Kategorie</span><span class="sxs-lookup"><span data-stu-id="e0b5c-112">Category</span></span>

<span data-ttu-id="e0b5c-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0b5c-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e0b5c-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e0b5c-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
