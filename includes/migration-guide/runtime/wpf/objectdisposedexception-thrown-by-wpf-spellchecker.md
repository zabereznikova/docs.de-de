---
ms.openlocfilehash: 9d09f598538b9d5ee3f995d6281b8eb4b2668050
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761299"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="26e14-101">Von der WPF-Rechtschreibprüfung ausgelöste ObjectDisposedException-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="26e14-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="26e14-102">Details</span><span class="sxs-lookup"><span data-stu-id="26e14-102">Details</span></span>|<span data-ttu-id="26e14-103">WPF-Anwendungen stürzen beim Beenden der Anwendung gelegentlich ab. Dabei löst die Rechtschreibprüfung die Ausnahme <xref:System.ObjectDisposedException?displayProperty=name> aus.</span><span class="sxs-lookup"><span data-stu-id="26e14-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="26e14-104">Dies wurde in WPF für .NET Framework 4.7 behoben, indem die Ausnahme ordnungsgemäß verarbeitet wird. Dadurch wird sichergestellt, dass die Anwendungen nicht mehr beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="26e14-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="26e14-105">Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="26e14-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="26e14-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="26e14-106">Suggestion</span></span>|<span data-ttu-id="26e14-107">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="26e14-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="26e14-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="26e14-108">Scope</span></span>|<span data-ttu-id="26e14-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="26e14-109">Edge</span></span>|
|<span data-ttu-id="26e14-110">Version</span><span class="sxs-lookup"><span data-stu-id="26e14-110">Version</span></span>|<span data-ttu-id="26e14-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="26e14-111">4.6.1</span></span>|
|<span data-ttu-id="26e14-112">Typ</span><span class="sxs-lookup"><span data-stu-id="26e14-112">Type</span></span>|<span data-ttu-id="26e14-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="26e14-113">Runtime</span></span>|

