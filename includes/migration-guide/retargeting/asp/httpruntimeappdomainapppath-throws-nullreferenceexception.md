---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617532"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="184a4-101">HttpRuntime.AppDomainAppPath löst NullReferenceException aus</span><span class="sxs-lookup"><span data-stu-id="184a4-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="184a4-102">Details</span><span class="sxs-lookup"><span data-stu-id="184a4-102">Details</span></span>

<span data-ttu-id="184a4-103">In .NET Framework 4.6.2 löst die Laufzeit `T:System.NullReferenceException` aus, wenn ein `P:System.Web.HttpRuntime.AppDomainAppPath`-Wert abgerufen wird, der NULL-Zeichen enthält. In .NET Framework 4.6.1 und früheren Versionen löst die Laufzeit eine `T:System.ArgumentNullException` aus.</span><span class="sxs-lookup"><span data-stu-id="184a4-103">In the .NET Framework 4.6.2, the runtime throws a `T:System.NullReferenceException` when retrieving a `P:System.Web.HttpRuntime.AppDomainAppPath` value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an `T:System.ArgumentNullException`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="184a4-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="184a4-104">Suggestion</span></span>

<span data-ttu-id="184a4-105">Sie können mit einer der folgenden Möglichkeiten auf diese Änderung reagieren:</span><span class="sxs-lookup"><span data-stu-id="184a4-105">You can do either of the follow to respond to this change:</span></span>

- <span data-ttu-id="184a4-106">Behandeln Sie die `T:System.NullReferenceException`, wenn Ihre Anwendung in .NET Framework 4.6.2 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="184a4-106">Handle the `T:System.NullReferenceException` if you application is running on the .NET Framework 4.6.2.</span></span>
- <span data-ttu-id="184a4-107">Führen Sie ein Upgrade auf .NET Framework 4.7 durch, sodass das vorherige Verhalten wiederhergestellt und eine `T:System.ArgumentNullException` ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="184a4-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an `T:System.ArgumentNullException`.</span></span>

| <span data-ttu-id="184a4-108">name</span><span class="sxs-lookup"><span data-stu-id="184a4-108">Name</span></span>    | <span data-ttu-id="184a4-109">Wert</span><span class="sxs-lookup"><span data-stu-id="184a4-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="184a4-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="184a4-110">Scope</span></span>   | <span data-ttu-id="184a4-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="184a4-111">Edge</span></span>        |
| <span data-ttu-id="184a4-112">Version</span><span class="sxs-lookup"><span data-stu-id="184a4-112">Version</span></span> | <span data-ttu-id="184a4-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="184a4-113">4.6.2</span></span>       |
| <span data-ttu-id="184a4-114">Typ</span><span class="sxs-lookup"><span data-stu-id="184a4-114">Type</span></span>    | <span data-ttu-id="184a4-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="184a4-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="184a4-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="184a4-116">Affected APIs</span></span>

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
