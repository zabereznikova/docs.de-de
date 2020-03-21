---
title: 'Optimieren der Leistung: Objektverhalten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interface virtualization [WPF]
- dependency properties [WPF], performance
- event handlers [WPF]
- object performance considerations [WPF]
- Freezable objects [WPF], performance
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
ms.openlocfilehash: 67184db7fc1459e83ac7b1e6ff09ef56e43f0ca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187076"
---
# <a name="optimizing-performance-object-behavior"></a>Optimieren der Leistung: Objektverhalten
Wenn Sie das Verhalten von systeminternen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekten verstehen, können Sie Funktionalität und Leistung optimal miteinander vereinen.  

<a name="Not_Removing_Event_Handlers"></a>
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>Wenn Ereignishandler nicht aus Objekten entfernt werden, bleiben diese möglicherweise aktiv  
 Der Delegat, den ein Objekt an sein Ereignis übergibt, ist gewissermaßen ein Verweis auf dieses Objekt. Aufgrund von Ereignishandlern können Objekte länger als erwartet aktiv sein. Wenn sie ein Objekt bereinigen, das registriert wurde, um auf ein Ereignis eines Objekts zu lauschen, ist es erforderlich, dass Sie diesen Delegaten entfernen, bevor Sie das Objekt freigeben. Wenn nicht benötigte Objekte weiter aktiv sind, erhöht dies die Speicherauslastung Ihrer Anwendung. Dies ist insbesondere dann der Fall, wenn das Objekt der Stamm einer logischen oder visuellen Struktur ist.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] führt ein schwaches Ereignislistenermuster für Ereignisse ein, das dann nützlich sein kann, wenn die Beziehungen der Objektlebensdauer zwischen Quelle und Listener schwierig zu überwachen sind. Einige vorhandene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignisse verwenden dieses Muster. Wenn Sie Objekte mit benutzerdefinierten Ereignissen implementieren, kann dieses Muster für Sie nützlich sein. Weitere Informationen finden Sie unter [Schwache Ereignismuster](weak-event-patterns.md).  
  
 Es gibt mehrere Tools, wie z.B. den CLR-Profiler und den Workingset-Viewer, die Informationen zur Speicherauslastung eines angegebenen Prozesses zur Verfügung stellen können. Der CLR-Profiler umfasst eine Reihe sehr nützlicher Ansichten des Belegungsprofils, darunter z.B. ein Histogramm der zugewiesenen Typen, Zuordnungs- und Aufrufdiagramme, eine Zeitachse mit den automatische Speicherbereinigungen verschiedener Generationen und der daraus entstehende Status des verwalteten Heaps nach diesen Bereinigungen sowie eine Aufrufstruktur, die Zuweisungen und Laden von Assemblys für jede Methode veranschaulicht. Weitere Informationen finden Sie unter [Leistung](https://docs.microsoft.com/previous-versions/aa497289(v=msdn.10)).  
  
<a name="DPs_and_Objects"></a>
## <a name="dependency-properties-and-objects"></a>Anhängigkeitseigenschaften und Objekte  
 Im Allgemeinen ist der Zugriff <xref:System.Windows.DependencyObject> auf eine Abhängigkeitseigenschaft von a nicht langsamer als der Zugriff auf eine CLR-Eigenschaft. Obwohl es einen kleinen Leistungsaufwand für das Festlegen eines Eigenschaftswerts gibt, ist das Abrufen eines Werts so schnell wie das Abrufen des Werts von einer CLR-Eigenschaft. Der kleine Leistungsaufwand wird durch die Tatsache verursacht, dass Abhängigkeitseigenschaften zuverlässige Funktionen unterstützen, wie z.B. die Datenbindung, die Animation, die Vererbung und das Formatieren. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>DependencyProperty-Optimierungen  
 Sie sollten Abhängigkeitseigenschaften in Ihrer Anwendung sorgfältig definieren. Wenn <xref:System.Windows.DependencyProperty> Die Auswirkungen nur auf Metadatenoptionen des Rendertyps und nicht auf andere Metadatenoptionen wie <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, wirken, sollten Sie diese als solche markieren, indem Sie die Metadaten überschreiben. Weitere Informationen über das Überschreiben oder Abrufen von Eigenschaftenmetadaten finden Sie unter [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
 Möglicherweise ist es effizienter, mit einem Handler für Eigenschaftenänderungen die Messungs-, Anordnungs- und Rendering-Durchläufe manuell für ungültig zu erklären, wenn nicht alle Eigenschaftenänderungen „Messung“, „Anordnung“ und „Rendering“ betreffen. Möglicherweise möchten Sie einen Hintergrund nur dann erneut rendern, wenn ein Wert höher als ein festgelegter Grenzwert ist. In diesem Fall würde Ihr Handler für Eigenschaftenänderungen nur „render“ für ungültig erklären, wenn der festgelegte Grenzwert überschritten wird.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Sie können eine Abhängigkeitseigenschaft nicht frei vererben  
 Registrierte Abhängigkeitseigenschaften sind standardmäßig nicht vererbbar. Allerdings können Sie eine Eigenschaft explizit vererbbar machen. Obwohl dies nützlich ist, beeinträchtigt das Konvertieren einer Eigenschaft in eine vererbbare Eigenschaft die Leistung, da die Zeit für das Aufheben der Validierung erhöht wird.  
  
### <a name="use-registerclasshandler-carefully"></a>Verwenden Sie RegisterClassHandler mit Vorsicht  
 Während <xref:System.Windows.EventManager.RegisterClassHandler%2A> Sie beim Aufrufen den Instanzstatus speichern können, ist es wichtig, sich bewusst zu sein, dass der Handler für jede Instanz aufgerufen wird, was zu Leistungsproblemen führen kann. Verwenden <xref:System.Windows.EventManager.RegisterClassHandler%2A> Sie dies nur, wenn Ihre Anwendung erfordert, dass Sie den Instance-Status speichern.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Legen Sie den Standardwert für eine Abhängigkeitseigenschaft während der Registrierung fest  
 Legen Sie <xref:System.Windows.DependencyProperty> beim Erstellen eines, das einen Standardwert erfordert, den <xref:System.Windows.DependencyProperty.Register%2A> Wert <xref:System.Windows.DependencyProperty>mithilfe der Standardmetadaten fest, die als Parameter an die Methode der übergeben werden. Nutzen Sie diese Vorgehensweise, statt den Eigenschaftswert in einem Konstruktor oder in jeder Instanz des Elements festzulegen.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Festlegen des Werts der Metadaten der Eigenschaft mit der Register-Methode  
 Beim Erstellen <xref:System.Windows.DependencyProperty>einer haben Sie die <xref:System.Windows.PropertyMetadata> Möglichkeit, <xref:System.Windows.DependencyProperty.Register%2A> <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> die mit den oder Methoden festzulegen. Obwohl Ihr Objekt über einen statischen Konstruktor verfügen könnte, der aufrufen soll, <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>ist dies nicht die optimale Lösung und wirkt sich auf die Leistung aus. Um eine optimale <xref:System.Windows.PropertyMetadata> Leistung zu <xref:System.Windows.DependencyProperty.Register%2A>erzielen, legen Sie die während des Aufrufs auf fest.  
  
<a name="Freezable_Objects"></a>
## <a name="freezable-objects"></a>Freezable-Objekte  
 A <xref:System.Windows.Freezable> ist ein spezieller Objekttyp, der zwei Zustände hat: nicht eingefroren und eingefroren. Wenn Sie Objekte immer dann, wenn es möglich ist, fixieren, wird dadurch die Leistung Ihrer Anwendung verbessert und ihr Workingset reduziert. Weitere Informationen finden Sie unter der [Übersicht über Freezable-Objekte](freezable-objects-overview.md).  
  
 Jedes <xref:System.Windows.Freezable> hat <xref:System.Windows.Freezable.Changed> ein Ereignis, das ausgelöst wird, wenn es sich ändert. Änderungsbenachrichtigungen nehmen jedoch einiges an Anwendungsleistung in Anspruch.  
  
 Betrachten Sie das folgende <xref:System.Windows.Shapes.Rectangle> Beispiel, <xref:System.Windows.Media.Brush> in dem jedes Objekt dasselbe Objekt verwendet:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 Stellt standardmäßig [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einen Ereignishandler <xref:System.Windows.Media.SolidColorBrush> für das <xref:System.Windows.Freezable.Changed> Objektereignis bereit, <xref:System.Windows.Shapes.Rectangle> um die <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft des Objekts ungültig zu machen. In diesem Fall muss <xref:System.Windows.Media.SolidColorBrush> der jedes <xref:System.Windows.Freezable.Changed> Mal, wenn das Ereignis ausgelöst <xref:System.Windows.Shapes.Rectangle>werden muss, die Rückruffunktion für jeden Aufruf erforderlich sein – die Akkumulation dieser Rückruffunktion,die Aufrufe dieser Rückruffunktion eine erhebliche Leistungseinbußen mit sich bringen. Darüber hinaus ist es sehr ressourcenintensiv, Handler an diesem Punkt hinzuzufügen und zu entfernen, da die Anwendung dazu die gesamte Liste durchlaufen müssten. Wenn sich das Anwendungsszenario nie an der <xref:System.Windows.Media.SolidColorBrush>ändert, werden Die Kosten für die unnötige Wartung <xref:System.Windows.Freezable.Changed> von Ereignishandlern nicht bezahlt.  
  
 Das <xref:System.Windows.Freezable> Einfrieren von a kann seine Leistung verbessern, da es keine Ressourcen mehr für die Verwaltung von Änderungsbenachrichtigungen aufwenden muss. Die folgende Tabelle zeigt die <xref:System.Windows.Media.SolidColorBrush> Größe <xref:System.Windows.Freezable.IsFrozen%2A> einer einfachen `true`Eigenschaft, wenn sie auf , im Vergleich zu dem Zeitpunkt, an dem sie nicht festgelegt ist, festgelegt ist. Dies setzt voraus, <xref:System.Windows.Shapes.Shape.Fill%2A> dass <xref:System.Windows.Shapes.Rectangle> ein Pinsel auf die Eigenschaft von zehn Objekten angewendet wird.  
  
|**State**|**Größe**|  
|---------------|--------------|  
|Gefroren<xref:System.Windows.Media.SolidColorBrush>|212 Bytes|  
|Nicht eingefroren<xref:System.Windows.Media.SolidColorBrush>|972 Bytes|  
  
 Im folgenden Codebeispiel wird dieses Konzept veranschaulicht:  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Durch geänderte Handler auf nicht fixierten Freezable-Objekte bleiben Objekte möglicherweise aktiv  
 Der Delegat, den <xref:System.Windows.Freezable> ein <xref:System.Windows.Freezable.Changed> Objekt an das Ereignis eines Objekts übergibt, ist im Grunde ein Verweis auf dieses Objekt. Daher <xref:System.Windows.Freezable.Changed> können Ereignishandler Objekte länger als erwartet am Leben erhalten. Beim Durchführen der Bereinigung eines Objekts, <xref:System.Windows.Freezable> das <xref:System.Windows.Freezable.Changed> sich zum Abhören des Objektereignisses registriert hat, ist es wichtig, diesen Delegaten zu entfernen, bevor das Objekt freigegeben wird.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]schließt auch <xref:System.Windows.Freezable.Changed> Ereignisse intern an. Beispielsweise werden alle Abhängigkeitseigenschaften, die als Wert wert sind, <xref:System.Windows.Freezable> Ereignisse automatisch abhören. <xref:System.Windows.Freezable.Changed> Die <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft, die <xref:System.Windows.Media.Brush>eine an an nimmt, veranschaulicht dieses Konzept.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 Bei der `myBrush` Zuweisung `myRectangle.Fill`von wird ein <xref:System.Windows.Shapes.Rectangle> Delegat, der <xref:System.Windows.Media.SolidColorBrush> auf <xref:System.Windows.Freezable.Changed> das Objekt verweist, dem Ereignis des Objekts hinzugefügt. Dies bedeutet, dass folgender Code `myRect` nicht zur automatischen Speicherbereinigung berechtigt:  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 In diesem `myBrush` Fall `myRectangle` wird immer noch am Leben gehalten <xref:System.Windows.Freezable.Changed> und wird zu ihm zurückrufen, wenn es sein Ereignis feuert. Beachten Sie, `myBrush` dass <xref:System.Windows.Shapes.Shape.Fill%2A> das Zuweisen <xref:System.Windows.Shapes.Rectangle> zur Eigenschaft eines `myBrush`neuen Objekts einfach einen weiteren Ereignishandler zu hinzufügt.  
  
 Die empfohlene Möglichkeit zum Bereinigen dieser Objekttypen besteht darin, die <xref:System.Windows.Media.Brush> aus der <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft zu entfernen, wodurch wiederum der <xref:System.Windows.Freezable.Changed> Ereignishandler entfernt wird.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>
## <a name="user-interface-virtualization"></a>Virtualisierung der Benutzeroberfläche  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet auch eine <xref:System.Windows.Controls.StackPanel> Variation des Elements, das datengebundene untergeordnete Inhalte automatisch "virtualisiert". In diesem Zusammenhang bezieht sich das Wort „virtualisieren“ auf eine Technik, mit der eine Teilmenge von Objekten aus einer größeren Menge von Datenelementen generiert wird, je nachdem, welche Elemente auf dem Bildschirm sichtbar sind. Es ist sowohl für den Arbeitsspeicher als auch für den Prozessor sehr aufwändig, eine große Menge an UI-Elementen zu generieren, wenn sich möglicherweise nur sehr wenige Elemente zu einer angegebenen Zeit auf einem Bildschirm befinden. <xref:System.Windows.Controls.VirtualizingStackPanel>(durch die <xref:System.Windows.Controls.VirtualizingPanel>von bereitgestellte Funktionalität) berechnet <xref:System.Windows.Controls.ItemContainerGenerator> sichtbare Elemente und arbeitet mit dem von einem <xref:System.Windows.Controls.ItemsControl> (z. B. <xref:System.Windows.Controls.ListBox> oder <xref:System.Windows.Controls.ListView>), um nur Elemente für sichtbare Elemente zu erstellen.  
  
 Zur Leistungsoptimierung werden visuelle Objekte für diese Elemente nur generiert oder aktiv gehalten, wenn sie auf dem Bildschirm sichtbar sind. Wenn sie sich nicht mehr im sichtbaren Bereich des Steuerelements befinden, können die visuellen Objekte entfernt werden. Dies ist nicht zu verwechseln mit Datenvirtualisierung, bei der Datenobjekte nicht alle in der lokalen Auflistung vorhanden sind, sondern bei Bedarf einfließen.  
  
 Die folgende Tabelle zeigt die verstrichene Zeit <xref:System.Windows.Controls.TextBlock> beim <xref:System.Windows.Controls.StackPanel> Hinzufügen <xref:System.Windows.Controls.VirtualizingStackPanel>und Rendern von 5000 Elementen zu a und a . In diesem Szenario stellen die Messungen die Zeit zwischen <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> dem Anfügen einer Textzeichenfolge an die Eigenschaft eines <xref:System.Windows.Controls.ItemsControl> Objekts zu dem Zeitpunkt dar, zu dem die Bedienfeldelemente die Textzeichenfolge anzeigen.  
  
|**Hostpanel**|**Renderingzeit (in ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>Weitere Informationen

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
