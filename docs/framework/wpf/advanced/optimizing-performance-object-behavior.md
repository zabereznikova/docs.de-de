---
title: "Optimieren der Leistung: Objektverhalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Abhängigkeitseigenschaften, Leistung"
  - "Ereignishandler [WPF]"
  - "Freezable-Objekte, Leistung"
  - "Objektleistungsaspekte"
  - "Virtualisierung der Benutzeroberfläche"
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Optimieren der Leistung: Objektverhalten
Wenn Sie das systeminterne Verhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Objekten kennen, können Sie leichter zwischen Funktionalität und Leistung abwägen.  
  
   
  
<a name="Not_Removing_Event_Handlers"></a>   
## Durch nicht entfernte Ereignishandler am Objekt werden die Objekte möglicherweise als aktiv beibehalten  
 Der Delegat, den ein Objekt an sein Ereignis übergibt, ist gewissermaßen ein Verweis auf dieses Objekt.  Deshalb können Ereignishandler Objekte länger als erwartet als aktiv beibehalten.  Wenn Sie ein Objekt bereinigen, das zur Überwachung eines Objektereignisses registriert wurde, müssen Sie vor der Freigabe des Objekts den entsprechenden Delegaten entfernen.  Als aktiv beibehaltene und nicht mehr benötigte Objekte führen dazu, dass die Anwendung mehr Arbeitsspeicher benötigt.  Dies trifft insbesondere dann zu, wenn es sich bei dem Objekt um den Stamm einer [logischen Struktur](GTMT) oder einer [visuellen Struktur](GTMT) handelt.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] führt für Ereignisse ein Muster für schwache Ereignislistener ein, das besonders hilfreich ist, wenn die Objektlebensdauerbeziehungen zwischen Quelle und Listener schwer zu verfolgen sind.  Einige vorhandene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignisse verwenden dieses Muster.  Wenn Sie Objekte mit benutzerdefinierten Ereignissen implementieren, kann Ihnen dieses Muster von Nutzen sein.  Ausführliche Informationen finden Sie unter [Schwache Ereignismuster](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).  
  
 Es gibt mehrere Tools, z. B. CLR\-Profiler und Workingset\-Viewer, die Informationen zur Arbeitsspeichernutzung eines angegebenen Prozesses bereitstellen können.  Der CLR\-Profiler enthält eine Reihe sehr nützlicher Ansichten des Zuordnungsprofils. Dazu gehören ein Histogramm der zugeordneten Typen, Zuordnungs\- und Aufrufdiagramme, eine Zeitleiste mit den Garbage Collections der verschiedenen Generationen und dem resultierenden Status des verwalteten Heaps nach den Collections sowie eine Aufrufstruktur, die die Zuordnungen pro Methode sowie die Assemblyladevorgänge anzeigt.  Informationen finden Sie unter [.NET Framework Developer Center](http://go.microsoft.com/fwlink/?LinkId=117435).  
  
<a name="DPs_and_Objects"></a>   
## Abhängigkeitseigenschaften und Objekte  
 Im Allgemeinen ist das Zugreifen auf eine [Abhängigkeitseigenschaft](GTMT) von einem <xref:System.Windows.DependencyObject> nicht langsamer als das Zugreifen auf eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaft.  Das Festlegen eines Eigenschaftswerts beansprucht zwar geringfügig mehr Leistung, aber das Abrufen eines Werts erfolgt so schnell wie das Abrufen eines Werts aus einer [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaft.  Der geringfügig höhere Leistungsbedarf wird dadurch ausgeglichen, dass [Abhängigkeitseigenschaften](GTMT) robuste Features, z. B. Datenbindung, Animation, Vererbung und Formatierung, unterstützen.  Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
### DependencyProperty\-Optimierungen  
 Sie sollten [Abhängigkeitseigenschaften](GTMT) in der Anwendung sehr sorgfältig definieren.  Wenn sich die <xref:System.Windows.DependencyProperty> nur auf Rendering\-Metadatenoptionen und nicht auf andere Metadatenoptionen auswirkt, z. B. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, sollten Sie sie entsprechend kennzeichnen, indem Sie ihre Metadaten überschreiben.  Weitere Informationen über das Überschreiben oder Abrufen von Eigenschaftenmetadaten finden Sie unter [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 Wenn sich nicht alle Eigenschaftenänderungen auf Measure, Anordnung und Rendering auswirken, kann es sich als effizienter erweisen, wenn Sie mithilfe eines Handlers für Eigenschaftenänderungen Measure\-, Anordnungs\- und Renderingläufe außer Kraft setzen.  Beispiel: Sie möchten einen Hintergrund nur dann erneut rendern, wenn ein Wert den festgelegten Grenzwert überschreitet.  In diesem Fall würde der Handler der Eigenschaftenänderungen das Rendern nur dann außer Kraft setzen, wenn der Wert den festgelegten Grenzwert überschreitet.  
  
### DependencyProperty\-Vererbung hat Leistungseinbußen zur Folge  
 Standardmäßig sind registrierte [Abhängigkeitseigenschaften](GTMT) nicht vererbbar.  Sie können jedoch jede Eigenschaft explizit als vererbbar ausweisen.  Obwohl dies ein nützliches Feature ist, wirken sich Eigenschaften, die zu einer vererbbaren Eigenschaft konvertiert wurden, auf die Leistung aus, da die Ungültigkeitserklärung von Eigenschaften mehr Zeit in Anspruch nimmt.  
  
### Sorgfältiges Verwenden von RegisterClassHandler  
 Sie können durch den Aufruf von <xref:System.Windows.EventManager.RegisterClassHandler%2A> zwar den Zustand der Instanz speichern, sollten aber beachten, dass der Handler in jeder Instanz aufgerufen wird, was zu Leistungseinbußen führen kann.  Verwenden Sie <xref:System.Windows.EventManager.RegisterClassHandler%2A> nur dann, wenn die Anwendung das Speichern des Instanzenzustands erfordert.  
  
### Festlegen des Standardwerts für eine DependencyProperty während der Registrierung  
 Wenn Sie eine <xref:System.Windows.DependencyProperty> erstellen, die einen Standardwert erfordert, legen Sie den Wert mithilfe der Standardmetadaten fest, die als Parameter an die <xref:System.Windows.DependencyProperty.Register%2A>\-Methode der <xref:System.Windows.DependencyProperty> übergeben wurden.  Verwenden Sie dieses Verfahren, anstatt den Eigenschaftswert in einem Konstruktor oder in jeder Instanz eines Elements festzulegen.  
  
### Festlegen des PropertyMetadata\-Werts mit Register  
 Wenn Sie eine <xref:System.Windows.DependencyProperty> erstellen, können Sie die <xref:System.Windows.PropertyMetadata> wahlweise anhand der <xref:System.Windows.DependencyProperty.Register%2A>\-Methode oder der <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>\-Methode festlegen.  Das Objekt könnte zwar zum Aufruf von <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> einen statischen Konstruktor verwenden, was jedoch keine optimale Lösung darstellt und Leistungseinbußen zur Folge hat.  Um die beste Leistung zu erhalten, legen Sie die <xref:System.Windows.PropertyMetadata> während des Aufrufs auf <xref:System.Windows.DependencyProperty.Register%2A> fest.  
  
<a name="Freezable_Objects"></a>   
## Freezable\-Objekte  
 Ein <xref:System.Windows.Freezable> ist ein besonderer Typ von Objekt, das zwei Zustände aufweisen kann: nicht fixiert und fixiert.  Sie sollten Objekte nach Möglichkeit fixieren, um die Leistung der Anwendung zu verbessern und deren Workingset zu reduzieren.  Weitere Informationen finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Jedes <xref:System.Windows.Freezable> verfügt über ein <xref:System.Windows.Freezable.Changed>\-Ereignis, das immer dann ausgelöst wird, wenn sich das Objekt ändert.  Änderungsbenachrichtigungen sind jedoch im Hinblick auf die Anwendungsleistung aufwendig.  
  
 Betrachten Sie das folgende Beispiel, in dem jedes <xref:System.Windows.Shapes.Rectangle> das gleiche <xref:System.Windows.Media.Brush>\-Objekt verwendet:  
  
 [!code-csharp[Performance#PerformanceSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt standardmäßig einen Ereignishandler für das <xref:System.Windows.Freezable.Changed>\-Ereignis des <xref:System.Windows.Media.SolidColorBrush>\-Objekts bereit, um die <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft des <xref:System.Windows.Shapes.Rectangle>\-Objekts außer Kraft zu setzen.  In diesem Fall muss das <xref:System.Windows.Media.SolidColorBrush>\-Objekt bei jedem Auslösen des <xref:System.Windows.Freezable.Changed>\-Ereignisses die Rückruffunktion für jedes <xref:System.Windows.Shapes.Rectangle> aufrufen. Die Anhäufung dieser Rückruffunktionsaufrufe führt zu erheblichen Leistungseinbußen.  Außerdem ist das Hinzufügen und Entfernen von Handlern zu diesem Zeitpunkt sehr ressourcenintensiv, da die Anwendung dazu die gesamte Liste durchlaufen müsste.  Wenn in Ihrem Anwendungsszenario <xref:System.Windows.Media.SolidColorBrush> nie geändert wird, müssten Sie einen unnötigen Aufwand zur Verwaltung der <xref:System.Windows.Freezable.Changed>\-Ereignishandler betreiben.  
  
 Das Fixieren eines <xref:System.Windows.Freezable>\-Objekts kann zu Leistungsverbesserungen führen, da es keine Ressourcen mehr für die Verwaltung der Änderungsbenachrichtigungen verbrauchen muss.  Die folgende Tabelle zeigt die Größe eines einfachen <xref:System.Windows.Media.SolidColorBrush>\-Objekts, dessen <xref:System.Windows.Freezable.IsFrozen%2A>\-Eigenschaft auf `true` festgelegt ist, im Vergleich zu einem nicht fixierten Objekt.  Dabei wird davon ausgegangen, dass ein Pinsel auf die <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft von zehn <xref:System.Windows.Shapes.Rectangle>\-Objekten angewendet wird.  
  
|**Zustand**|**Größe**|  
|-----------------|---------------|  
|<xref:System.Windows.Media.SolidColorBrush> ist fixiert|212 Bytes|  
|<xref:System.Windows.Media.SolidColorBrush> ist nicht fixiert|972 Bytes|  
  
 Im folgenden Codebeispiel wird dieses Konzept veranschaulicht:  
  
 [!code-csharp[Performance#PerformanceSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### Durch geänderte Handler für nicht fixierte Freezable\-Objekte werden Objekte möglicherweise als aktiv beibehalten  
 Der Delegat, den ein Objekt an ein <xref:System.Windows.Freezable.Changed>\-Ereignis eines <xref:System.Windows.Freezable>\-Objekts übergibt, ist gewissermaßen ein Verweis auf dieses Objekt.  Deshalb können <xref:System.Windows.Freezable.Changed>\-Ereignishandler Objekte länger als erwartet als aktiv beibehalten.  Wenn Sie ein Objekt bereinigen, das zur Überwachung des <xref:System.Windows.Freezable.Changed>\-Ereignisses eines <xref:System.Windows.Freezable>\-Objekts registriert wurde, müssen Sie vor der Freigabe des Objekts den entsprechenden Delegaten entfernen.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nimmt außerdem eine interne Verknüpfung der <xref:System.Windows.Freezable.Changed>\-Ereignisse vor.  Zum Beispiel überwachen alle [Abhängigkeitseigenschaften](GTMT), die <xref:System.Windows.Freezable> als Wert übernehmen, die <xref:System.Windows.Freezable.Changed>\-Ereignisse automatisch.  Die <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft, die einen <xref:System.Windows.Media.Brush> annimmt, illustriert dieses Konzept.  
  
 [!code-csharp[Performance#PerformanceSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 Bei der Zuordnung von `myBrush` zu `myRectangle.Fill` wird ein auf das <xref:System.Windows.Shapes.Rectangle>\-Objekt zurückweisender Delegat zum <xref:System.Windows.Freezable.Changed>\-Ereignis des <xref:System.Windows.Media.SolidColorBrush>\-Objekts hinzugefügt.  Dies bedeutet, dass im folgenden Code `myRect` nicht für die Garbage Collection freigegeben wird:  
  
 [!code-csharp[Performance#PerformanceSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 In diesem Fall wird durch `myBrush` das Objekt `myRectangle` als aktiv beibehalten und erneut aufgerufen, wenn das <xref:System.Windows.Freezable.Changed>\-Ereignis ausgelöst wird.  Beachten Sie, dass die Zuordnung von `myBrush` zu der <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft eines neuen <xref:System.Windows.Shapes.Rectangle>\-Objekts einfach einen weiteren Ereignishandler an `myBrush` hinzufügt.  
  
 Um diese Objekttypen zu bereinigen, wird empfohlen, dass Sie <xref:System.Windows.Media.Brush> aus der <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft löschen, wodurch wiederum der <xref:System.Windows.Freezable.Changed>\-Ereignishandler gelöscht wird.  
  
 [!code-csharp[Performance#PerformanceSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## Virtualisierung der Benutzeroberfläche  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt außerdem eine Variante des <xref:System.Windows.Controls.StackPanel>\-Elements bereit, das datengebundenen untergeordneten Inhalt automatisch "virtualisiert".  In diesem Zusammenhang bezeichnet "virtualisieren" eine Vorgehensweise, bei der eine Teilmenge von Objekten aus einer größeren Anzahl von Datenelementen generiert wird, wobei berücksichtigt wird, welche Elemente auf dem Bildschirm angezeigt werden.  Das Generieren einer großen Anzahl von Benutzeroberflächenelementen nimmt sehr viel Arbeitsspeicher und Prozessorleistung in Anspruch, auch wenn jeweils nur einige der Elemente auf dem Bildschirm angezeigt werden.  <xref:System.Windows.Controls.VirtualizingStackPanel> \(mithilfe der Funktionen von <xref:System.Windows.Controls.VirtualizingPanel>\) berechnet die sichtbaren Elemente und erstellt dann zusammen mit dem <xref:System.Windows.Controls.ItemContainerGenerator> aus einem <xref:System.Windows.Controls.ItemsControl> \(z. B. einem <xref:System.Windows.Controls.ListBox> oder einer <xref:System.Windows.Controls.ListView>\) nur die Elemente für die sichtbaren Elemente  
  
 Im Sinne der Leistungsoptimierung werden visuelle Objekte nur dann für diese Elemente generiert oder als aktiv beibehalten, wenn sie auf dem Bildschirm angezeigt werden.  Wenn sie sich nicht mehr im Anzeigebereich des Steuerelements befinden, können die visuellen Objekte entfernt werden.  Dies darf nicht mit der Datenvirtualisierung verwechselt werden, bei der nicht alle Datenobjekte in der lokalen Auflistung vorhanden sind, sondern bei Bedarf als Stream geladen werden.  
  
 Die folgende Tabelle veranschaulicht die Zeitdauer, die zum Hinzufügen und Rendern von 5000 <xref:System.Windows.Controls.TextBlock>\-Elementen in einem <xref:System.Windows.Controls.StackPanel> und einem <xref:System.Windows.Controls.VirtualizingStackPanel> benötigt wird.  In diesem Szenario stehen die Messwerte für die Zeit, die ab dem Hinzufügen einer Textzeichenfolge zur <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft eines <xref:System.Windows.Controls.ItemsControl>\-Objekts bis zu dem Zeitpunkt verstrichen ist, zu dem die Bereichselemente die Textzeichenfolge darstellen.  
  
|**Hostbereich**|**Renderzeit \(ms\)**|  
|---------------------|---------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## Siehe auch  
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Nutzen der Vorteile der Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)