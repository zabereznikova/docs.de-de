---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621797"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="e5181-101">Von der WPF-Rechtschreibprüfung ausgelöste ObjectDisposedException-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="e5181-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="e5181-102">Details</span><span class="sxs-lookup"><span data-stu-id="e5181-102">Details</span></span>

<span data-ttu-id="e5181-103">WPF-Anwendungen stürzen beim Beenden der Anwendung gelegentlich ab. Dabei löst die Rechtschreibprüfung die Ausnahme <xref:System.ObjectDisposedException?displayProperty=fullName> aus.</span><span class="sxs-lookup"><span data-stu-id="e5181-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="e5181-104">Dies wurde in WPF für .NET Framework 4.7 behoben, indem die Ausnahme ordnungsgemäß verarbeitet wird. Dadurch wird sichergestellt, dass die Anwendungen nicht mehr beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="e5181-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="e5181-105">Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e5181-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e5181-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e5181-106">Suggestion</span></span>

<span data-ttu-id="e5181-107">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="e5181-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="e5181-108">name</span><span class="sxs-lookup"><span data-stu-id="e5181-108">Name</span></span>    | <span data-ttu-id="e5181-109">Wert</span><span class="sxs-lookup"><span data-stu-id="e5181-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e5181-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="e5181-110">Scope</span></span>   |<span data-ttu-id="e5181-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e5181-111">Edge</span></span>|
|<span data-ttu-id="e5181-112">Version</span><span class="sxs-lookup"><span data-stu-id="e5181-112">Version</span></span>|<span data-ttu-id="e5181-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e5181-113">4.6.1</span></span>|
|<span data-ttu-id="e5181-114">Typ</span><span class="sxs-lookup"><span data-stu-id="e5181-114">Type</span></span>|<span data-ttu-id="e5181-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e5181-115">Runtime</span></span>|
