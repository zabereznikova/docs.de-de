---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802545"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="6558a-101">Von der WPF-Rechtschreibprüfung ausgelöste ObjectDisposedException-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="6558a-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6558a-102">Details</span><span class="sxs-lookup"><span data-stu-id="6558a-102">Details</span></span>|<span data-ttu-id="6558a-103">WPF-Anwendungen stürzen beim Beenden der Anwendung gelegentlich ab. Dabei löst die Rechtschreibprüfung die Ausnahme <xref:System.ObjectDisposedException?displayProperty=name> aus.</span><span class="sxs-lookup"><span data-stu-id="6558a-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="6558a-104">Dies wurde in WPF für .NET Framework 4.7 behoben, indem die Ausnahme ordnungsgemäß verarbeitet wird. Dadurch wird sichergestellt, dass die Anwendungen nicht mehr beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="6558a-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="6558a-105">Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6558a-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="6558a-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6558a-106">Suggestion</span></span>|<span data-ttu-id="6558a-107">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="6558a-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="6558a-108">`Scope`</span><span class="sxs-lookup"><span data-stu-id="6558a-108">Scope</span></span>|<span data-ttu-id="6558a-109">Edge</span><span class="sxs-lookup"><span data-stu-id="6558a-109">Edge</span></span>|
|<span data-ttu-id="6558a-110">Version</span><span class="sxs-lookup"><span data-stu-id="6558a-110">Version</span></span>|<span data-ttu-id="6558a-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="6558a-111">4.6.1</span></span>|
|<span data-ttu-id="6558a-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6558a-112">Type</span></span>|<span data-ttu-id="6558a-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6558a-113">Runtime</span></span>|
