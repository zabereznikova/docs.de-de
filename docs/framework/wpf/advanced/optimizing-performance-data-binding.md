---
title: "Optimieren der Leistung: Datenbindung | Microsoft Docs"
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
  - "Binden von Daten, Leistung"
  - "Datenbindung, Leistung"
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Optimieren der Leistung: Datenbindung
Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Datenbindung bietet für Anwendungen eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren.  Elemente können an Daten aus einer Vielzahl von Datenquellen in Form von [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekten und [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] gebunden werden.  
  
 Dieses Thema enthält Empfehlungen zur Leistungssteigerung bei der Datenbindung.  
  
   
  
<a name="HowDataBindingReferencesAreResolved"></a>   
## Auflösen von Datenbindungsverweisen  
 Bevor Leistungsfragen der Datenbindung erläutert werden, lohnt es sich zu untersuchen, wie das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Datenbindungsmodul Objektverweise für die Bindung auflöst.  
  
 Die Quelle einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Datenbindung kann ein beliebiges [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekt sein.  Die Bindung kann an Eigenschaften, Untereigenschaften oder Indexer eines [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekts erfolgen.  Die Bindungsverweise werden mit [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)]\-Reflektion oder einem <xref:System.ComponentModel.ICustomTypeDescriptor> aufgelöst.  Im Folgenden finden Sie drei Methoden zum Auflösen von Objektverweisen zur Bindung.  
  
 Die erste Methode verwendet dazu Reflektion.  In diesem Fall werden mit dem <xref:System.Reflection.PropertyInfo>\-Objekt die Attribute der Eigenschaft ermittelt. Dieses Objekt bietet auch Zugriff auf die Metadaten der Eigenschaft.  Wenn die <xref:System.ComponentModel.ICustomTypeDescriptor>\-Schnittstelle verwendet wird, greift das Datenbindungsmodul mithilfe dieser Schnittstelle auf die Eigenschaftswerte zu.  Die <xref:System.ComponentModel.ICustomTypeDescriptor>\-Schnittstelle ist insbesondere in Fällen hilfreich, bei denen das Objekt nicht über einen statischen Eigenschaftensatz verfügt.  
  
 Benachrichtigungen über Eigenschaftenänderungen können durch Implementierung der <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle oder durch Verwendung der dem <xref:System.ComponentModel.TypeDescriptor> zugeordneten Änderungsbenachrichtigungen bereitgestellt werden.  Die bevorzugte Strategie zur Implementierung von Benachrichtigungen über Eigenschaftenänderungen ist aber die Verwendung von <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Wenn das Quellobjekt ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekt und die Quelleigenschaft eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaft ist, muss das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Datenbindungsmodul für das Quellobjekt zuerst Reflektion verwenden, um den <xref:System.ComponentModel.TypeDescriptor> abzurufen, und dann einen <xref:System.ComponentModel.PropertyDescriptor> abfragen.  Unter Leistungsaspekten ist diese Abfolge von Reflektionsvorgängen unter Umständen äußerst zeitaufwändig.  
  
 Die zweite Methode zum Auflösen von Objektverweisen verwendet ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Quellobjekt, das die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle implementiert, und eine Quelleigenschaft, bei der es sich um eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaft handelt.  In diesem Fall verwendet das Datenbindungsmodul Reflektion direkt für den Quelltyp und ruft die benötigte Eigenschaft ab.  Hierbei handelt es sich immer noch nicht um die optimale Methode, sie kommt aber mit weniger Anforderungen an das Workingset aus als die erste Methode.  
  
 Die dritte Methode zum Auflösen von Objektverweisen verwendet ein Quellobjekt, das ein <xref:System.Windows.DependencyObject> ist, und eine Quelleigenschaft, die eine <xref:System.Windows.DependencyProperty> ist.  In diesem Fall muss das Datenbindungsmodul keine Reflektion verwenden.  Stattdessen lösen das Eigenschaftenmodul und das Datenbindungsmodul den Eigenschaftenverweis unabhängig voneinander auf.  Dies ist die optimale Methode zum Auflösen von Objektverweisen, die zur Datenbindung verwendet werden.  
  
 In der Tabelle unten wird die Geschwindigkeit der Datenbindung der <xref:System.Windows.Controls.TextBlock.Text%2A>\-Eigenschaft von eintausend <xref:System.Windows.Controls.TextBlock>\-Elementen bei Verwendung der drei Methoden verglichen.  
  
|**Binden der Text\-Eigenschaft von TextBlock**|**Bindungszeit \(ms\)**|**Zeit zum Rendern \- inklusive Bindung \(ms\)**|  
|----------------------------------------------------|-----------------------------|------------------------------------------------------|  
|An eine Eigenschaft eines [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekts|115|314|  
|An eine Eigenschaft eines [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekts, das <xref:System.ComponentModel.INotifyPropertyChanged> implementiert|115|305|  
|An eine <xref:System.Windows.DependencyProperty> von einem <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## Bindung an große CLR\-Objekte  
 Die Auswirkungen auf die Leistung sind beträchtlich, wenn die Datenbindung an ein einzelnes [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekt mit tausenden von Eigenschaften ausgeführt wird.  Sie können diese Auswirkung minimieren, indem Sie das einzelne Objekt in mehrere [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekte mit weniger Eigenschaften aufteilen.  Die Tabelle enthält die Zeiten für Bindung und Rendern bei der Datenbindung an ein einzelnes großes [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekt im Vergleich zur Bindung an mehrere kleinere Objekte.  
  
|**Datenbindung von 1000 TextBlock\-Objekten**|**Bindungszeit \(ms\)**|**Zeit zum Rendern \- inklusive Bindung \(ms\)**|  
|---------------------------------------------------|-----------------------------|------------------------------------------------------|  
|An ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekt mit 1000 Eigenschaften|950|1200|  
|An 1000 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekte mit einer Eigenschaft|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## Bindung an ItemsSource  
 Angenommen, es gibt ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601>\-Objekt mit einer Liste von Angestellten, die Sie in einem <xref:System.Windows.Controls.ListBox> anzeigen möchten.  Um eine Entsprechung zwischen diesen beiden Objekten herzustellen, binden Sie die Angestelltenliste an die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft für das <xref:System.Windows.Controls.ListBox>.  Aber jetzt gibt es einen neuen Mitarbeiter in der Gruppe.  Möglicherweise gehen Sie davon aus, dass es ausreicht, diese neue Person einfach zur Angestelltenliste hinzuzufügen, um die Person in die gebundenen <xref:System.Windows.Controls.ListBox>\-Werte einzufügen, und dass diese Änderung automatisch vom Datenbindungsmodul erkannt wird.  Diese Annahme würde sich als falsch erweisen. In Wirklichkeit wird die Änderung nicht automatisch im <xref:System.Windows.Controls.ListBox> reflektiert.  Der Grund dafür ist, dass das [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], <xref:System.Collections.Generic.List%601>\-Objekt nicht automatisch ein Ereignis für eine geänderte Auflistung auslöst.  Damit das <xref:System.Windows.Controls.ListBox> die Änderungen übernimmt, müssten Sie die Angestelltenliste erneut erstellen und sie der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft des <xref:System.Windows.Controls.ListBox> wieder anfügen.  Die Lösung funktioniert zwar, hat aber enorme Auswirkungen auf die Leistung.  Jedes Mal, wenn Sie einem neuen Objekt die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von <xref:System.Windows.Controls.ListBox> wieder zuordnen, entfernt das <xref:System.Windows.Controls.ListBox> zunächst die bisherigen Elemente und generiert die gesamte Liste neu.  Die Auswirkungen auf die Leistung werden noch größer, wenn das <xref:System.Windows.Controls.ListBox> einer komplexen <xref:System.Windows.DataTemplate> zugeordnet wird.  
  
 Eine sehr effiziente Lösung für dieses Problem ist es, die Angestelltenliste zu einer <xref:System.Collections.ObjectModel.ObservableCollection%601> zu machen.  Ein <xref:System.Collections.ObjectModel.ObservableCollection%601>\-Objekt löst eine Änderungsbenachrichtigung aus, die das Datenbindungsmodul empfangen kann.  Das Ereignis fügt einem <xref:System.Windows.Controls.ItemsControl> ein Element hinzu bzw. entfernt es daraus, ohne dass die gesamte Liste neu generiert werden muss.  
  
 In der unten stehenden Tabelle wird die benötigte Zeit angezeigt, um das <xref:System.Windows.Controls.ListBox> zu aktualisieren \(bei deaktivierter Virtualisierung der Benutzeroberfläche\), wenn ein Element hinzugefügt wird.  Die Zahl in der ersten Zeile gibt die verstrichene Zeit an, wenn das [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-<xref:System.Collections.Generic.List%601>\-Objekt an <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> des <xref:System.Windows.Controls.ListBox>\-Elements gebunden wird.  Die Zahl in der zweiten Zeile gibt die verstrichene Zeit an, wenn eine <xref:System.Collections.ObjectModel.ObservableCollection%601> an die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> des <xref:System.Windows.Controls.ListBox>\-Elements gebunden wird.  Beachten Sie die immense Zeitersparnis, wenn die Datenbindungsstrategie von <xref:System.Collections.ObjectModel.ObservableCollection%601> verwendet wird.  
  
|**Datenbindung von ItemsSource**|**Aktualisierungszeit für 1 Element \(ms\)**|  
|--------------------------------------|--------------------------------------------------|  
|An ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601>\-Objekt|1656|  
|An eine <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## Bindung von IList an ItemsControl statt an IEnumerable  
 Wenn Sie auswählen können, <xref:System.Collections.Generic.IList%601> oder <xref:System.Collections.IEnumerable> an ein <xref:System.Windows.Controls.ItemsControl>\-Objekt zu binden, entscheiden Sie sich für das <xref:System.Collections.Generic.IList%601>\-Objekt.  Wenn Sie <xref:System.Collections.IEnumerable> an <xref:System.Windows.Controls.ItemsControl> binden, wird erzwungen, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein <xref:System.Collections.Generic.IList%601>\-Wrapperobjekt erstellt, was bedeutet, dass der unnötige Verwaltungsaufwand eines zweiten Objekts sich auf die Leistung auswirkt.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## Konvertieren Sie keine CLR\-Objekte in XML nur zur Datenbindung.  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie die Datenbindung an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-Inhalte ausführen. Allerdings ist die Datenbindung an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-Inhalte langsamer als die Datenbindung an [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekte.  Konvertieren Sie keine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objektdaten in XML, wenn es nur zum Zwecke der Datenbindung geschieht.  
  
## Siehe auch  
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Nutzen der Vorteile der Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Projektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF\-Anwendung](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)