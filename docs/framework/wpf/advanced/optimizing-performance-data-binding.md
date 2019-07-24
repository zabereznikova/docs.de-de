---
title: 'Optimieren der Leistung: Datenbindung'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 25c0906e9f23948476732b10b2c5fb10fe4eb55f
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401449"
---
# <a name="optimizing-performance-data-binding"></a>Optimieren der Leistung: Datenbindung
Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindung bietet für Anwendungen eine einfache und konsistente Möglichkeit, Daten darzustellen und mit ihnen zu interagieren. Elemente können an Daten aus einer Vielzahl von Datenquellen in Form von CLR-Objekten und [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]gebunden werden.  
  
 In diesem Thema erhalten Sie Empfehlungen bezüglich der Datenbindung.  

<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>So werden Datenbindungsverweise aufgelöst  
 Vor der Erläuterung von Problemen bei der Leistung der Datenbindung kann es sinnvoll sein, zu erfahren, wie die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Datenbindungs-Engine Objektverweise für die Bindung auflöst.  
  
 Bei der Quelle einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Datenbindung kann es sich um ein beliebiges CLR-Objekt handeln. Sie können an Eigenschaften, unter Eigenschaften oder Indexer eines CLR-Objekts binden. Die Bindungs Verweise werden entweder mithilfe Microsoft .NET Framework-Reflektion oder <xref:System.ComponentModel.ICustomTypeDescriptor>mithilfe von aufgelöst. Dies sind drei Methoden zu Auflösung von Objektverweisen für die Bindung.  
  
 In der ersten Methode verwenden Sie die Reflektion. In diesem Fall wird das <xref:System.Reflection.PropertyInfo> -Objekt verwendet, um die Attribute der Eigenschaft zu ermitteln und den Zugriff auf die Metadaten der Eigenschaft bereitzustellen. Bei Verwendung der <xref:System.ComponentModel.ICustomTypeDescriptor> -Schnittstelle verwendet die Daten Bindungs-Engine diese Schnittstelle, um auf die Eigenschaftswerte zuzugreifen. Die <xref:System.ComponentModel.ICustomTypeDescriptor> -Schnittstelle ist besonders nützlich, wenn das Objekt nicht über einen statischen Satz von Eigenschaften verfügt.  
  
 Eigenschafts Änderungs Benachrichtigungen können entweder durch Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle oder durch Verwendung der der zugeordneten <xref:System.ComponentModel.TypeDescriptor>Änderungs Benachrichtigungen bereitgestellt werden. Die bevorzugte Strategie zum Implementieren von Benachrichtigungen über Eigenschafts Änderungen ist jedoch <xref:System.ComponentModel.INotifyPropertyChanged>die Verwendung von.  
  
 Wenn das Quell Objekt ein CLR-Objekt ist und die Source-Eigenschaft eine CLR-Eigenschaft [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist, muss die Daten Bindungs-Engine zuerst die Reflektion für das Quell <xref:System.ComponentModel.TypeDescriptor>Objekt verwenden, um den zu <xref:System.ComponentModel.PropertyDescriptor>erhalten, und dann eine Abfrage für eine durchführen. Diese Folge von Reflektionsvorgängen kann hinsichtlich der Leistung sehr zeitaufwändig sein.  
  
 Die zweite Methode zum Auflösen von Objekt verweisen umfasst ein CLR-Quell Objekt, <xref:System.ComponentModel.INotifyPropertyChanged> das die-Schnittstelle implementiert, und eine Quell Eigenschaft, die eine CLR-Eigenschaft ist. In diesem Fall wendet die Datenbindungs-Engine die Reflektion direkt auf die Quelle an und erhält die erforderliche Eigenschaft. Dies stellt immer noch nicht die optimale Methode dar, aber sie hat weniger Workingsetanforderungen als die erste Methode.  
  
 Die dritte Methode zum Auflösen von Objekt verweisen umfasst ein Quell Objekt, das <xref:System.Windows.DependencyObject> eine ist, und eine Quell Eigenschaft <xref:System.Windows.DependencyProperty>, die eine ist. In diesem Fall muss die Datenbindungs-Engine keine Reflektion verwenden. Stattdessen lösen die Eigenschaften-Engine und die Datenbindungs-Engine gemeinsam und unabhängig den Eigenschaftenverweis auf. Dies stellt die optimale Methode für das Auflösen von Objektverweisen für die Datenbindung dar.  
  
 In der folgenden Tabelle wird die Geschwindigkeit der Datenbindung <xref:System.Windows.Controls.TextBlock.Text%2A> für die- <xref:System.Windows.Controls.TextBlock> Eigenschaft der 1000-Elemente mithilfe dieser drei Methoden verglichen.  
  
|**Bindung einer Text-Eigenschaft an einen TextBlock**|**Bindungszeit (in ms)**|**Renderingzeit, einschließlich Bindung (in ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|An eine Eigenschaft eines CLR-Objekts|115|314|  
|An eine Eigenschaft eines CLR-Objekts, das implementiert<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|Zu einem <xref:System.Windows.DependencyProperty> <xref:System.Windows.DependencyObject>eines.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>Bindung an große CLR-Objekte  
 Wenn Sie Daten an ein einzelnes CLR-Objekt mit Tausenden von Eigenschaften binden, wirkt sich dies erheblich auf die Leistung aus. Sie können diese Auswirkung minimieren, indem Sie das einzelne Objekt in mehrere CLR-Objekte mit weniger Eigenschaften aufteilen. In der Tabelle werden die Bindungs-und Renderingzeiten für die Datenbindung an ein einzelnes großes CLR-Objekt im Vergleich zu mehreren kleineren Objekten angezeigt.  
  
|**Datenbindung an 1000 TextBlock-Objekte**|**Bindungszeit (in ms)**|**Renderingzeit, einschließlich Bindung (in ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|Zu einem CLR-Objekt mit 1000-Eigenschaften|950|1200|  
|Zu 1000 CLR-Objekten mit einer Eigenschaft|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>Bindung an eine ItemsSource  
 Stellen Sie sich ein Szenario vor, in dem Sie <xref:System.Collections.Generic.List%601> über ein CLR-Objekt verfügen, das eine Liste von Mitarbeitern enthält <xref:System.Windows.Controls.ListBox>, die Sie in einem anzeigen möchten. Um eine Entsprechung zwischen diesen beiden Objekten zu erstellen, binden Sie die Employee-Liste <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> an die- <xref:System.Windows.Controls.ListBox>Eigenschaft des-Objekts. Gehen Sie nun davon aus, dass ein neuer Angestellter dazu kommt. Wenn Sie diese neue Person in Ihre gebundenen <xref:System.Windows.Controls.ListBox> Werte einfügen möchten, können Sie diese Person einfach Ihrer Mitarbeiterliste hinzufügen und erwarten, dass diese Änderung automatisch von der Datenbindungs-Engine erkannt wird. Diese Annahme würde false belegen. in Wirklichkeit wird die Änderung nicht <xref:System.Windows.Controls.ListBox> automatisch in wiedergegeben. Dies liegt daran, dass das <xref:System.Collections.Generic.List%601> CLR-Objekt nicht automatisch ein Auflistungs geändertes Ereignis aufhebt. Um die <xref:System.Windows.Controls.ListBox> Änderungen zu übernehmen, müssen Sie die Liste der Mitarbeiter neu erstellen und an die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft des <xref:System.Windows.Controls.ListBox>anfügen. Obwohl diese Lösung funktioniert, beeinträchtigt sie die Leistung deutlich. Jedes Mal, wenn Sie den <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von <xref:System.Windows.Controls.ListBox> einem neuen-Objekt zuweisen, <xref:System.Windows.Controls.ListBox> löst der erste seine vorherigen Elemente aus und generiert seine gesamte Liste erneut. Die Auswirkungen auf die Leistung werden vergrößert, <xref:System.Windows.Controls.ListBox> Wenn Sie einem komplexen <xref:System.Windows.DataTemplate>zuordnen.  
  
 Eine äußerst effiziente Lösung für dieses Problem besteht darin, die Mitarbeiterliste <xref:System.Collections.ObjectModel.ObservableCollection%601>zu zu machen. Ein <xref:System.Collections.ObjectModel.ObservableCollection%601> -Objekt löst eine Änderungs Benachrichtigung aus, die von der Datenbindungs-Engine empfangen werden kann. Das Ereignis fügt ein Element <xref:System.Windows.Controls.ItemsControl> hinzu oder entfernt dieses, ohne die gesamte Liste neu generieren zu müssen.  
  
 Die folgende Tabelle zeigt die Zeit, die benötigt wird, <xref:System.Windows.Controls.ListBox> um das zu aktualisieren (bei deaktivierter benutzeroberflächenvirtualisierung), wenn ein Element hinzugefügt wird. Die Zahl in der ersten Zeile stellt die verstrichene Zeit dar, <xref:System.Collections.Generic.List%601> zu der das CLR- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>Objekt an <xref:System.Windows.Controls.ListBox> den Element gebunden ist. Die Zahl in der zweiten Zeile stellt die verstrichene Zeit <xref:System.Collections.ObjectModel.ObservableCollection%601> dar, die an <xref:System.Windows.Controls.ListBox> den des <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>Elements gebunden ist. Beachten Sie die erheblichen Zeiteinsparungen mithilfe <xref:System.Collections.ObjectModel.ObservableCollection%601> der Strategie für die Datenbindung.  
  
|**Datenbindung der ItemsSource**|**Zeit für das Aktualisieren eines Elements (in ms)**|  
|--------------------------------------|---------------------------------------|  
|Zu einem CLR <xref:System.Collections.Generic.List%601> -Objekt|1656|  
|Zu einem<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Bindung von IList an ItemsControl und nicht an IEnumerable  
 Wählen Sie das <xref:System.Collections.Generic.IList%601> <xref:System.Windows.Controls.ItemsControl> <xref:System.Collections.IEnumerable> Objektaus,wennSieeineMöglichkeithaben,eineodereineaneinObjektzubinden.<xref:System.Collections.Generic.IList%601> Binden <xref:System.Collections.IEnumerable> an einen <xref:System.Windows.Controls.ItemsControl> erzwingt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Erstellung eines <xref:System.Collections.Generic.IList%601> Wrapper Objekts. Dies bedeutet, dass die Leistung durch den unnötigen Aufwand eines zweiten Objekts beeinträchtigt wird.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Konvertieren Sie CLR-Objekte nicht nur für die Datenbindung in XML  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ermöglicht es Ihnen, Daten an [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] den Inhalt zu binden, aber die [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Datenbindung an den Inhalt ist langsamer als die Datenbindung an CLR-Objekte. Konvertieren Sie CLR-Objektdaten nicht in XML, wenn der einzige Zweck für die Datenbindung besteht.  
  
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
