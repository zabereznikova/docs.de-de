---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614506"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>OperationContext.Current kann NULL zurückgeben, wenn es in einer using-Klausel aufgerufen wird

#### <a name="details"></a>Details

<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> kann `null` zurückgeben, und eine <xref:System.NullReferenceException> kann ausgelöst werden, wenn alle folgenden Bedingungen zutreffen:

- Sie rufen den Wert der Eigenschaft <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> in einer Methode ab, die entweder <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt.
- Sie instanziieren das <xref:System.ServiceModel.OperationContextScope>-Objekt in einer `using`-Klausel.
- Sie rufen den Wert der Eigenschaft <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> in `using statement` ab. Zum Beispiel:

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a>Vorschlag

Dieses Problem können Sie wie folgt beheben:

- Ändern Sie den Code wie folgt, um ein neues <xref:System.ServiceModel.OperationContext.Current%2A>-Objekt zu instanziieren, das nicht `null` ist:

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- Installieren Sie das neueste Update für .NET Framework 4.6.2, oder führen Sie ein Upgrade auf eine höhere Version von .NET Framework durch. Dies deaktiviert die Weitergabe von <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> und stellt das Verhalten von WCF-Anwendungen in .NET Framework 4.6.1 und früheren Versionen wieder her. Dieses Verhalten kann konfiguriert werden. Es entspricht dem Hinzufügen der folgenden App-Einstellung zu Ihrer Konfigurationsdatei:

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    Wenn diese Änderung nicht erwünscht ist und Ihre Anwendung von der Weitergabe des Ausführungskontexts zwischen unterschiedlichen Vorgangskontexten abhängig ist, können Sie die Übertragung wie folgt aktivieren:

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
