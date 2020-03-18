---
ms.openlocfilehash: 2f960942bda54505690cbac3151ef74ec0ab5ebb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235491"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>Bei der Verwendung von Eintrittsinvarianzdiensten können Deadlocks auftreten

|   |   |
|---|---|
|Details|Ein Deadlock kann zu einem Eintrittsinvarianzdienst führen, der Instanzen des Diensts auf jeweils einen Ausführungsthread beschränkt. Dienste, die anfällig für dieses Problem sind, verfügen über das folgende <xref:System.ServiceModel.ServiceBehaviorAttribute> in ihrem Code:<pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]&#13;&#10;</code></pre>|
|Vorschlag|Dieses Problem können Sie wie folgt beheben:<ul><li>Legen Sie den Parallelitätsmodus des Diensts auf <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> oder &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt; fest. Beispiel:</li></ul><pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single)]&#13;&#10;</code></pre><ul><li>Installieren Sie das neueste Update für .NET Framework 4.6.2, oder führen Sie ein Upgrade auf eine höhere Version von .NET Framework durch. Dies deaktiviert die Weitergabe von <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Dieses Verhalten kann konfiguriert werden. Es entspricht dem Hinzufügen der folgenden App-Einstellung zu Ihrer Konfigurationsdatei:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Der Wert <code>Switch.System.ServiceModel.DisableOperationContextAsyncFlow</code> darf für Rentrant-Dienste nicht auf <code>false</code> festgelegt werden.|
|`Scope`|Nebenversion|
|Version|4.6.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType></li></ul>|
