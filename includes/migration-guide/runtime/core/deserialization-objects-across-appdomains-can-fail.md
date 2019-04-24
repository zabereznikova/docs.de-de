---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804009"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="cafd5-101">Deserialisierung von Objekten für mehrere Anwendungsdomänen kann einen Fehler auslösen</span><span class="sxs-lookup"><span data-stu-id="cafd5-101">Deserialization of objects across appdomains can fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cafd5-102">Details</span><span class="sxs-lookup"><span data-stu-id="cafd5-102">Details</span></span>|<span data-ttu-id="cafd5-103">In einigen Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="cafd5-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>|
|<span data-ttu-id="cafd5-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="cafd5-104">Suggestion</span></span>|<span data-ttu-id="cafd5-105">Siehe [Entschärfung: Deserialisierung von Objekten über App-Domänen](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="cafd5-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>|
|<span data-ttu-id="cafd5-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="cafd5-106">Scope</span></span>|<span data-ttu-id="cafd5-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cafd5-107">Edge</span></span>|
|<span data-ttu-id="cafd5-108">Version</span><span class="sxs-lookup"><span data-stu-id="cafd5-108">Version</span></span>|<span data-ttu-id="cafd5-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="cafd5-109">4.5.1</span></span>|
|<span data-ttu-id="cafd5-110">Typ</span><span class="sxs-lookup"><span data-stu-id="cafd5-110">Type</span></span>|<span data-ttu-id="cafd5-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="cafd5-111">Runtime</span></span>|
