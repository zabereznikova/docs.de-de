---
ms.openlocfilehash: a806107456a65a4919592da9535a2617f677cfe0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496466"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>WPF DispatcherSynchronizationContext.CreateCopy gibt jetzt anstelle der aktuellen Instanz eine neue Kopie zurück

#### <a name="details"></a>Details

In .NET Framework 4 hat <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> in erster Linie einen Verweis auf die aktuelle Instanz zurückgegeben, um die Leistung zu optimieren. In .NET Framework 4.5 wird eine neue Instanz zurückgegeben, wodurch es erstmalig möglich ist zu Schlussfolgern, dass gleiche Verweise angeben, dass sich der ausführende Thread im richtigen Synchronisierungskontext befindet.  Es ist unwahrscheinlich, dass Code, der die Identität dieser Verweise prüft, betroffen ist. Aber aufgrund der Änderung sollte Code, der <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> aufruft, im Rahmen der Migration zu .NET Framework 4.5 oder einer höheren Version getestet werden.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, dass <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> jetzt ein neues <xref:System.Threading.SynchronizationContext?displayProperty=fullName>-Objekt zurückgibt. Zuvor wurde Code, der die Gleichheit von Verweisen verwendete, die auf diese Weise generiert wurden, tatsächlich nicht dahingehend überprüft, ob er sich im richtigen Kontext befunden hat. Dies wird jetzt jedoch durchgeführt, wenn bei der Erstellung .NET Framework 4.5 oder höher verwendet wird.  Obwohl es unwahrscheinlich ist, dass dies zu Problemen führt, sollte das Anwenden der betroffenen Codepfade ausreichend sein, um zu ermitteln, ob dies zu Problemen führen kann.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy`

-->
