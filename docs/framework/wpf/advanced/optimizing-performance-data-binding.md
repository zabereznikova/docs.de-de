---
title: 'Optimieren der Leistung: Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: dfc58036bc39879009b31d29dc41247a914bcd59
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352021"
---
# <a name="optimizing-performance-data-binding"></a>Optimieren der Leistung: Datenbindung
Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindung bietet für Anwendungen eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können an Daten aus einer Vielzahl von Datenquellen in Form von [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekten und [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] gebunden werden.  
  
 In diesem Thema erhalten Sie Empfehlungen bezüglich der Datenbindung.  
  

  
<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>So werden Datenbindungsverweise aufgelöst  
 Vor der Erläuterung von Problemen bei der Leistung der Datenbindung kann es sinnvoll sein, zu erfahren, wie die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindungs-Engine Objektverweise für die Bindung auflöst.  
  
 Die Quelle eine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindung kann jedes [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekt sein. Sie können an Eigenschaften, Untereigenschaften oder Indexer eines [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekts binden. Mithilfe der beiden Microsoft .NET Framework-Reflektion Bindungsverweise aufgelöst werden oder ein <xref:System.ComponentModel.ICustomTypeDescriptor>. Dies sind drei Methoden zu Auflösung von Objektverweisen für die Bindung.  
  
 In der ersten Methode verwenden Sie die Reflektion. In diesem Fall die <xref:System.Reflection.PropertyInfo> Objekt wird verwendet, um die Attribute der Eigenschaft ermitteln und ermöglicht den Zugriff auf Metadaten. Bei Verwendung der <xref:System.ComponentModel.ICustomTypeDescriptor> -Schnittstelle, die Datenbindungs-Engine verwendet diese Schnittstelle für die Eigenschaftswerte zuzugreifen. Die <xref:System.ComponentModel.ICustomTypeDescriptor> Schnittstelle ist besonders hilfreich in Fällen, in dem das Objekt keinen statischen Satz von Eigenschaften.  
  
 Benachrichtigungen über eigenschaftsänderungen können angegeben werden, entweder durch die Implementierung der <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle oder die zugeordnete änderungsbenachrichtigungen mit der <xref:System.ComponentModel.TypeDescriptor>. Die geeignetere Strategie zum Implementieren von Benachrichtigungen über eigenschaftsänderungen jedoch ist die Verwendung <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Wenn das Quellobjekt ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Objekt und die Quelleigenschaft ist ein [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Eigenschaft, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Datenbindungs-Engine muss zuerst für das Quellobjekt mithilfe der Reflektion erhalten die <xref:System.ComponentModel.TypeDescriptor>, und dann Abfragen für eine <xref:System.ComponentModel.PropertyDescriptor>. Diese Folge von Reflektionsvorgängen kann hinsichtlich der Leistung sehr zeitaufwändig sein.  
  
 Zum Auflösen von Objektverweisen der zweiten Methode werden eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Quellobjekt, das implementiert, die <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle und eine Quelleigenschaft, die eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Eigenschaft. In diesem Fall wendet die Datenbindungs-Engine die Reflektion direkt auf die Quelle an und erhält die erforderliche Eigenschaft. Dies stellt immer noch nicht die optimale Methode dar, aber sie hat weniger Workingsetanforderungen als die erste Methode.  
  
 Die dritte Methode zum Auflösen von Objektverweisen involviert ein Quellobjekt, das eine <xref:System.Windows.DependencyObject> und eine Quelleigenschaft, die eine <xref:System.Windows.DependencyProperty>. In diesem Fall muss die Datenbindungs-Engine keine Reflektion verwenden. Stattdessen lösen die Eigenschaften-Engine und die Datenbindungs-Engine gemeinsam und unabhängig den Eigenschaftenverweis auf. Dies stellt die optimale Methode für das Auflösen von Objektverweisen für die Datenbindung dar.  
  
 Die folgende Tabelle vergleicht die Geschwindigkeit der Datenbindung die <xref:System.Windows.Controls.TextBlock.Text%2A> -Eigenschaft von Tausend <xref:System.Windows.Controls.TextBlock> Elemente, die diese drei Methoden verwenden.  
  
|**Bindung einer Text-Eigenschaft an einen TextBlock**|**Bindungszeit (in ms)**|**Renderingzeit, einschließlich Bindung (in ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|An die Eigenschaft eines [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekts|115|314|  
|An eine Eigenschaft einer [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Objekts, das implementiert <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
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
 Betrachten Sie ein Szenario, in dem Sie besitzen, eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> -Objekt, das eine Liste der Mitarbeiter, die enthält in angezeigt werden soll eine <xref:System.Windows.Controls.ListBox>. Um eine Entsprechung zwischen diesen beiden Objekten zu erstellen, binden Sie Ihre Angestelltenliste an die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox>. Gehen Sie nun davon aus, dass ein neuer Angestellter dazu kommt. Sie könnten meinen, dass um diese neue Person in die gebundenen einfügen <xref:System.Windows.Controls.ListBox> Werte, Sie würden einfach diese Person Angestelltenliste hinzufügen und erwarten, dass diese Änderung automatisch von der Datenbindungs-Engine erkannt werden. Diese Annahme würde als falsch herausstellen; in Wirklichkeit, der keine Änderung der <xref:System.Windows.Controls.ListBox> automatisch. Grund hierfür ist die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> Objekt wird nicht automatisch ein CollectionChanged-Ereignis auslöst. Zum Abrufen der <xref:System.Windows.Controls.ListBox> um die Änderungen zu übernehmen, müssen neu von der Liste mit Mitarbeitern, und fügen Sie es erneut die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox>. Obwohl diese Lösung funktioniert, beeinträchtigt sie die Leistung deutlich. Jedes Mal, die Sie neu zuweisen der <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von <xref:System.Windows.Controls.ListBox> auf ein neues Objekt, das <xref:System.Windows.Controls.ListBox> zunächst die bisherigen Elemente und generiert seine komplette Liste. Die leistungsbeeinträchtigung wird noch vergrößert, wenn Ihre <xref:System.Windows.Controls.ListBox> ordnet einem komplexen <xref:System.Windows.DataTemplate>.  
  
 Eine sehr effiziente Lösung für dieses Problem ist, stellen Ihre Angestelltenliste ein <xref:System.Collections.ObjectModel.ObservableCollection%601>. Ein <xref:System.Collections.ObjectModel.ObservableCollection%601> -Objekt löst eine änderungsbenachrichtigung aus, die die Datenbindungs-Engine empfangen kann. Das Ereignis hinzugefügt oder entfernt ein Element aus einer <xref:System.Windows.Controls.ItemsControl> ohne die gesamte Liste erneut generieren.  
  
 Die folgende Tabelle zeigt die Zeit, die zum Aktualisieren der <xref:System.Windows.Controls.ListBox> (mit UI-Virtualisierung deaktiviert.) Wenn ein Element hinzugefügt wird. Die Anzahl in der ersten Zeile gibt die verstrichene Zeit bei der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> -Objekt gebunden ist <xref:System.Windows.Controls.ListBox> des Elements <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Die Anzahl in der zweiten Zeile darstellt, die verstrichene Zeit beim ein <xref:System.Collections.ObjectModel.ObservableCollection%601> gebunden ist die <xref:System.Windows.Controls.ListBox> des Elements <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Beachten Sie die erhebliche einsparungen mithilfe der <xref:System.Collections.ObjectModel.ObservableCollection%601> Strategie für die Bindung von Daten.  
  
|**Datenbindung der ItemsSource**|**Zeit für das Aktualisieren eines Elements (in ms)**|  
|--------------------------------------|---------------------------------------|  
|Um eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> Objekt|1656|  
|Um eine <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Bindung von IList an ItemsControl und nicht an IEnumerable  
 Wenn Sie die Wahl zwischen der Bindung haben ein <xref:System.Collections.Generic.IList%601> oder ein <xref:System.Collections.IEnumerable> zu ein <xref:System.Windows.Controls.ItemsControl> Objekt, wählen Sie die <xref:System.Collections.Generic.IList%601> Objekt. Binden von <xref:System.Collections.IEnumerable> auf eine <xref:System.Windows.Controls.ItemsControl> erzwingt, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Erstellen eines Wrappers <xref:System.Collections.Generic.IList%601> -Objekt, das bedeutet, dass die Leistung wird durch den unnötigen Mehraufwand eines zweiten Objekts beeinträchtigt.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Konvertieren Sie CLR-Objekte nicht nur für die Datenbindung in XML  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie eine Datenbindung an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Inhalt durchführen; allerdings ist die Datenbindung an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Inhalt langsamer als an [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekte. Konvertieren Sie [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objektdaten nicht nur für die Datenbindung in XML.  
  
## <a name="see-also"></a>Siehe auch
- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung](walkthrough-caching-application-data-in-a-wpf-application.md)
