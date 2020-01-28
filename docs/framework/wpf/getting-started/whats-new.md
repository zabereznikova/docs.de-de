---
title: Neues in WPF Version 4.5
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 8eff8da7746047c450b2e23af63d43b13f3b970c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746922"
---
# <a name="whats-new-in-wpf-version-45"></a>Neues in WPF Version 4.5
<a name="introduction"></a>Dieses Thema enthält Informationen zu neuen und verbesserten Features in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Version 4,5.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Menübandsteuerung](#ribbon_control)  
  
- [Verbesserte Leistung bei der Anzeige großer Mengen gruppierter Daten](#grouped_virtualization)  
  
- [Neue Funktionen für das VirtualizingPanel](#VirtualizingPanel)  
  
- [Bindung an statische Eigenschaften](#static_properties)  
  
- [Zugriff auf Auflistungen in Nicht-UI-Threads](#xthread_access)  
  
- [Synchrone und asynchrone Überprüfung von Daten](#INotifyDataErrorInfo)  
  
- [Automatische Aktualisierung der Quelle einer Datenbindung](#delay)  
  
- [Bindung an Typen, die ICustomTypeProvider implementieren](#ICustomTypeProvider)  
  
- [Abrufen von Datenbindungsinformationen aus einem Bindungsausdruck](#binding_state)  
  
- [Prüfen auf ein gültiges DataContext-Objekt](#DisconnectedSource)  
  
- [Neupositionierung von Daten bei Wertänderung (Live-Strukturierung)](#live_shaping)  
  
- [Verbesserte Unterstützung für die Einrichtung eines schwachen Verweises auf ein Ereignis](#weak_event_pattern)  
  
- [Neue Methoden für die Verteilerklasse](#async)  
  
- [Markuperweiterungen für Ereignisse](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## <a name="ribbon-control"></a>Menübandsteuerung  
 WPF 4.5 wird mit einer <xref:System.Windows.Controls.Ribbon.Ribbon>-Steuerung ausgeliefert, die eine Symbolleiste für den Schnellzugriff, ein Anwendungsmenü und Registerkarten hostet.  Weitere Informationen finden Sie unter [Übersicht über die Multifunktionsleiste](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Verbesserte Leistung bei der Anzeige großer Mengen gruppierter Daten  
 UI-Virtualisierung liegt vor, wenn eine Teilmenge von UI-Elementen aus einer größeren Anzahl von Datenelementen generiert wird, wobei berücksichtigt wird, welche Elemente auf dem Bildschirm angezeigt werden. Das <xref:System.Windows.Controls.VirtualizingPanel> definiert die angefügte <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A>-Eigenschaft, die die UI-Virtualisierung für gruppierte Daten ermöglicht.  Weitere Informationen zum Gruppieren von Daten finden Sie in der Anleitung zum Sortieren und Gruppieren von Daten mit einer Ansicht in XAML.  Weitere Informationen zum Virtualisieren von gruppierten Daten finden Sie in der angefügten Eigenschaft <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A>.  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a>Neue Funktionen für das VirtualizingPanel  
  
1. Sie können angeben, ob ein <xref:System.Windows.Controls.VirtualizingPanel> wie z. B. das <xref:System.Windows.Controls.VirtualizingStackPanel> abgeschnittene Elemente anzeigt; dazu dient die angefügte <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>-Eigenschaft. Wenn <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> auf <xref:System.Windows.Controls.ScrollUnit.Item> festgelegt ist, zeigt das <xref:System.Windows.Controls.VirtualizingPanel> nur Elemente an, die vollständig sichtbar sind. Wenn <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> auf <xref:System.Windows.Controls.ScrollUnit.Pixel> festgelegt ist, kann das <xref:System.Windows.Controls.VirtualizingPanel> teilweise sichtbare Elemente anzeigen.  
  
2. Sie können die Größe des Cache vor und nach dem Viewport während der Virtualisierung durch das <xref:System.Windows.Controls.VirtualizingPanel> angeben; dazu dient die angefügte <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A>-Eigenschaft.  Der Cache ist der Platz über bzw. unter dem Viewport, in dem keine Elemente virtualisiert werden.  Wenn Sie mit einem Cache die Erstellung von UI-Elementen unterdrücken, während sie in die Ansicht rücken, kann dadurch die Leistung verbessert werden. Der Cache hat beim Auffüllen geringere Priorität; dadurch wird vermieden, dass die Anwendung während des Vorgangs nicht mehr reagiert. Die <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType>-Eigenschaft legt die von <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType> verwendete Maßeinheit fest.  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a>Bindung an statische Eigenschaften  
 Sie können statische Eigenschaften als Quelle einer Datenbindung verwenden. Die Datenbindungs-Engine erkennt es, wenn sich der Eigenschaftswert ändert, falls ein statisches Ereignis ausgelöst wird.  Wenn beispielsweise die `SomeClass`-Klasse eine statische Eigenschaft namens `MyProperty` definiert, kann `SomeClass` ein statisches Ereignis definieren, das ausgelöst wird, wenn sich der Wert von `MyProperty` ändert.  Das statische Ereignis kann eine der folgenden Signaturen verwenden.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Beachten Sie, dass die-Klasse im ersten Fall ein statisches Ereignis namens *propertyName*`Changed` verfügbar macht, das <xref:System.EventArgs> an den-Ereignishandler übergibt.  Im zweiten Fall macht die Klasse ein statisches Ereignis namens `StaticPropertyChanged` verfügbar, das den <xref:System.ComponentModel.PropertyChangedEventArgs>-Ereignishandler übergibt. Eine Klasse, die die statische Eigenschaft implementiert, kann Benachrichtigungen über Eigenschaftsänderungen nach Wahl mit einer der beiden Methode auslösen.  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a>Zugriff auf Auflistungen in Nicht-UI-Threads  
 Mit WPF können Sie auf Datensammlungen auf anderen Threads als dem, der die Auflistung erstellt hat, zugreifen und diese ändern.  Dadurch können Sie mit einem Hintergrundthread Daten aus einer externen Quelle, z. B. aus einer Datenbank, empfangen und die Daten im UI-Thread anzeigen.  Wenn Sie die Auflistung mit einem anderen Thread modifizieren, reagiert die Benutzeroberfläche weiterhin auf die Benutzerinteraktion.  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a>Synchrone und asynchrone Überprüfung von Daten  
 Die <xref:System.ComponentModel.INotifyDataErrorInfo>-Schnittstelle ermöglicht es Datenentitätsklassen, benutzerdefinierte Validierungsregeln zu implementieren und Validierungsergebnisse asynchron verfügbar zu machen. Diese Schnittstelle unterstützt auch benutzerdefinierte Fehlerobjekte, mehrere Fehler pro Eigenschaft, eigenschaftenübergreifende Fehler und Fehler auf Entitätsebene.  Weitere Informationen finden Sie unter <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Automatische Aktualisierung der Quelle einer Datenbindung  
 Wenn Sie eine Datenquelle mit einer Datenbindung aktualisieren, können Sie mit der Eigenschaft <xref:System.Windows.Data.BindingBase.Delay%2A> angeben, wie viel Zeit nach der Änderung der Eigenschaft am Ziel vergehen soll, bevor die Quelle aktualisiert wird.  Angenommen, Sie haben ein <xref:System.Windows.Controls.Slider>, das seine <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>-Eigenschaftendaten in beide Richtungen an eine Eigenschaft eines Datenobjekts gebunden hat, und die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Eigenschaft ist auf <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> festgelegt.  In diesem Beispiel wird, wenn der Benutzer <xref:System.Windows.Controls.Slider> verschiebt, die Quelle für jedes Pixel aktualisiert, das <xref:System.Windows.Controls.Slider> verschiebt.  Das Quellobjekt benötigt in der Regel den Wert des Schiebereglers nur, wenn sich der <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> des Schiebereglers nicht mehr ändert.  Um zu verhindern, dass sich die Quelle zu oft aktualisiert, geben Sie mit <xref:System.Windows.Data.BindingBase.Delay%2A> an, dass die Quelle nicht aktualisiert werden soll, bis nach abgeschlossener Bewegung ein bestimmter Zeitraum vergangen ist.  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Bindung an Typen, die ICustomTypeProvider implementieren  
 WPF unterstützt die Datenbindung an Objekte, die <xref:System.Reflection.ICustomTypeProvider> implementieren, auch als benutzerdefinierte Typen bezeichnet.  Sie können benutzerdefinierte Typen in den folgenden Fällen verwenden.  
  
1. Als <xref:System.Windows.PropertyPath> in einer Datenbindung. Beispielsweise kann die <xref:System.Windows.Data.Binding.Path%2A>-Eigenschaft von <xref:System.Windows.Data.Binding> auf eine Eigenschaft eines benutzerdefinierten Typs verweisen.  
  
2. Als Wert der <xref:System.Windows.DataTemplate.DataType%2A>-Eigenschaft.  
  
3. Als Typ, der die automatisch generierten Spalten in <xref:System.Windows.Controls.DataGrid> festlegt.  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Abrufen von Datenbindungsinformationen aus einem Bindungsausdruck  
 In bestimmten Situationen rufen Sie die <xref:System.Windows.Data.BindingExpression> von <xref:System.Windows.Data.Binding> ab und benötigen Informationen zu den Quell- und Zielobjekten der Bindung.  Es wurden neue APIs hinzugefügt, damit Sie das Quell- oder Zielobjekt oder die zugeordnete Eigenschaft abrufen können.  Wenn Sie über <xref:System.Windows.Data.BindingExpression> verfügen, verwenden Sie folgende APIs, um Informationen über das Ziel und die Quelle abzurufen.  
  
|Um diesen Wert der Bindung zu suchen|Verwenden Sie dieses API|  
|---------------------------------------|------------------|  
|Das Zielobjekt|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|Die Zieleigenschaft|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Das Quellobjekt|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|Die Quelleigenschaft|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Ob die <xref:System.Windows.Data.BindingExpression> zu einer <xref:System.Windows.Data.BindingGroup> gehört|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|Der Besitzer einer <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a>Prüfen auf ein gültiges DataContext-Objekt  
 Es gibt Situationen, in denen der <xref:System.Windows.FrameworkElement.DataContext%2A> eines Elementcontainers in einem <xref:System.Windows.Controls.ItemsControl> getrennt wird.  Ein Elementcontainer ist das Benutzeroberflächenelement, das ein Element in einem <xref:System.Windows.Controls.ItemsControl> anzeigt.  Wenn ein <xref:System.Windows.Controls.ItemsControl> an eine Auflistung datengebunden ist, wird ein Elementcontainer für jedes Element generiert. In einigen Fällen werden Elementcontainer aus der visuellen Struktur entfernt. Zwei typische Situationen, in denen ein Elementcontainer entfernt wird, sind folgende: Wenn ein Element aus der zugrunde liegenden Auflistung entfernt wird, und wenn Virtualisierung auf <xref:System.Windows.Controls.ItemsControl> aktiviert wird. In diesen Fällen wird die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft des Elementcontainers auf das Sentinelobjekt festgelegt, das von der statischen <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird.  Sie sollten überprüfen, ob <xref:System.Windows.FrameworkElement.DataContext%2A> gleich dem <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A>-Objekt ist, bevor Sie auf den <xref:System.Windows.FrameworkElement.DataContext%2A> eines Elementcontainers zugreifen.  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Neupositionierung von Daten bei Wertänderung (Live-Strukturierung)  
 Eine Datenauflistung kann gruppiert, gefiltert oder sortiert werden. WPF 4.5 ermöglicht die Neuanordnung, wenn die Daten geändert werden. Angenommen, eine Anwendung listet mit <xref:System.Windows.Controls.DataGrid> die Aktien an einer Börse auf, und die Aktien werden nach Aktienwert sortiert. Wenn die Livesortierung in der <xref:System.Windows.Data.CollectionView> der Aktien aktiviert ist, ändert sich die Position einer Aktie in <xref:System.Windows.Controls.DataGrid>, wenn der Wert der Aktie über oder unter den Wert einer anderen Aktie steigt oder sinkt.   Weitere Informationen finden Sie unter der <xref:System.ComponentModel.ICollectionViewLiveShaping>-Schnittstelle.  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Verbesserte Unterstützung für die Einrichtung eines schwachen Verweises auf ein Ereignis  
 Die Implementierung des schwachen Ereignismusters ist jetzt einfacher, da Abonnenten der Ereignisse daran beteiligt sein können, ohne eine zusätzliche Schnittstelle implementieren zu müssen.  Die generische <xref:System.Windows.WeakEventManager>-Klasse ermöglicht es Abonnenten außerdem, am schwachen Ereignismuster teilzunehmen, wenn für ein bestimmtes Ereignis kein dedizierter <xref:System.Windows.WeakEventManager> vorhanden ist.  Weitere Informationen finden Sie unter [Schwache Ereignismuster](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a>Neue Methoden für die Verteilerklasse  
 Die Verteilerklasse definiert neue Methoden für synchrone und asynchrone Vorgänge.  Die synchrone <xref:System.Windows.Threading.Dispatcher.Invoke%2A>-Methode definiert Überladungen, die einen <xref:System.Action>- oder <xref:System.Func%601>-Parameter entgegennehmen. Die neue asynchrone Methode <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> nimmt ebenfalls <xref:System.Action> oder <xref:System.Func%601> als Rückrufparameter entgegen und gibt <xref:System.Windows.Threading.DispatcherOperation> oder <xref:System.Windows.Threading.DispatcherOperation%601> zurück.   Die <xref:System.Windows.Threading.DispatcherOperation>- und <xref:System.Windows.Threading.DispatcherOperation%601>-Klassen definieren eine <xref:System.Threading.Tasks.Task>-Eigenschaft.  Wenn Sie <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> aufrufen, können Sie das Schlüsselwort `await` entweder mit <xref:System.Windows.Threading.DispatcherOperation> oder mit dem zugehörigen <xref:System.Threading.Tasks.Task> verwenden. Wenn Sie synchron auf das <xref:System.Threading.Tasks.Task> warten müssen, das von <xref:System.Windows.Threading.DispatcherOperation> oder <xref:System.Windows.Threading.DispatcherOperation%601> zurückgegeben wird, rufen Sie die <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A>-Erweiterungsmethode auf. Wenn Sie <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> aufrufen, führt das zu einem Deadlock, wenn der Vorgang auf einem aufrufenden Thread in die Warteschlange gestellt wird. Weitere Informationen zum Verwenden einer <xref:System.Threading.Tasks.Task> zum Ausführen von asynchronen Vorgängen finden Sie unter [Task parallelism (Task Parallel Library)](../../../standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a>Markuperweiterungen für Ereignisse  
 WPF 4.5 unterstützt Markuperweiterungen für Ereignisse.  WPF definiert zwar keine Markuperweiterung zur Verwendung für Ereignisse, diese können aber von Drittanbietern erstellt werden.  
  
## <a name="see-also"></a>Siehe auch

- [Neuigkeiten in .NET Framework](../../whats-new/index.md)
