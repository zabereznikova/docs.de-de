---
ms.openlocfilehash: 8f4ee44e8432bae3537c6f064f564b9f044a7c33
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761455"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Selektor stürzt ab, wenn ein Element aus einer benutzerdefinierten INCC-Sammlung entfernt wird

|   |   |
|---|---|
|Details|<code>T:System.InvalidOperationException</code> kann in folgendem Szenario auftreten:<ul><li>Das ItemsSource-Element für <code>T:System.Windows.Controls.Primitives.Selector</code> ist eine Sammlung mit einer benutzerdefinierten Implementierung von <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>Das ausgewählte Element wird aus der Sammlung entfernt.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> weist den Wert <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code>=–1 auf, der eine unbekannte Position angibt.</li></ul>Die Aufrufliste der Ausnahme beginnt bei „System.Windows.Threading.Dispatcher.VerifyAccess()“ in „System.Windows.DependencyObject.GetValue(DependencyProperty dp)“ in „System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)“. Diese Ausnahme kann in .NET Framework 4.5 auftreten, wenn die Anwendung über mehr als einen Dispatcher-Thread verfügt. In .NET Framework 4.7 kann diese Ausnahme auch bei Anwendungen mit einem einzelnen Dispatcher-Thread ausgelöst werden. Dieses Problem wurde in .NET Framework 4.7.1 behoben.|
|Vorschlag|Upgrade auf .NET Framework 4.7.1|
|Bereich|Gering|
|Version|4.7|
|Typ|Laufzeit|

