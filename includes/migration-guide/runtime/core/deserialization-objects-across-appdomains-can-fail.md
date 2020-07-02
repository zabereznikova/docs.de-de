---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620213"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="8047d-101">Deserialisierung von Objekten für mehrere Anwendungsdomänen kann einen Fehler auslösen</span><span class="sxs-lookup"><span data-stu-id="8047d-101">Deserialization of objects across appdomains can fail</span></span>

#### <a name="details"></a><span data-ttu-id="8047d-102">Details</span><span class="sxs-lookup"><span data-stu-id="8047d-102">Details</span></span>

<span data-ttu-id="8047d-103">In einigen Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="8047d-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8047d-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="8047d-104">Suggestion</span></span>

<span data-ttu-id="8047d-105">Siehe [Entschärfung: Deserialisierung von Objekten über App-Domänen](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="8047d-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>

| <span data-ttu-id="8047d-106">name</span><span class="sxs-lookup"><span data-stu-id="8047d-106">Name</span></span>    | <span data-ttu-id="8047d-107">Wert</span><span class="sxs-lookup"><span data-stu-id="8047d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8047d-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="8047d-108">Scope</span></span>   |<span data-ttu-id="8047d-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8047d-109">Edge</span></span>|
|<span data-ttu-id="8047d-110">Version</span><span class="sxs-lookup"><span data-stu-id="8047d-110">Version</span></span>|<span data-ttu-id="8047d-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="8047d-111">4.5.1</span></span>|
|<span data-ttu-id="8047d-112">Typ</span><span class="sxs-lookup"><span data-stu-id="8047d-112">Type</span></span>|<span data-ttu-id="8047d-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8047d-113">Runtime</span></span>|
