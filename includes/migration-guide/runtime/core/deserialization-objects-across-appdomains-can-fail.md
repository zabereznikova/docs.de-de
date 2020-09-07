---
ms.openlocfilehash: 3f82a4daac3b5d8981532f0c82e9a76f13c68b6e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497351"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="31825-101">Deserialisierung von Objekten für mehrere Anwendungsdomänen kann einen Fehler auslösen</span><span class="sxs-lookup"><span data-stu-id="31825-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="31825-102">Details</span><span class="sxs-lookup"><span data-stu-id="31825-102">Details</span></span>

<span data-ttu-id="31825-103">In einigen Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="31825-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="31825-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="31825-104">Suggestion</span></span>

<span data-ttu-id="31825-105">Siehe [Entschärfung: Deserialisierung von Objekten über App-Domänen](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="31825-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="31825-106">name</span><span class="sxs-lookup"><span data-stu-id="31825-106">Name</span></span>    | <span data-ttu-id="31825-107">Wert</span><span class="sxs-lookup"><span data-stu-id="31825-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="31825-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="31825-108">Scope</span></span>   |<span data-ttu-id="31825-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="31825-109">Edge</span></span>|
|<span data-ttu-id="31825-110">Version</span><span class="sxs-lookup"><span data-stu-id="31825-110">Version</span></span>|<span data-ttu-id="31825-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="31825-111">4.5.1</span></span>|
|<span data-ttu-id="31825-112">Typ</span><span class="sxs-lookup"><span data-stu-id="31825-112">Type</span></span>|<span data-ttu-id="31825-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="31825-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="31825-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="31825-114">Affected APIs</span></span>

<span data-ttu-id="31825-115">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="31825-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
