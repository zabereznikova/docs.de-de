---
title: "Optimieren der Leistung: Layout und Entwurf | Microsoft Docs"
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
  - "Entwurfsaspekte"
  - "Layoutdurchlauf"
  - "Layout, Optimieren der Leistung"
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Optimieren der Leistung: Layout und Entwurf
Der Entwurf Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung kann deren Leistung durch unnötigen Verwaltungsaufwand bei der Berechnung des Layouts und bei der Überprüfung von Objektverweisen beeinflussen.  Das Erstellen von Objekten, besonders zur Laufzeit, kann sich im Leistungsverhalten der Anwendung bemerkbar machen.  
  
 Dieses Thema enthält Empfehlungen zur Leistungssteigerung in diesen Bereichen.  
  
## Layout  
 Der Begriff "Layoutdurchlauf" beschreibt den Vorgang des Messens und Anordnens der Member einer Auflistung untergeordneter Elemente eines von <xref:System.Windows.Controls.Panel> abgeleiteten Objekts und deren anschließender Zeichnung auf dem Bildschirm.  Der Layoutdurchlauf ist ein rechenintensiver Vorgang. Je mehr untergeordnete Elemente sich in der Auflistung befinden, desto mehr Rechenschritte sind nötig.  Jedes Mal, wenn ein untergeordnetes <xref:System.Windows.UIElement>\-Objekt in der Auflistung seine Position ändert, kann ein neuer Durchlauf des Layoutsystems ausgelöst werden.  Aufgrund der engen Beziehung zwischen Objektmerkmalen und Layoutverhalten ist ein Verständnis der Ereignistypen wichtig, die das Layoutsystem aufrufen können.  Die Anwendung bietet eine bessere Leistung, wenn möglichst wenige unnötige Aufrufe des Layoutdurchlaufs erfolgen.  
  
 Das Layoutsystem führt pro untergeordnetem Member in einer Auflistung zwei Durchläufe aus: eine Maßübergabe und eine Anordnungsübergabe.  Jedes untergeordnete Objekt bietet eine eigene überschriebene Implementierung der <xref:System.Windows.UIElement.Measure%2A>\-Methode und der <xref:System.Windows.UIElement.Arrange%2A>\-Methode, um sein eigenes spezifisches Layoutverhalten bereitzustellen.  Im einfachsten Fall ist das Layout ein rekursives System, das dafür sorgt, dass ein Element in der Größe angepasst, positioniert und auf dem Bildschirm gezeichnet wird.  
  
-   Ein untergeordnetes <xref:System.Windows.UIElement>\-Objekt startet den Layoutvorgang, indem zuerst dessen Kerneigenschaften gemessen werden.  
  
-   Die <xref:System.Windows.FrameworkElement>\-Eigenschaften des Objekts, die mit der Größe zusammenhängen, z. B. <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Margin%2A>, werden ausgewertet.  
  
-   Die spezifische Logik von <xref:System.Windows.Controls.Panel>, z. B. die <xref:System.Windows.Controls.DockPanel.Dock%2A>\-Eigenschaft von <xref:System.Windows.Controls.DockPanel> oder die <xref:System.Windows.Controls.StackPanel.Orientation%2A>\-Eigenschaft von <xref:System.Windows.Controls.StackPanel>, wird angewendet.  
  
-   Der Inhalt wird angeordnet bzw. positioniert, nachdem alle untergeordneten Objekte gemessen wurden.  
  
-   Die Auflistung von untergeordneten Objekten wird auf dem Bildschirm gezeichnet.  
  
 Der Layoutdurchlaufprozess wird erneut aufgerufen, wenn eine der folgenden Aktionen ausgeführt wird:  
  
-   Der Auflistung wird ein untergeordnetes Objekt hinzugefügt.  
  
-   Eine <xref:System.Windows.FrameworkElement.LayoutTransform%2A> wird auf das untergeordnete Objekt angewendet.  
  
-   Die <xref:System.Windows.UIElement.UpdateLayout%2A>\-Methode wird für das untergeordnete Objekt aufgerufen.  
  
-   Wenn der Wert einer [Abhängigkeitseigenschaft](GTMT), die mit Metadaten markiert ist, die die Maß\- oder Anordnungsübergaben betreffen, geändert wird.  
  
### Verwenden des effizientesten Panels \(nach Möglichkeit\)  
 Die Komplexität des Layoutvorgangs basiert direkt auf dem Layoutverhalten der von <xref:System.Windows.Controls.Panel> abgeleiteten Elemente, die verwendet werden.  So bietet ein <xref:System.Windows.Controls.Grid>\-Steuerelement oder ein <xref:System.Windows.Controls.StackPanel>\-Steuerelement viel mehr Funktionen als ein <xref:System.Windows.Controls.Canvas>\-Steuerelement.  Der Preis für diese Mehrzahl an Funktionen ist eine stärkere Beeinträchtigung der Leistung.  Wenn Sie allerdings die Funktionen eines <xref:System.Windows.Controls.Grid>\-Steuerelements nicht benötigen, sollten Sie die weniger leistungsbeeinträchtigenden Alternativen verwenden, z. B. <xref:System.Windows.Controls.Canvas> oder ein benutzerdefiniertes Panel.  
  
 Weitere Informationen finden Sie unter [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md).  
  
### Aktualisieren statt Ersetzen von RenderTransform  
 Sie können eine <xref:System.Windows.Media.Transform> aktualisieren statt sie als Wert einer <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft zu ersetzen.  Dies gilt insbesondere für Szenarien, die Animationen einschließen.  Durch die Aktualisierung einer vorhandenen <xref:System.Windows.Media.Transform> vermeiden Sie eine unnötige Layoutberechnung.  
  
### Erstellen der Struktur mithilfe eines Top\-Down\-Ansatzes  
 Wenn der [logischen Struktur](GTMT) ein Knoten hinzugefügt oder daraus entfernt wird, werden Ungültigkeitserklärungen von Eigenschaften für das übergeordnete Element des Knotens und alle untergeordneten Elemente ausgelöst.  Daher sollte immer ein Konstruktionsmuster mit einem Top\-Down\-Ansatz gewählt werden, um den Aufwand für unnötige Ungültigkeitserklärungen von Knoten, die bereits überprüft wurden, zu vermeiden.  In der folgenden Tabelle ist der Unterschied in der Ausführungsgeschwindigkeit aufgeführt, wenn eine Struktur mit dem Top\-Down\-Ansatz bzw. mit dem Bottom\-Up\-Ansatz erstellt wird, wobei die Struktur 150 Ebenen tief ist mit einem einzelnen <xref:System.Windows.Controls.TextBlock> und einem <xref:System.Windows.Controls.DockPanel> auf jeder Ebene.  
  
|**Aktion**|**Strukturerstellung \(in ms\)**|**Rendern \- einschließlich Strukturerstellung \(in ms\)**|  
|----------------|--------------------------------------|----------------------------------------------------------------|  
|Bottom\-Up\-Ansatz|366|454|  
|Top\-Down\-Ansatz|11|96|  
  
 Im folgenden Codebeispiel wird das Erstellen einer Struktur mit dem Top\-Down\-Ansatz gezeigt.  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
## Siehe auch  
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Nutzen der Vorteile der Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Projektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)