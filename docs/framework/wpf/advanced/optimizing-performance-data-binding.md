---
title: 'Optimieren der Leistung: Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: da870e9459ee2cbe0384c146546c378fb7247f03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="optimizing-performance-data-binding"></a>Optimieren der Leistung: Datenbindung
Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindung bietet für Anwendungen eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können an Daten aus einer Vielzahl von Datenquellen in Form von [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekten und [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] gebunden werden.  
  
 In diesem Thema erhalten Sie Empfehlungen bezüglich der Datenbindung.  
  

  
<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>So werden Datenbindungsverweise aufgelöst  
 Vor der Erläuterung von Problemen bei der Leistung der Datenbindung kann es sinnvoll sein, zu erfahren, wie das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindungsmodul Objektverweise für die Bindung auflöst.  
  
 Die Quelle eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindung kann jedes [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekt sein. Sie können an Eigenschaften, Untereigenschaften oder Indexer eines [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekts binden. Die Bindungsverweise werden aufgelöst, mithilfe einer Microsoft .NET Framework-Reflektions- oder eine <xref:System.ComponentModel.ICustomTypeDescriptor>. Dies sind drei Methoden zu Auflösung von Objektverweisen für die Bindung.  
  
 In der ersten Methode verwenden Sie die Reflektion. In diesem Fall die <xref:System.Reflection.PropertyInfo> Objekt wird verwendet, um die Attribute der Eigenschaft zu ermitteln und ermöglicht den Zugriff auf die Eigenschaftenmetadaten. Bei Verwendung der <xref:System.ComponentModel.ICustomTypeDescriptor> -Schnittstelle, das Datenbindungsmodul mithilfe dieser Schnittstelle auf die Eigenschaftswerte zugreifen. Die <xref:System.ComponentModel.ICustomTypeDescriptor> Schnittstelle ist besonders in Fällen, in dem das Objekt keinen statischen Satz von Eigenschaften.  
  
 Änderungsbenachrichtigungen für die Eigenschaft können angegeben werden, entweder durch die Implementierung der <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle oder die zugeordneten Benachrichtigungen durch die Verwendung der <xref:System.ComponentModel.TypeDescriptor>. Allerdings ist die bevorzugte Strategie für die Implementierung von änderungsbenachrichtigungen für die Eigenschaft verwenden <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Wenn das Quellobjekt ist eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Objekt und die Quelleigenschaft ist eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Eigenschaft, der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Datenbindungsmodul muss zuerst auf das Quellobjekt, das mithilfe von Reflektion abgerufen der <xref:System.ComponentModel.TypeDescriptor>, und Fragen Sie für eine <xref:System.ComponentModel.PropertyDescriptor>. Diese Folge von Reflektionsvorgängen kann hinsichtlich der Leistung sehr zeitaufwändig sein.  
  
 Die zweite Methode zum Auflösen von Objektverweisen umfasst eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Quellobjekt, die implementiert die <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle und eine Source-Eigenschaft, die eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Eigenschaft. In diesem Fall wendet das Datenbindungsmodul die Reflektion direkt auf die Quelle an und erhält die erforderliche Eigenschaft. Dies stellt immer noch nicht die optimale Methode dar, aber sie hat weniger Workingsetanforderungen als die erste Methode.  
  
 Die dritte Methode zum Auflösen von Objektverweisen verwendet ein Quellobjekt, das eine <xref:System.Windows.DependencyObject> und eine Source-Eigenschaft, die eine <xref:System.Windows.DependencyProperty>. In diesem Fall muss das Datenbindungsmodul keine Reflektion verwenden. Stattdessen lösen das Eigenschaftenmodul und das Datenbindungsmodul gemeinsam und unabhängig den Eigenschaftenverweis auf. Dies stellt die optimale Methode für das Auflösen von Objektverweisen für die Datenbindung dar.  
  
 Die folgende Tabelle vergleicht die Geschwindigkeit der Datenbindung der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft Tausendstel <xref:System.Windows.Controls.TextBlock> Elemente, die mit diesen drei Methoden.  
  
|**Bindung einer Text-Eigenschaft an einen TextBlock**|**Bindungszeit (in ms)**|**Renderingzeit, einschließlich Bindung (in ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|An die Eigenschaft eines [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekts|115|314|  
|Um eine Eigenschaft einer [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Objekt implementiert <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|Um eine <xref:System.Windows.DependencyProperty> von einem <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>Bindung an große CLR-Objekte  
 Wenn Sie Daten an ein einzelnes [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekt mit tausend Eigenschaften binden, beeinträchtigt dies die Leistung deutlich. Sie können die Beeinträchtigung verringern, indem Sie das einzelne Objekt in mehrere [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekte aufteilen, die weniger Eigenschaften haben. In der unten stehenden Tabelle werden die Bindungs- und Renderingzeiten für die Datenbindung an ein einzelnes großes [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekt und an mehrere kleinere Objekte dargestellt.  
  
|**Datenbindung an 1000 TextBlock-Objekte**|**Bindungszeit (in ms)**|**Renderingzeit, einschließlich Bindung (in ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|An ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekt mit 1000 Eigenschaften|950|1200|  
|An 1000 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekte mit einer Eigenschaft|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>Bindung an eine ItemsSource  
 Betrachten Sie ein Szenario, in dem Sie besitzen, eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> Objekt, das eine Liste der Mitarbeiter, die enthält in angezeigt werden soll eine <xref:System.Windows.Controls.ListBox>. Um eine Entsprechung zwischen diesen beiden Objekten zu erstellen, binden Sie Ihre Mitarbeiterliste, um die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft von der <xref:System.Windows.Controls.ListBox>. Gehen Sie nun davon aus, dass ein neuer Angestellter dazu kommt. Sie könnten meinen, dass zum Einfügen von neuen Person in die gebundenen <xref:System.Windows.Controls.ListBox> Werte Sie einfach diese Person hinzugefügt, die zur Mitarbeiterliste und erwarten, dass diese Änderung in das Datenbindungsmodul automatisch erkannt werden. Diese Annahme würde als "false" erweisen. in Wirklichkeit wird die Änderung nicht in übernommen werden die <xref:System.Windows.Controls.ListBox> automatisch. Grund hierfür ist die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> Objekt löst nicht automatisch ein Ereignis für die Sammlung wurde geändert. Zum Abrufen der <xref:System.Windows.Controls.ListBox> um die Änderungen zu übernehmen, müssten Sie neu erstellen die Liste der Mitarbeiter, und fügen Sie ihn erneut der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox>. Obwohl diese Lösung funktioniert, beeinträchtigt sie die Leistung deutlich. Jedes Mal, die Sie neu zuweisen der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von <xref:System.Windows.Controls.ListBox> auf ein neues Objekt, das <xref:System.Windows.Controls.ListBox> zunächst ihre bisherigen Elemente und generiert die gesamte Liste. Auswirkungen auf die Leistung wird vergrößert, wenn Ihre <xref:System.Windows.Controls.ListBox> ordnet ein komplexer <xref:System.Windows.DataTemplate>.  
  
 Eine sehr effiziente Lösung für dieses Problem besteht darin, Ihre Mitarbeiterliste stellen eine <xref:System.Collections.ObjectModel.ObservableCollection%601>. Ein <xref:System.Collections.ObjectModel.ObservableCollection%601> -Objekt löst eine Change-Benachrichtigung, die das Datenbindungsmodul empfangen kann. Das Ereignis hinzugefügt oder entfernt ein Element aus einer <xref:System.Windows.Controls.ItemsControl> ohne die Notwendigkeit, die gesamte Liste erneut zu generieren.  
  
 Die folgende Tabelle zeigt die Zeit, die zum Aktualisieren der <xref:System.Windows.Controls.ListBox> (mit die Virtualisierung der Benutzeroberfläche deaktiviert) Wenn ein Element hinzugefügt wird. Die Anzahl in der ersten Zeile gibt die verstrichene Zeit bei der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> -Objekt gebunden wird <xref:System.Windows.Controls.ListBox> des Elements <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Die Anzahl in der zweiten Zeile gibt die verstrichene Zeit beim ein <xref:System.Collections.ObjectModel.ObservableCollection%601> gebunden ist, um die <xref:System.Windows.Controls.ListBox> des Elements <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Hinweis: bei der Verwendung zu sehr viel Zeit sparen die <xref:System.Collections.ObjectModel.ObservableCollection%601> Strategie für die Bindung.  
  
|**Datenbindung der ItemsSource**|**Zeit für das Aktualisieren eines Elements (in ms)**|  
|--------------------------------------|---------------------------------------|  
|Um eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> Objekt|1656|  
|Um ein <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Bindung von IList an ItemsControl und nicht an IEnumerable  
 Sie haben die Wahl zwischen der Bindung einer <xref:System.Collections.Generic.IList%601> oder ein <xref:System.Collections.IEnumerable> auf eine <xref:System.Windows.Controls.ItemsControl> Objekt, wählen Sie die <xref:System.Collections.Generic.IList%601> Objekt. Binden von <xref:System.Collections.IEnumerable> auf eine <xref:System.Windows.Controls.ItemsControl> erzwingt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einen Wrapper erstellen <xref:System.Collections.Generic.IList%601> -Objekt, das bedeutet, dass die Leistung wird beeinträchtigt, durch den Aufwand der ein zweites Objekt.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Konvertieren Sie CLR-Objekte nicht nur für die Datenbindung in XML  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie eine Datenbindung an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Inhalt durchführen; allerdings ist die Datenbindung an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Inhalt langsamer als an [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekte. Konvertieren Sie [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objektdaten nicht nur für die Datenbindung in XML.  
  
## <a name="see-also"></a>Siehe auch  
 [Optimieren der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Vorteile der Hardware nutzen](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Objektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
