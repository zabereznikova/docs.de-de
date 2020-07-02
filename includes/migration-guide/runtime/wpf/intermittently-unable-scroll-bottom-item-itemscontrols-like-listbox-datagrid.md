---
ms.openlocfilehash: b92dc8a1c48e83846c3d9a1d86e66629f31b7722
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622020"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="23c6b-101">Das Scrollen zum untersten Eintrag in ItemsControl-Steuerelementen (z.B. ListBox und DataGrid) war bei Verwendung von benutzerdefinierten DataTemplates zeitweilig nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="23c6b-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

#### <a name="details"></a><span data-ttu-id="23c6b-102">Details</span><span class="sxs-lookup"><span data-stu-id="23c6b-102">Details</span></span>

<span data-ttu-id="23c6b-103">In einigen Fällen verursacht ein Fehler in .NET Framework 4.5, dass ItemsControl-Steuerelemente (z.B. <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName> und <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>) nicht zum untersten Eintrag scrollen, wenn benutzerdefinierte DataTemplates verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23c6b-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="23c6b-104">Wenn der Vorgang ein zweites Mal versucht wird (nachdem wieder nach oben gescrollt wurde), funktioniert es entsprechend.</span><span class="sxs-lookup"><span data-stu-id="23c6b-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="23c6b-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="23c6b-105">Suggestion</span></span>

<span data-ttu-id="23c6b-106">Dieses Problem wurde in .NET Framework 4.5.2 behoben und kann durch ein Upgrade auf diese (oder eine höhere) Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="23c6b-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="23c6b-107">Alternativ können Benutzer weiterhin Scrolleisten in diesen Auflistungen ziehen, wobei sie es möglicherweise zweimal versuchen müssen, bis der Vorgang erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="23c6b-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>

| <span data-ttu-id="23c6b-108">name</span><span class="sxs-lookup"><span data-stu-id="23c6b-108">Name</span></span>    | <span data-ttu-id="23c6b-109">Wert</span><span class="sxs-lookup"><span data-stu-id="23c6b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="23c6b-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="23c6b-110">Scope</span></span>   |<span data-ttu-id="23c6b-111">Gering</span><span class="sxs-lookup"><span data-stu-id="23c6b-111">Minor</span></span>|
|<span data-ttu-id="23c6b-112">Version</span><span class="sxs-lookup"><span data-stu-id="23c6b-112">Version</span></span>|<span data-ttu-id="23c6b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="23c6b-113">4.5</span></span>|
|<span data-ttu-id="23c6b-114">Typ</span><span class="sxs-lookup"><span data-stu-id="23c6b-114">Type</span></span>|<span data-ttu-id="23c6b-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="23c6b-115">Runtime</span></span>|
