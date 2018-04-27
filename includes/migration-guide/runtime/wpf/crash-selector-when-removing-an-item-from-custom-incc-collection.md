### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Selektor stürzt ab, wenn ein Element aus einer benutzerdefinierten INCC-Sammlung entfernt wird

|   |   |
|---|---|
|Details|<code>T:System.InvalidOperationException</code> kann in folgendem Szenario auftreten:<ul><li>Das ItemsSource-Element für <code>T:System.Windows.Controls.Primitives.Selector</code> ist eine Sammlung mit einer benutzerdefinierten Implementierung von <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>Das ausgewählte Element wird aus der Sammlung entfernt.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> weist den Wert <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code>=–1 auf, der eine unbekannte Position angibt.</li></ul>Die Aufrufliste der Ausnahme beginnt bei „System.Windows.Threading.Dispatcher.VerifyAccess()“ in „System.Windows.DependencyObject.GetValue(DependencyProperty dp)“ in „System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)“. Diese Ausnahme kann in .NET 4.5 auftreten, wenn die Anwendung über mehr als einen Dispatcher-Thread verfügt. In .NET 4.7 kann diese Ausnahme auch bei Anwendungen mit einem einzelnen Dispatcher-Thread ausgelöst werden. Dieses Problem wurde in .NET 4.7.1 behoben.|
|Vorschlag|Führen Sie ein Upgrade auf .NET 4.7.1 durch.|
|Bereich|Gering|
|Version|4.7|
|Typ|Laufzeit|

