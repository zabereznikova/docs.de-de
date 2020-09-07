---
ms.openlocfilehash: f50022d9a7bacd7be40fe3050ced26e7c25cf7aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497671"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Selektor stürzt ab, wenn ein Element aus einer benutzerdefinierten INCC-Sammlung entfernt wird

#### <a name="details"></a>Details

<code>T:System.InvalidOperationException</code> kann in folgendem Szenario auftreten:<ul><li>Das ItemsSource-Element für <code>T:System.Windows.Controls.Primitives.Selector</code> ist eine Sammlung mit einer benutzerdefinierten Implementierung von <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>Das ausgewählte Element wird aus der Sammlung entfernt.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> weist den Wert <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code>=–1 auf, der eine unbekannte Position angibt.</li></ul>Die Aufrufliste der Ausnahme beginnt bei „System.Windows.Threading.Dispatcher.VerifyAccess()“ in „System.Windows.DependencyObject.GetValue(DependencyProperty dp)“ in „System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)“. Diese Ausnahme kann in .NET Framework 4.5 auftreten, wenn die Anwendung über mehr als einen Dispatcher-Thread verfügt. In .NET Framework 4.7 kann diese Ausnahme auch bei Anwendungen mit einem einzelnen Dispatcher-Thread ausgelöst werden. Dieses Problem wurde in .NET Framework 4.7.1 behoben.

#### <a name="suggestion"></a>Vorschlag

Upgrade auf .NET Framework 4.7.1

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.7|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
