---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496602"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="d863c-101">Von der WPF-Rechtschreibprüfung ausgelöste ObjectDisposedException-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="d863c-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="d863c-102">Details</span><span class="sxs-lookup"><span data-stu-id="d863c-102">Details</span></span>

<span data-ttu-id="d863c-103">WPF-Anwendungen stürzen beim Beenden der Anwendung gelegentlich ab. Dabei löst die Rechtschreibprüfung die Ausnahme <xref:System.ObjectDisposedException?displayProperty=fullName> aus.</span><span class="sxs-lookup"><span data-stu-id="d863c-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="d863c-104">Dies wurde in WPF für .NET Framework 4.7 behoben, indem die Ausnahme ordnungsgemäß verarbeitet wird. Dadurch wird sichergestellt, dass die Anwendungen nicht mehr beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="d863c-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="d863c-105">Es ist zu beachten, dass auch weiterhin gelegentlich nicht abgefangene Ausnahmen bei Anwendungen auftreten, die unter einem Debugger ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d863c-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d863c-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d863c-106">Suggestion</span></span>

<span data-ttu-id="d863c-107">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="d863c-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="d863c-108">name</span><span class="sxs-lookup"><span data-stu-id="d863c-108">Name</span></span>    | <span data-ttu-id="d863c-109">Wert</span><span class="sxs-lookup"><span data-stu-id="d863c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d863c-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="d863c-110">Scope</span></span>   |<span data-ttu-id="d863c-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d863c-111">Edge</span></span>|
|<span data-ttu-id="d863c-112">Version</span><span class="sxs-lookup"><span data-stu-id="d863c-112">Version</span></span>|<span data-ttu-id="d863c-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="d863c-113">4.6.1</span></span>|
|<span data-ttu-id="d863c-114">Typ</span><span class="sxs-lookup"><span data-stu-id="d863c-114">Type</span></span>|<span data-ttu-id="d863c-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d863c-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d863c-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d863c-116">Affected APIs</span></span>

<span data-ttu-id="d863c-117">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="d863c-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
