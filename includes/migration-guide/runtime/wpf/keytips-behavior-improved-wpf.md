---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497623"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="eb8aa-101">Besseres KeyTips-Verhalten in WPF</span><span class="sxs-lookup"><span data-stu-id="eb8aa-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="eb8aa-102">Details</span><span class="sxs-lookup"><span data-stu-id="eb8aa-102">Details</span></span>

<span data-ttu-id="eb8aa-103">Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht.</span><span class="sxs-lookup"><span data-stu-id="eb8aa-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="eb8aa-104">Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend.</span><span class="sxs-lookup"><span data-stu-id="eb8aa-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="eb8aa-105">Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="eb8aa-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eb8aa-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="eb8aa-106">Suggestion</span></span>

<span data-ttu-id="eb8aa-107">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="eb8aa-107">N/A</span></span>

| <span data-ttu-id="eb8aa-108">name</span><span class="sxs-lookup"><span data-stu-id="eb8aa-108">Name</span></span>    | <span data-ttu-id="eb8aa-109">Wert</span><span class="sxs-lookup"><span data-stu-id="eb8aa-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eb8aa-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="eb8aa-110">Scope</span></span>   |<span data-ttu-id="eb8aa-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="eb8aa-111">Edge</span></span>|
|<span data-ttu-id="eb8aa-112">Version</span><span class="sxs-lookup"><span data-stu-id="eb8aa-112">Version</span></span>|<span data-ttu-id="eb8aa-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="eb8aa-113">4.7.2</span></span>|
|<span data-ttu-id="eb8aa-114">Typ</span><span class="sxs-lookup"><span data-stu-id="eb8aa-114">Type</span></span>|<span data-ttu-id="eb8aa-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="eb8aa-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="eb8aa-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="eb8aa-116">Affected APIs</span></span>

<span data-ttu-id="eb8aa-117">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="eb8aa-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
