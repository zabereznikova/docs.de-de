---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236133"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="072e8-101">Besseres KeyTips-Verhalten in WPF</span><span class="sxs-lookup"><span data-stu-id="072e8-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="072e8-102">Details</span><span class="sxs-lookup"><span data-stu-id="072e8-102">Details</span></span>|<span data-ttu-id="072e8-103">Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht.</span><span class="sxs-lookup"><span data-stu-id="072e8-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="072e8-104">Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend.</span><span class="sxs-lookup"><span data-stu-id="072e8-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="072e8-105">Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="072e8-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="072e8-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="072e8-106">Suggestion</span></span>|<span data-ttu-id="072e8-107">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="072e8-107">N/A</span></span>|
|<span data-ttu-id="072e8-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="072e8-108">Scope</span></span>|<span data-ttu-id="072e8-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="072e8-109">Edge</span></span>|
|<span data-ttu-id="072e8-110">Version</span><span class="sxs-lookup"><span data-stu-id="072e8-110">Version</span></span>|<span data-ttu-id="072e8-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="072e8-111">4.7.2</span></span>|
|<span data-ttu-id="072e8-112">Typ</span><span class="sxs-lookup"><span data-stu-id="072e8-112">Type</span></span>|<span data-ttu-id="072e8-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="072e8-113">Runtime</span></span>|
