---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621270"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="bf4ac-101">Besseres KeyTips-Verhalten in WPF</span><span class="sxs-lookup"><span data-stu-id="bf4ac-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="bf4ac-102">Details</span><span class="sxs-lookup"><span data-stu-id="bf4ac-102">Details</span></span>

<span data-ttu-id="bf4ac-103">Das Keytips-Verhalten wurde so geändert, dass es dem Verhalten von Microsoft Word und Windows Explorer entspricht.</span><span class="sxs-lookup"><span data-stu-id="bf4ac-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="bf4ac-104">Indem überprüft wird, ob der Keytip-Status aktiviert ist oder nicht, wenn <xref:System.Windows.Input.KeyEventArgs.SystemKey> (insbesondere <xref:System.Windows.Input.Key> oder <xref:System.Windows.Input.Key.F11>) gedrückt wird, behandelt WPF die Keytip-Tasten entsprechend.</span><span class="sxs-lookup"><span data-stu-id="bf4ac-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="bf4ac-105">Keytips verwerfen nun ein Menü, auch wenn es mit der Maus geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="bf4ac-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bf4ac-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="bf4ac-106">Suggestion</span></span>

<span data-ttu-id="bf4ac-107">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="bf4ac-107">N/A</span></span>

| <span data-ttu-id="bf4ac-108">name</span><span class="sxs-lookup"><span data-stu-id="bf4ac-108">Name</span></span>    | <span data-ttu-id="bf4ac-109">Wert</span><span class="sxs-lookup"><span data-stu-id="bf4ac-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bf4ac-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="bf4ac-110">Scope</span></span>   |<span data-ttu-id="bf4ac-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bf4ac-111">Edge</span></span>|
|<span data-ttu-id="bf4ac-112">Version</span><span class="sxs-lookup"><span data-stu-id="bf4ac-112">Version</span></span>|<span data-ttu-id="bf4ac-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="bf4ac-113">4.7.2</span></span>|
|<span data-ttu-id="bf4ac-114">Typ</span><span class="sxs-lookup"><span data-stu-id="bf4ac-114">Type</span></span>|<span data-ttu-id="bf4ac-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bf4ac-115">Runtime</span></span>|
