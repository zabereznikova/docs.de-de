---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614527"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>Bei der Verwendung von Eintrittsinvarianzdiensten können Deadlocks auftreten

#### <a name="details"></a>Details

Ein Deadlock kann zu einem Eintrittsinvarianzdienst führen, der Instanzen des Diensts auf jeweils einen Ausführungsthread beschränkt. Dienste, die anfällig für dieses Problem sind, verfügen über das folgende <xref:System.ServiceModel.ServiceBehaviorAttribute> in ihrem Code:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a>Vorschlag

Dieses Problem können Sie wie folgt beheben:

- Legen Sie den Parallelitätsmodus des Diensts auf <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> oder &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt; fest. Zum Beispiel:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- Installieren Sie das neueste Update für .NET Framework 4.6.2, oder führen Sie ein Upgrade auf eine höhere Version von .NET Framework durch. Dies deaktiviert die Weitergabe von <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Dieses Verhalten kann konfiguriert werden. Es entspricht dem Hinzufügen der folgenden App-Einstellung zu Ihrer Konfigurationsdatei:

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

Der Wert `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` darf für Reentrant-Dienste nicht auf `false` festgelegt werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
