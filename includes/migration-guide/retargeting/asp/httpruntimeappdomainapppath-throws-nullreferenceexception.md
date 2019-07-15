---
ms.openlocfilehash: d6c658f306dd4792e3cb5dbdc9471043ca95a071
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859183"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="24420-101">HttpRuntime.AppDomainAppPath löst NullReferenceException aus</span><span class="sxs-lookup"><span data-stu-id="24420-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="24420-102">Details</span><span class="sxs-lookup"><span data-stu-id="24420-102">Details</span></span>|<span data-ttu-id="24420-103">In .NET Framework 4.6.2 löst die Laufzeit <code>T:System.NullReferenceException</code> aus, wenn ein <code>P:System.Web.HttpRuntime.AppDomainAppPath</code>-Wert abgerufen wird, der NULL-Zeichen enthält. In .NET Framework 4.6.1 und früheren Versionen löst die Laufzeit eine <code>T:System.ArgumentNullException</code> aus.</span><span class="sxs-lookup"><span data-stu-id="24420-103">In the .NET Framework 4.6.2, the runtime throws a <code>T:System.NullReferenceException</code> when retrieving a <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an <code>T:System.ArgumentNullException</code>.</span></span>|
|<span data-ttu-id="24420-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="24420-104">Suggestion</span></span>|<span data-ttu-id="24420-105">Sie können mit einer der folgenden Möglichkeiten auf diese Änderung reagieren:</span><span class="sxs-lookup"><span data-stu-id="24420-105">You can do either of the follow to respond to this change:</span></span><ul><li><span data-ttu-id="24420-106">Behandeln Sie die <code>T:System.NullReferenceException</code>, wenn Ihre Anwendung in .NET Framework 4.6.2 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24420-106">Handle the <code>T:System.NullReferenceException</code> if you application is running on the .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="24420-107">Führen Sie ein Upgrade auf .NET Framework 4.7 durch, sodass das vorherige Verhalten wiederhergestellt und eine <code>T:System.ArgumentNullException</code> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="24420-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an <code>T:System.ArgumentNullException</code>.</span></span></li></ul>|
|<span data-ttu-id="24420-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="24420-108">Scope</span></span>|<span data-ttu-id="24420-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="24420-109">Edge</span></span>|
|<span data-ttu-id="24420-110">Version</span><span class="sxs-lookup"><span data-stu-id="24420-110">Version</span></span>|<span data-ttu-id="24420-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="24420-111">4.6.2</span></span>|
|<span data-ttu-id="24420-112">Typ</span><span class="sxs-lookup"><span data-stu-id="24420-112">Type</span></span>|<span data-ttu-id="24420-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="24420-113">Retargeting</span></span>|
|<span data-ttu-id="24420-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="24420-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|

