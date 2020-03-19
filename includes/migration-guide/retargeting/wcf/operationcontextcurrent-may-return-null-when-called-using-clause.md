---
ms.openlocfilehash: e08b78b49cab88d4435d75b04bd446b413a61340
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859254"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>OperationContext.Current kann NULL zurückgeben, wenn es in einer using-Klausel aufgerufen wird

|   |   |
|---|---|
|Details|<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> kann <code>null</code> zurückgeben, und eine <xref:System.NullReferenceException> kann ausgelöst werden, wenn alle folgenden Bedingungen zutreffen:<ul><li>Sie rufen den Wert der Eigenschaft <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> in einer Methode ab, die entweder <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt.</li><li>Sie instanziieren das <xref:System.ServiceModel.OperationContextScope>-Objekt in einer <code>using</code>-Klausel.</li><li>Sie rufen den Wert der Eigenschaft <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> in <code>using statement</code> ab. Zum Beispiel:</li></ul><pre><code class="lang-csharp">using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext context = OperationContext.Current;      // OperationContext.Current is null.&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre>|
|Vorschlag|Dieses Problem können Sie wie folgt beheben:<ul><li>Ändern Sie den Code wie folgt, um ein neues <xref:System.ServiceModel.OperationContext.Current%2A>-Objekt zu instanziieren, das nicht <code>null</code> ist:</li></ul><pre><code class="lang-csharp">OperationContext ocx = OperationContext.Current;&#13;&#10;using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext.Current = new OperationContext(ocx.Channel);&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre><ul><li>Installieren Sie das neueste Update für .NET Framework 4.6.2, oder führen Sie ein Upgrade auf eine höhere Version von .NET Framework durch. Dies deaktiviert die Weitergabe von <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> und stellt das Verhalten von WCF-Anwendungen in .NET Framework 4.6.1 und früheren Versionen wieder her. Dieses Verhalten kann konfiguriert werden. Es entspricht dem Hinzufügen der folgenden App-Einstellung zu Ihrer Konfigurationsdatei:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Wenn diese Änderung nicht erwünscht ist und Ihre Anwendung von der Weitergabe des Ausführungskontexts zwischen unterschiedlichen Vorgangskontexten abhängig ist, können Sie die Übertragung wie folgt aktivieren:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;false&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.6.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType></li></ul>|
