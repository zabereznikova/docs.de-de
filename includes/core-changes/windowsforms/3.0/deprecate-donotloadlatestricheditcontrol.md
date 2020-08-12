---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556176"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="6805e-101">Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="6805e-101">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="6805e-102">Der mit .NET Framework 4.7.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.UseLegacyImages` wird in Windows Forms unter .NET Core oder .NET 5.0 oder höher nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6805e-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6805e-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6805e-103">Change description</span></span>

<span data-ttu-id="6805e-104">In .NET Framework 4.6.2 und früheren Versionen instanziiert das <xref:System.Windows.Forms.RichTextBox>-Steuerelement das Win32 RichEdit-Steuerelement v3.0, und bei Anwendungen für .NET Framework 4.7.1 instanziiert das <xref:System.Windows.Forms.RichTextBox>-Steuerelement RichEdit v4.1 (in *msftedit.dll*).</span><span class="sxs-lookup"><span data-stu-id="6805e-104">In .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control instantiates the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control instantiates RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="6805e-105">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` wurde eingeführt, damit Anwendungen für .NET Framework 4.7.1 und höhere Versionen das neue RichEdit v4.1-Steuerelement ignorieren und stattdessen das alte RichEdit v3-Steuerelement verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6805e-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="6805e-106">In .NET Core und .NET 5.0 oder höheren Versionen wird der `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl`-Switch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6805e-106">In .NET Core and .NET 5.0 and later versions, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="6805e-107">Es werden nur neue Versionen des <xref:System.Windows.Forms.RichTextBox>-Steuerelements unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6805e-107">Only new versions of the <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6805e-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6805e-108">Version introduced</span></span>

<span data-ttu-id="6805e-109">3.0</span><span class="sxs-lookup"><span data-stu-id="6805e-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6805e-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="6805e-110">Recommended action</span></span>

<span data-ttu-id="6805e-111">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="6805e-111">Remove the switch.</span></span> <span data-ttu-id="6805e-112">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6805e-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="6805e-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="6805e-113">Category</span></span>

<span data-ttu-id="6805e-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6805e-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6805e-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6805e-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
