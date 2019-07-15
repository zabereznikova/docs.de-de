---
ms.openlocfilehash: d7cf32eb369e2607ee540d7188cc680b9506c261
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67856929"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="ea0b1-101">Besseres KeyTips-Verhalten in WPF</span><span class="sxs-lookup"><span data-stu-id="ea0b1-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ea0b1-102">Details</span><span class="sxs-lookup"><span data-stu-id="ea0b1-102">Details</span></span>|<span data-ttu-id="ea0b1-103">Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht.</span><span class="sxs-lookup"><span data-stu-id="ea0b1-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="ea0b1-104">Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend.</span><span class="sxs-lookup"><span data-stu-id="ea0b1-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="ea0b1-105">Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="ea0b1-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="ea0b1-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ea0b1-106">Suggestion</span></span>|<span data-ttu-id="ea0b1-107">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="ea0b1-107">N/A</span></span>|
|<span data-ttu-id="ea0b1-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="ea0b1-108">Scope</span></span>|<span data-ttu-id="ea0b1-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ea0b1-109">Edge</span></span>|
|<span data-ttu-id="ea0b1-110">Version</span><span class="sxs-lookup"><span data-stu-id="ea0b1-110">Version</span></span>|<span data-ttu-id="ea0b1-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="ea0b1-111">4.7.2</span></span>|
|<span data-ttu-id="ea0b1-112">Typ</span><span class="sxs-lookup"><span data-stu-id="ea0b1-112">Type</span></span>|<span data-ttu-id="ea0b1-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ea0b1-113">Runtime</span></span>|

