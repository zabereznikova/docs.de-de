---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616255"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>Änderung von XOML-Workflowdefinition und ndSqlTrackingService-Cacheschlüssel von MD5 in SHA256

#### <a name="details"></a>Details

Die Workflowlaufzeit verwaltet einen Cache mit in XOML definierten Workflowdefinitionen. SqlTrackingService verwaltet ebenfalls einen Cache, der mit Zeichenfolgen verschlüsselt ist. Diese Caches werden nach Werten verschlüsselt, die den Hashwert der Prüfsumme enthalten. In .NET Framework 4.7.2 und früheren Versionen wird beim Hashing der Prüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.8 wird der Algorithmus SHA256 verwendet. Diese Änderung bringt kein Kompatibilitätsproblem mit sich, da die Werte bei jedem Start von Workflowlaufzeit und SqlTrackingService neu berechnet werden. Kunden haben jedoch die Möglichkeit, ggf. zur Verwendung des älteren Hashalgorithmus zurückzukehren.

#### <a name="suggestion"></a>Vorschlag

Wenn diese Änderung beim Ausführen von Workflows ein Problem darstellt, legen Sie einen oder beide `AppContext`-Switches auf „True“ fest:

- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;
- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;
In Code:

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

Oder in der Konfigurationsdatei der Anwendung, die das <xref:System.Workflow.Runtime.WorkflowRuntime>-Objekt erstellt:

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.8         |
| Typ    | Neuzuweisung |
