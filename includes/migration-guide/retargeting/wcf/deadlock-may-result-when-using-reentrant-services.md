---
ms.openlocfilehash: add7b803c413f8d9ba913d5dcc1a21bbd0c5bd48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803997"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>Bei der Verwendung von Eintrittsinvarianzdiensten können Deadlocks auftreten

|   |   |
|---|---|
|Details|Ein Deadlock kann zu einem Eintrittsinvarianzdienst führen, der Instanzen des Diensts auf jeweils einen Ausführungsthread beschränkt. Dienste, die anfällig für dieses Problem sind, verfügen über das folgende <xref:System.ServiceModel.ServiceBehaviorAttribute> in ihrem Code:<pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]&#13;&#10;</code></pre>|
|Vorschlag|Dieses Problem können Sie wie folgt beheben:<ul><li>Legen Sie den Parallelitätsmodus des Diensts auf <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> oder &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt; fest. Beispiel:</li></ul><pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single)]&#13;&#10;</code></pre><ul><li>Installieren Sie das neueste Update für .NET Framework 4.6.2, oder führen Sie ein Upgrade auf eine höhere Version von .NET Framework durch. Dies deaktiviert die Weitergabe von <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Dieses Verhalten kann konfiguriert werden. Es entspricht dem Hinzufügen der folgenden App-Einstellung zu Ihrer Konfigurationsdatei:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Der Wert <code>Switch.System.ServiceModel.DisableOperationContextAsyncFlow</code> darf für Reentrant-Dienste nicht auf <code>false</code> festgelegt werden.|
|Bereich|Gering|
|Version|4.6.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType></li></ul>|
