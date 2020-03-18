---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67856929"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="babe9-101">Besseres KeyTips-Verhalten in WPF</span><span class="sxs-lookup"><span data-stu-id="babe9-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="babe9-102">Details</span><span class="sxs-lookup"><span data-stu-id="babe9-102">Details</span></span>|<span data-ttu-id="babe9-103">Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht.</span><span class="sxs-lookup"><span data-stu-id="babe9-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="babe9-104">Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend.</span><span class="sxs-lookup"><span data-stu-id="babe9-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="babe9-105">Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="babe9-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="babe9-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="babe9-106">Suggestion</span></span>|<span data-ttu-id="babe9-107">–</span><span class="sxs-lookup"><span data-stu-id="babe9-107">N/A</span></span>|
|<span data-ttu-id="babe9-108">`Scope`</span><span class="sxs-lookup"><span data-stu-id="babe9-108">Scope</span></span>|<span data-ttu-id="babe9-109">Edge</span><span class="sxs-lookup"><span data-stu-id="babe9-109">Edge</span></span>|
|<span data-ttu-id="babe9-110">Version</span><span class="sxs-lookup"><span data-stu-id="babe9-110">Version</span></span>|<span data-ttu-id="babe9-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="babe9-111">4.7.2</span></span>|
|<span data-ttu-id="babe9-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="babe9-112">Type</span></span>|<span data-ttu-id="babe9-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="babe9-113">Runtime</span></span>|
