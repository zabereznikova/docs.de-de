---
ms.openlocfilehash: fc6066fd0b23d299158114cb397934041b99ba47
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620460"
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
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType></li></ul>|
