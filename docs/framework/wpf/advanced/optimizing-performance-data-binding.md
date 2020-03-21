---
title: 'Optimieren der Leistung: Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 3128f453378f9d74f867b571e30f2be4e8add8a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186756"
---
# <a name="optimizing-performance-data-binding"></a>Optimieren der Leistung: Datenbindung
Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindung bietet für Anwendungen eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können in Form von CLR-Objekten und XML an Daten aus einer Vielzahl von Datenquellen gebunden werden.  
  
 In diesem Thema erhalten Sie Empfehlungen bezüglich der Datenbindung.  

<a name="HowDataBindingReferencesAreResolved"></a>
## <a name="how-data-binding-references-are-resolved"></a>So werden Datenbindungsverweise aufgelöst  
 Vor der Erläuterung von Problemen bei der Leistung der Datenbindung kann es sinnvoll sein, zu erfahren, wie die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindungs-Engine Objektverweise für die Bindung auflöst.  
  
 Die Quelle [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] einer Datenbindung kann ein beliebiges CLR-Objekt sein. Sie können eine Bindung an Eigenschaften, Untereigenschaften oder Indexer eines CLR-Objekts binden. Die Bindungsverweise werden entweder mithilfe der Microsoft <xref:System.ComponentModel.ICustomTypeDescriptor>.NET Framework-Reflektion oder einer aufgelöst. Dies sind drei Methoden zu Auflösung von Objektverweisen für die Bindung.  
  
 In der ersten Methode verwenden Sie die Reflektion. In diesem Fall <xref:System.Reflection.PropertyInfo> wird das Objekt verwendet, um die Attribute der Eigenschaft zu ermitteln und bietet Zugriff auf Eigenschaftenmetadaten. Bei Verwendung <xref:System.ComponentModel.ICustomTypeDescriptor> der Schnittstelle verwendet das Datenbindungsmodul diese Schnittstelle, um auf die Eigenschaftswerte zuzugreifen. Die <xref:System.ComponentModel.ICustomTypeDescriptor> Schnittstelle ist besonders nützlich in Fällen, in denen das Objekt nicht über einen statischen Satz von Eigenschaften verfügt.  
  
 Eigenschaftenänderungsbenachrichtigungen können entweder durch <xref:System.ComponentModel.INotifyPropertyChanged> Implementieren der Schnittstelle oder mithilfe <xref:System.ComponentModel.TypeDescriptor>der Änderungsbenachrichtigungen bereitgestellt werden, die der zugeordnet sind. Die bevorzugte Strategie zum Implementieren von Eigenschaftenänderungsbenachrichtigungen ist jedoch die Verwendung <xref:System.ComponentModel.INotifyPropertyChanged>von .  
  
 Wenn das Quellobjekt ein CLR-Objekt ist und die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Quelleigenschaft eine CLR-Eigenschaft ist, muss <xref:System.ComponentModel.TypeDescriptor>das Datenbindungsmodul <xref:System.ComponentModel.PropertyDescriptor>zuerst die Reflektion für das Quellobjekt verwenden, um die abrufe, und dann eine Abfrage für eine . Diese Folge von Reflektionsvorgängen kann hinsichtlich der Leistung sehr zeitaufwändig sein.  
  
 Die zweite Methode zum Auflösen von Objektverweisen umfasst <xref:System.ComponentModel.INotifyPropertyChanged> ein CLR-Quellobjekt, das die Schnittstelle implementiert, und eine Quelleigenschaft, die eine CLR-Eigenschaft ist. In diesem Fall wendet die Datenbindungs-Engine die Reflektion direkt auf die Quelle an und erhält die erforderliche Eigenschaft. Dies stellt immer noch nicht die optimale Methode dar, aber sie hat weniger Workingsetanforderungen als die erste Methode.  
  
 Die dritte Methode zum Auflösen von Objektverweisen <xref:System.Windows.DependencyObject> umfasst ein Quellobjekt, das eine und eine Quelleigenschaft ist, die eine <xref:System.Windows.DependencyProperty>ist. In diesem Fall muss die Datenbindungs-Engine keine Reflektion verwenden. Stattdessen lösen die Eigenschaften-Engine und die Datenbindungs-Engine gemeinsam und unabhängig den Eigenschaftenverweis auf. Dies stellt die optimale Methode für das Auflösen von Objektverweisen für die Datenbindung dar.  
  
 Die folgende Tabelle vergleicht die <xref:System.Windows.Controls.TextBlock.Text%2A> Geschwindigkeit der <xref:System.Windows.Controls.TextBlock> Datenbindung der Eigenschaft von tausend Elementen mit diesen drei Methoden.  
  
|**Bindung einer Text-Eigenschaft an einen TextBlock**|**Bindungszeit (in ms)**|**Renderingzeit, einschließlich Bindung (in ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|Zu einer Eigenschaft eines CLR-Objekts|115|314|  
|An eine Eigenschaft eines CLR-Objekts, das<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|Zu <xref:System.Windows.DependencyProperty> einem <xref:System.Windows.DependencyObject>von .|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>
## <a name="binding-to-large-clr-objects"></a>Bindung an große CLR-Objekte  
 Wenn Sie Daten an ein einzelnes CLR-Objekt mit Tausenden von Eigenschaften binden, wirkt sich dies erheblich auf die Leistung aus. Sie können diese Auswirkungen minimieren, indem Sie das einzelne Objekt in mehrere CLR-Objekte mit weniger Eigenschaften unterteilen. Die Tabelle zeigt die Bindungs- und Renderzeiten für die Datenbindung an ein einzelnes großes CLR-Objekt im Vergleich zu mehreren kleineren Objekten.  
  
|**Datenbindung an 1000 TextBlock-Objekte**|**Bindungszeit (in ms)**|**Renderingzeit, einschließlich Bindung (in ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|Zu einem CLR-Objekt mit 1000 Eigenschaften|950|1200|  
|An 1000 CLR-Objekte mit einer Eigenschaft|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>
## <a name="binding-to-an-itemssource"></a>Bindung an eine ItemsSource  
 Stellen Sie sich ein Szenario <xref:System.Collections.Generic.List%601> vor, in dem Sie über ein CLR-Objekt verfügen, das eine Liste der Mitarbeiter enthält, die Sie in einem <xref:System.Windows.Controls.ListBox>anzeigen möchten. Um eine Entsprechung zwischen diesen beiden Objekten zu <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> erstellen, <xref:System.Windows.Controls.ListBox>binden Sie Ihre Mitarbeiterliste an die Eigenschaft der . Gehen Sie nun davon aus, dass ein neuer Angestellter dazu kommt. Sie könnten denken, dass Sie diese Person <xref:System.Windows.Controls.ListBox> einfach zu Ihrer Mitarbeiterliste hinzufügen und erwarten würden, dass diese Änderung automatisch vom Datenbindungsmodul erkannt wird, um diese neue Person in Ihre gebundenen Werte einzufügen. Diese Annahme würde sich als falsch erweisen; in Wirklichkeit wird die Änderung nicht <xref:System.Windows.Controls.ListBox> automatisch in der widergespiegelt. Dies liegt daran, dass das CLR-Objekt <xref:System.Collections.Generic.List%601> nicht automatisch ein Änderungsereignis für auflistungen auslöst. Um die <xref:System.Windows.Controls.ListBox> Änderungen zu übernehmen, müssen Sie Ihre Mitarbeiterliste neu erstellen und sie <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> erneut an <xref:System.Windows.Controls.ListBox>die Eigenschaft des anhängen. Obwohl diese Lösung funktioniert, beeinträchtigt sie die Leistung deutlich. Jedes Mal, wenn <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox> Sie das von <xref:System.Windows.Controls.ListBox> einem neuen Objekt neu zuweisen, wirft der Erste seine vorherigen Elemente weg und regeneriert seine gesamte Liste. Die Auswirkungen auf die Leistung <xref:System.Windows.Controls.ListBox> werden vergrößert, wenn Ihre Zuordnungen zu einem komplexen <xref:System.Windows.DataTemplate>.  
  
 Eine sehr effiziente Lösung für dieses Problem <xref:System.Collections.ObjectModel.ObservableCollection%601>besteht darin, Ihre Mitarbeiterliste zu einer zu machen. Ein <xref:System.Collections.ObjectModel.ObservableCollection%601> Objekt löst eine Änderungsbenachrichtigung aus, die das Datenbindungsmodul empfangen kann. Das Ereignis fügt ein Element <xref:System.Windows.Controls.ItemsControl> hinzu oder entfernt es aus einem, ohne die gesamte Liste neu generieren zu müssen.  
  
 Die folgende Tabelle zeigt die Zeit, die zum Aktualisieren der (wenn die <xref:System.Windows.Controls.ListBox> UI-Virtualisierung deaktiviert ist) benötigt wird, wenn ein Element hinzugefügt wird. Die Zahl in der ersten Zeile stellt die <xref:System.Collections.Generic.List%601> verstrichene <xref:System.Windows.Controls.ListBox> Zeit <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>dar, zu der das CLR-Objekt an die des Elements gebunden ist. Die Zahl in der zweiten Zeile stellt <xref:System.Collections.ObjectModel.ObservableCollection%601> die verstrichene Zeit dar, zu der ein an das <xref:System.Windows.Controls.ListBox> Element gebunden <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>ist. Beachten Sie die erheblichen <xref:System.Collections.ObjectModel.ObservableCollection%601> Zeiteinsparungen mit der Datenbindungsstrategie.  
  
|**Datenbindung der ItemsSource**|**Zeit für das Aktualisieren eines Elements (in ms)**|  
|--------------------------------------|---------------------------------------|  
|Zu einem <xref:System.Collections.Generic.List%601> CLR-Objekt|1656|  
|Zu einem<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Bindung von IList an ItemsControl und nicht an IEnumerable  
 Wenn Sie zwischen dem <xref:System.Collections.Generic.IList%601> Binden <xref:System.Collections.IEnumerable> eines <xref:System.Windows.Controls.ItemsControl> oder eines <xref:System.Collections.Generic.IList%601> an ein Objekt stehen, wählen Sie das Objekt aus. Bindung <xref:System.Collections.IEnumerable> an <xref:System.Windows.Controls.ItemsControl> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einen Kräfte zum <xref:System.Collections.Generic.IList%601> Erstellen eines Wrapperobjekts, was bedeutet, dass Ihre Leistung durch den unnötigen Overhead eines zweiten Objekts beeinträchtigt wird.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Konvertieren Sie CLR-Objekte nicht nur für die Datenbindung in XML  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ermöglicht es Ihnen, Daten an XML-Inhalte zu binden; Die Datenbindung an XML-Inhalte ist jedoch langsamer als die Datenbindung an CLR-Objekte. Konvertieren Sie CLR-Objektdaten nicht in XML, wenn der einzige Zweck die Datenbindung ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung](walkthrough-caching-application-data-in-a-wpf-application.md)
