---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616255"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a><span data-ttu-id="75cd8-101">Änderung von XOML-Workflowdefinition und ndSqlTrackingService-Cacheschlüssel von MD5 in SHA256</span><span class="sxs-lookup"><span data-stu-id="75cd8-101">Workflow XOML definition and SqlTrackingService cache keys changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="75cd8-102">Details</span><span class="sxs-lookup"><span data-stu-id="75cd8-102">Details</span></span>

<span data-ttu-id="75cd8-103">Die Workflowlaufzeit verwaltet einen Cache mit in XOML definierten Workflowdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="75cd8-103">The Workflow Runtime in keeps a cache of workflow definitions defined in XOML.</span></span> <span data-ttu-id="75cd8-104">SqlTrackingService verwaltet ebenfalls einen Cache, der mit Zeichenfolgen verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="75cd8-104">The SqlTrackingService also keeps a cache that is keyed by strings.</span></span> <span data-ttu-id="75cd8-105">Diese Caches werden nach Werten verschlüsselt, die den Hashwert der Prüfsumme enthalten.</span><span class="sxs-lookup"><span data-stu-id="75cd8-105">These caches are keyed by values that include checksum hash value.</span></span> <span data-ttu-id="75cd8-106">In .NET Framework 4.7.2 und früheren Versionen wird beim Hashing der Prüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="75cd8-106">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="75cd8-107">Ab .NET Framework 4.8 wird der Algorithmus SHA256 verwendet. Diese Änderung bringt kein Kompatibilitätsproblem mit sich, da die Werte bei jedem Start von Workflowlaufzeit und SqlTrackingService neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="75cd8-107">Starting with the .NET Framework 4.8, the algorithm used is SHA256.There shouldn't be a compatibility issue with this change because the values are recalculated each time the Workflow Runtime and SqlTrackingService is started.</span></span> <span data-ttu-id="75cd8-108">Kunden haben jedoch die Möglichkeit, ggf. zur Verwendung des älteren Hashalgorithmus zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="75cd8-108">However, we have provided quirks to allow customers to revert back to usage of the legacy hashing algorithm, if necessary.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="75cd8-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="75cd8-109">Suggestion</span></span>

<span data-ttu-id="75cd8-110">Wenn diese Änderung beim Ausführen von Workflows ein Problem darstellt, legen Sie einen oder beide `AppContext`-Switches auf „True“ fest:</span><span class="sxs-lookup"><span data-stu-id="75cd8-110">If this change presents a problem when executing workflows, try setting one or both of the `AppContext` switches:</span></span>

- <span data-ttu-id="75cd8-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;</span><span class="sxs-lookup"><span data-stu-id="75cd8-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; to true.</span></span>
- <span data-ttu-id="75cd8-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;</span><span class="sxs-lookup"><span data-stu-id="75cd8-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; to true.</span></span>
<span data-ttu-id="75cd8-113">In Code:</span><span class="sxs-lookup"><span data-stu-id="75cd8-113">In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="75cd8-114">Oder in der Konfigurationsdatei der Anwendung, die das <xref:System.Workflow.Runtime.WorkflowRuntime>-Objekt erstellt:</span><span class="sxs-lookup"><span data-stu-id="75cd8-114">Or in the configuration file (this needs to be in the config file for the application that is creating the <xref:System.Workflow.Runtime.WorkflowRuntime> object):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="75cd8-115">name</span><span class="sxs-lookup"><span data-stu-id="75cd8-115">Name</span></span>    | <span data-ttu-id="75cd8-116">Wert</span><span class="sxs-lookup"><span data-stu-id="75cd8-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="75cd8-117">Bereich</span><span class="sxs-lookup"><span data-stu-id="75cd8-117">Scope</span></span>   | <span data-ttu-id="75cd8-118">Gering</span><span class="sxs-lookup"><span data-stu-id="75cd8-118">Minor</span></span>       |
| <span data-ttu-id="75cd8-119">Version</span><span class="sxs-lookup"><span data-stu-id="75cd8-119">Version</span></span> | <span data-ttu-id="75cd8-120">4.8</span><span class="sxs-lookup"><span data-stu-id="75cd8-120">4.8</span></span>         |
| <span data-ttu-id="75cd8-121">Typ</span><span class="sxs-lookup"><span data-stu-id="75cd8-121">Type</span></span>    | <span data-ttu-id="75cd8-122">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="75cd8-122">Retargeting</span></span> |
