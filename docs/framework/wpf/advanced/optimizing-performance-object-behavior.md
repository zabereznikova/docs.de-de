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
ms.openlocfilehash: 025c8691eb1aaf9483a222530a5590670ede486b
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400467"
---
# <a name="optimizing-performance-object-behavior"></a>Optimieren der Leistung: Objektverhalten
Wenn Sie das Verhalten von systeminternen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekten verstehen, können Sie Funktionalität und Leistung optimal miteinander vereinen.  

<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>Wenn Ereignishandler nicht aus Objekten entfernt werden, bleiben diese möglicherweise aktiv  
 Der Delegat, den ein Objekt an sein Ereignis übergibt, ist gewissermaßen ein Verweis auf dieses Objekt. Aufgrund von Ereignishandlern können Objekte länger als erwartet aktiv sein. Wenn sie ein Objekt bereinigen, das registriert wurde, um auf ein Ereignis eines Objekts zu lauschen, ist es erforderlich, dass Sie diesen Delegaten entfernen, bevor Sie das Objekt freigeben. Wenn nicht benötigte Objekte weiter aktiv sind, erhöht dies die Speicherauslastung Ihrer Anwendung. Dies ist insbesondere dann der Fall, wenn das Objekt der Stamm einer logischen oder visuellen Struktur ist.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] führt ein schwaches Ereignislistenermuster für Ereignisse ein, das dann nützlich sein kann, wenn die Beziehungen der Objektlebensdauer zwischen Quelle und Listener schwierig zu überwachen sind. Einige vorhandene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignisse verwenden dieses Muster. Wenn Sie Objekte mit benutzerdefinierten Ereignissen implementieren, kann dieses Muster für Sie nützlich sein. Weitere Informationen finden Sie unter [Schwache Ereignismuster](weak-event-patterns.md).  
  
 Es gibt mehrere Tools, wie z.B. den CLR-Profiler und den Workingset-Viewer, die Informationen zur Speicherauslastung eines angegebenen Prozesses zur Verfügung stellen können. Der CLR-Profiler umfasst eine Reihe sehr nützlicher Ansichten des Belegungsprofils, darunter z.B. ein Histogramm der zugewiesenen Typen, Zuordnungs- und Aufrufdiagramme, eine Zeitachse mit den automatische Speicherbereinigungen verschiedener Generationen und der daraus entstehende Status des verwalteten Heaps nach diesen Bereinigungen sowie eine Aufrufstruktur, die Zuweisungen und Laden von Assemblys für jede Methode veranschaulicht. Weitere Informationen finden Sie unter [.NET Framework Developer Center](https://go.microsoft.com/fwlink/?LinkId=117435).  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>Anhängigkeitseigenschaften und Objekte  
 Im allgemeinen <xref:System.Windows.DependencyObject> ist der Zugriff auf eine Abhängigkeits Eigenschaft eines nicht langsamer als der Zugriff auf eine CLR-Eigenschaft. Der Aufwand für die Festlegung eines Eigenschafts Werts kann zwar geringfügig beeinträchtigt werden, aber das Erzielen eines Werts ist so schnell wie der Wert aus einer CLR-Eigenschaft. Der kleine Leistungsaufwand wird durch die Tatsache verursacht, dass Abhängigkeitseigenschaften zuverlässige Funktionen unterstützen, wie z.B. die Datenbindung, die Animation, die Vererbung und das Formatieren. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>DependencyProperty-Optimierungen  
 Sie sollten Abhängigkeitseigenschaften in Ihrer Anwendung sorgfältig definieren. Wenn Sie nur die Metadatenoptionen von "Rendering Type" und keine anderen Metadatenoptionen <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>wie z. b <xref:System.Windows.DependencyProperty> Weitere Informationen über das Überschreiben oder Abrufen von Eigenschaftenmetadaten finden Sie unter [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
 Möglicherweise ist es effizienter, mit einem Handler für Eigenschaftenänderungen die Messungs-, Anordnungs- und Rendering-Durchläufe manuell für ungültig zu erklären, wenn nicht alle Eigenschaftenänderungen „Messung“, „Anordnung“ und „Rendering“ betreffen. Möglicherweise möchten Sie einen Hintergrund nur dann erneut rendern, wenn ein Wert höher als ein festgelegter Grenzwert ist. In diesem Fall würde Ihr Handler für Eigenschaftenänderungen nur „render“ für ungültig erklären, wenn der festgelegte Grenzwert überschritten wird.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Sie können eine Abhängigkeitseigenschaft nicht frei vererben  
 Registrierte Abhängigkeitseigenschaften sind standardmäßig nicht vererbbar. Allerdings können Sie eine Eigenschaft explizit vererbbar machen. Obwohl dies nützlich ist, beeinträchtigt das Konvertieren einer Eigenschaft in eine vererbbare Eigenschaft die Leistung, da die Zeit für das Aufheben der Validierung erhöht wird.  
  
### <a name="use-registerclasshandler-carefully"></a>Verwenden Sie RegisterClassHandler mit Vorsicht  
 Beim Aufrufen <xref:System.Windows.EventManager.RegisterClassHandler%2A> von können Sie den Instanzstatus speichern. es ist jedoch wichtig zu beachten, dass der Handler für jede Instanz aufgerufen wird, was zu Leistungsproblemen führen kann. Verwenden <xref:System.Windows.EventManager.RegisterClassHandler%2A> Sie nur, wenn Ihre Anwendung erfordert, dass Sie den Instanzstatus speichern.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Legen Sie den Standardwert für eine Abhängigkeitseigenschaft während der Registrierung fest  
 Wenn Sie ein <xref:System.Windows.DependencyProperty> erstellen, das einen Standardwert erfordert, legen Sie den Wert mithilfe der Standard Metadaten fest, die <xref:System.Windows.DependencyProperty.Register%2A> als Parameter an <xref:System.Windows.DependencyProperty>die-Methode von übergeben werden. Nutzen Sie diese Vorgehensweise, statt den Eigenschaftswert in einem Konstruktor oder in jeder Instanz des Elements festzulegen.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Festlegen des Werts der Metadaten der Eigenschaft mit der Register-Methode  
 Beim Erstellen <xref:System.Windows.DependencyProperty>von haben Sie die Möglichkeit, die <xref:System.Windows.PropertyMetadata> mithilfe der <xref:System.Windows.DependencyProperty.Register%2A> -Methode oder <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> der-Methode festzulegen. Obwohl das Objekt über einen statischen Konstruktor verfügen kann, <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>um aufzurufen, ist dies nicht die optimale Lösung und wirkt sich auf die Leistung aus. Legen Sie <xref:System.Windows.PropertyMetadata> <xref:System.Windows.DependencyProperty.Register%2A>für eine optimale Leistung die während des Aufrufes fest.  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Freezable-Objekte  
 Ein <xref:System.Windows.Freezable> ist ein spezieller Objekttyp, der zwei Zustände aufweist: nicht fixiert und fixiert. Wenn Sie Objekte immer dann, wenn es möglich ist, fixieren, wird dadurch die Leistung Ihrer Anwendung verbessert und ihr Workingset reduziert. Weitere Informationen finden Sie unter der [Übersicht über Freezable-Objekte](freezable-objects-overview.md).  
  
 Jedes <xref:System.Windows.Freezable> verfügt über <xref:System.Windows.Freezable.Changed> ein-Ereignis, das ausgelöst wird, wenn es sich ändert. Änderungsbenachrichtigungen nehmen jedoch einiges an Anwendungsleistung in Anspruch.  
  
 Sehen Sie sich das folgende Beispiel an <xref:System.Windows.Shapes.Rectangle> , in dem <xref:System.Windows.Media.Brush> jeweils das gleiche Objekt verwendet wird:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 Standardmäßig stellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einen Ereignishandler für das- <xref:System.Windows.Media.SolidColorBrush> Ereignis des <xref:System.Windows.Freezable.Changed> -Objekts bereit, um die- <xref:System.Windows.Shapes.Rectangle> Eigenschaft des <xref:System.Windows.Shapes.Shape.Fill%2A> -Objekts für ungültig zu erklären. In diesem Fall muss jedes Mal, <xref:System.Windows.Media.SolidColorBrush> wenn das- <xref:System.Windows.Freezable.Changed> Ereignis auslösen muss, die Rückruffunktion für jede <xref:System.Windows.Shapes.Rectangle>– aufrufen. die Ansammlung dieser Rückruf Funktionsaufrufe verursachen einen erheblichen Leistungsabfall. Darüber hinaus ist es sehr ressourcenintensiv, Handler an diesem Punkt hinzuzufügen und zu entfernen, da die Anwendung dazu die gesamte Liste durchlaufen müssten. Wenn sich das <xref:System.Windows.Media.SolidColorBrush>Anwendungsszenario nie ändert, werden Sie die Kosten für eine unnötige Wartung <xref:System.Windows.Freezable.Changed> von Ereignis Handlern bezahlen.  
  
 Das Einfrieren <xref:System.Windows.Freezable> einer kann die Leistung verbessern, da Sie nicht mehr Ressourcen zum Verwalten von Änderungs Benachrichtigungen aufwenden muss. In der folgenden Tabelle wird die Größe einer einfachen <xref:System.Windows.Media.SolidColorBrush> angezeigt, <xref:System.Windows.Freezable.IsFrozen%2A> wenn die-Eigenschaft `true`auf festgelegt ist. Dies setzt voraus, dass ein Pinsel <xref:System.Windows.Shapes.Shape.Fill%2A> auf die- <xref:System.Windows.Shapes.Rectangle> Eigenschaft von zehn-Objekten angewendet wird.  
  
|**Zustand**|**Größe**|  
|---------------|--------------|  
|Gefror<xref:System.Windows.Media.SolidColorBrush>|212 Bytes|  
|Nicht fixiert<xref:System.Windows.Media.SolidColorBrush>|972 Bytes|  
  
 Im folgenden Codebeispiel wird dieses Konzept veranschaulicht:  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Durch geänderte Handler auf nicht fixierten Freezable-Objekte bleiben Objekte möglicherweise aktiv  
 Der Delegat, den ein Objekt an <xref:System.Windows.Freezable> das- <xref:System.Windows.Freezable.Changed> Ereignis eines-Objekts übergibt, ist tatsächlich ein Verweis auf dieses Objekt. Daher können <xref:System.Windows.Freezable.Changed> Ereignishandler die Objekte länger als erwartet beibehalten. Wenn Sie ein Objekt bereinigen, das registriert wurde, um auf das <xref:System.Windows.Freezable> -Ereignis <xref:System.Windows.Freezable.Changed> eines-Objekts zu lauschen, ist es von entscheidender Bedeutung, diesen Delegaten vor der Freigabe des-Objekts zu entfernen.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Freezable.Changed> verknüpft Ereignisse auch intern. Alle Abhängigkeits Eigenschaften, die <xref:System.Windows.Freezable> als Wert verwenden, lauschen z. b. automatisch auf <xref:System.Windows.Freezable.Changed> Ereignisse. Die <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft, die einen <xref:System.Windows.Media.Brush>annimmt, veranschaulicht dieses Konzept.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 Bei der Zuweisung von `myBrush` zu `myRectangle.Fill`wird ein Delegat, der auf <xref:System.Windows.Shapes.Rectangle> das-Objekt zurück zeigt, <xref:System.Windows.Media.SolidColorBrush> dem- <xref:System.Windows.Freezable.Changed> Ereignis des-Objekts hinzugefügt. Dies bedeutet, dass folgender Code `myRect` nicht zur automatischen Speicherbereinigung berechtigt:  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 In diesem Fall `myBrush` bleibt `myRectangle` immer noch aktiv und wird zurück aufgerufen, wenn <xref:System.Windows.Freezable.Changed> das Ereignis ausgelöst wird. Beachten Sie, `myBrush` dass bei <xref:System.Windows.Shapes.Shape.Fill%2A> der Zuweisung zur- <xref:System.Windows.Shapes.Rectangle> Eigenschaft einer neuen ein anderer Ereignishandler `myBrush`zu hinzugefügt wird.  
  
 Die empfohlene Vorgehensweise zum Bereinigen dieser Objekttypen besteht darin, den <xref:System.Windows.Media.Brush> aus der <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft zu entfernen, wodurch wiederum der <xref:System.Windows.Freezable.Changed> -Ereignishandler entfernt wird.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>Virtualisierung der Benutzeroberfläche  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet auch eine Variation des <xref:System.Windows.Controls.StackPanel> Elements, das automatisch Daten gebundenen untergeordneten Inhalt "virtualisiert". In diesem Zusammenhang bezieht sich das Wort „virtualisieren“ auf eine Technik, mit der eine Teilmenge von Objekten aus einer größeren Menge von Datenelementen generiert wird, je nachdem, welche Elemente auf dem Bildschirm sichtbar sind. Es ist sowohl für den Arbeitsspeicher als auch für den Prozessor sehr aufwändig, eine große Menge an UI-Elementen zu generieren, wenn sich möglicherweise nur sehr wenige Elemente zu einer angegebenen Zeit auf einem Bildschirm befinden. <xref:System.Windows.Controls.VirtualizingStackPanel>( <xref:System.Windows.Controls.VirtualizingPanel>durch die von bereitgestellte Funktionalität) berechnet sichtbare Elemente und funktioniert mit dem <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ItemContainerGenerator> <xref:System.Windows.Controls.ListBox> von einem (z <xref:System.Windows.Controls.ListView>. b. oder), um nur Elemente für sichtbare Elemente zu erstellen.  
  
 Zur Leistungsoptimierung werden visuelle Objekte für diese Elemente nur generiert oder aktiv gehalten, wenn sie auf dem Bildschirm sichtbar sind. Wenn sie sich nicht mehr im sichtbaren Bereich des Steuerelements befinden, können die visuellen Objekte entfernt werden. Dies ist nicht zu verwechseln mit Datenvirtualisierung, bei der Datenobjekte nicht alle in der lokalen Auflistung vorhanden sind, sondern bei Bedarf einfließen.  
  
 Die folgende Tabelle zeigt die verstrichene Zeit zum hinzu <xref:System.Windows.Controls.TextBlock> fügen und Rendern von <xref:System.Windows.Controls.VirtualizingStackPanel>5000 Elementen zu einem <xref:System.Windows.Controls.StackPanel> und einem. In diesem Szenario stellen die Messungen die Zeit zwischen dem Anfügen <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ItemsControl> einer Text Zeichenfolge an die-Eigenschaft eines Objekts dar, die dem Zeitpunkt entspricht, an dem die Panel-Elemente die Text Zeichenfolge anzeigen.  
  
|**Hostpanel**|**Renderingzeit (in ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>Siehe auch

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
