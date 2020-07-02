---
ms.openlocfilehash: 08ad6fd4ccb6d5ddbbb4fa7ef1b325ce30689748
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621293"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="ab70a-101">AppDomainSetup.DynamicBase wird mithilfe von UseRandomizedStringHashAlgorithm nicht mehr zufällig festgelegt</span><span class="sxs-lookup"><span data-stu-id="ab70a-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

#### <a name="details"></a><span data-ttu-id="ab70a-102">Details</span><span class="sxs-lookup"><span data-stu-id="ab70a-102">Details</span></span>

<span data-ttu-id="ab70a-103">Vor .NET Framework 4.6 wurde der Wert von <xref:System.AppDomainSetup.DynamicBase> für Anwendungsdomänen oder Prozesse zufällig festgelegt, wenn UseRandomizedStringHashAlgorithm in der Konfigurationsdatei der App aktiviert war.</span><span class="sxs-lookup"><span data-stu-id="ab70a-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="ab70a-104">Ab .NET Framework 4.6 gibt <xref:System.AppDomainSetup.DynamicBase> ein stabiles Ergebnis zurück, das zwischen verschiedenen Instanzen einer ausgeführten App und zwischen verschiedenen App-Domänen besteht.</span><span class="sxs-lookup"><span data-stu-id="ab70a-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="ab70a-105">Verschiedene Apps haben auch unterschiedliche dynamische Basen. Diese Änderung entfernt nur die Elemente von verschiedenen Instanzen einer App, die zufällig benannt werden.</span><span class="sxs-lookup"><span data-stu-id="ab70a-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ab70a-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ab70a-106">Suggestion</span></span>

<span data-ttu-id="ab70a-107">Beachten Sie, dass bei der Aktivierung von <code>UseRandomizedStringHashAlgorithm</code><xref:System.AppDomainSetup.DynamicBase> nicht zufällig festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="ab70a-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="ab70a-108">Wenn eine zufällige Basis benötigt wird, muss diese im Code Ihrer App anstelle einer API erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ab70a-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>

| <span data-ttu-id="ab70a-109">name</span><span class="sxs-lookup"><span data-stu-id="ab70a-109">Name</span></span>    | <span data-ttu-id="ab70a-110">Wert</span><span class="sxs-lookup"><span data-stu-id="ab70a-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ab70a-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="ab70a-111">Scope</span></span>   |<span data-ttu-id="ab70a-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ab70a-112">Edge</span></span>|
|<span data-ttu-id="ab70a-113">Version</span><span class="sxs-lookup"><span data-stu-id="ab70a-113">Version</span></span>|<span data-ttu-id="ab70a-114">4.6</span><span class="sxs-lookup"><span data-stu-id="ab70a-114">4.6</span></span>|
|<span data-ttu-id="ab70a-115">Typ</span><span class="sxs-lookup"><span data-stu-id="ab70a-115">Type</span></span>|<span data-ttu-id="ab70a-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ab70a-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ab70a-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ab70a-117">Affected APIs</span></span>

-<xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
