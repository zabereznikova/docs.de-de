---
title: "&#220;bersicht &#252;ber Bindungsquellen | Microsoft Docs"
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
  - "Binden von Daten, Bindungsquellen"
  - "Bindungsquellen"
  - "Datenbindung, Bindungsquelle"
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# &#220;bersicht &#252;ber Bindungsquellen
Bei der Datenbindung verweist das [Bindungsquellenobjekt](GTMT) auf das Objekt, von dem Sie Daten abrufen.  In diesem Thema werden die Objekttypen vorgestellt, die als Bindungsquelle verwendet werden können.  
  
   
  
<a name="binding_sources"></a>   
## Typen von Bindungsquellen  
 Bei der Datenbindung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden die folgenden Typen von [Bindungsquelle](GTMT) unterstützt:  
  
|Bindungsquelle|Beschreibung|  
|--------------------|------------------|  
|[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Objekte|Sie können eine Bindung an die öffentlichen Eigenschaften, Untereigenschaften und Indexer aller [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Objekte herstellen.  Das Bindungsmodul verwendet die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Reflektion, um die Werte der Eigenschaften abzurufen.  Darüber hinaus kann das Bindungsmodul auch bei Objekten, die <xref:System.ComponentModel.ICustomTypeDescriptor> implementieren oder über einen registrierten <xref:System.ComponentModel.TypeDescriptionProvider> verfügen, verwendet werden.<br /><br /> Weitere Informationen zum Implementieren einer Klasse, die als Bindungsquelle dienen kann, finden Sie weiter unten in diesem Thema unter [Implementieren einer Klasse als Bindungsquelle](#classes).|  
|Dynamische Objekte|Sie können eine Bindung an verfügbare Eigenschaften und Indexer eines Objekts herstellen, das die <xref:System.Dynamic.IDynamicMetaObjectProvider>\-Schnittstelle implementiert.  Wenn Sie auf den Member im Code zugreifen können, kann daran gebunden werden.  Wenn Sie z. B. mithilfe eines dynamischen Objekts auf einen Member im Code über `someObjet.AProperty` zugreifen können, können Sie durch Festlegen des Bindungspfads auf `AProperty` eine Bindung herstellen.|  
|[!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)]\-Objekte|Sie können eine Bindung an [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)]\-Objekte wie <xref:System.Data.DataTable> herstellen. [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)] <xref:System.Data.DataView> implementiert die <xref:System.ComponentModel.IBindingList>\-Schnittstelle, die Änderungsbenachrichtigungen bereitstellt, auf die das Bindungsmodul lauscht.|  
|[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-Objekte|Sie können eine Bindung an <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlDocument> oder <xref:System.Xml.XmlElement> herstellen und für diese Objekte auch `XPath`\-Abfragen ausführen.  Auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten, bei denen es sich um die [Bindungsquelle](GTMT) im Markup handelt, kann auf einfache Weise mit einem <xref:System.Windows.Data.XmlDataProvider>\-Objekt zugegriffen werden.  Weitere Informationen finden Sie unter [Binden an XML\-Daten mithilfe von XMLDataProvider und XPath\-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).<br /><br /> Sie können auch eine Bindung an <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> oder an Abfrageergebnisse auf Objekten dieser Typen mithilfe von LINQ to XML herstellen.  Auf XML\-Daten, bei denen es sich um die Bindungsquelle im Markup handelt, kann mithilfe von LINQ to XML auf einfache Weise über ein <xref:System.Windows.Data.ObjectDataProvider>\-Objekt zugegriffen werden.  Weitere Informationen finden Sie unter [Binden an XDocument, XElement oder LINQ für XML\-Abfrageergebnisse](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).|  
|<xref:System.Windows.DependencyObject>\-Objekte|Sie können mit den [Abhängigkeitseigenschaften](GTMT) von <xref:System.Windows.DependencyObject> eine Bindung herstellen.  Ein Beispiel finden Sie unter [Binden der Eigenschaften von zwei Steuerelementen](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md).|  
  
<a name="classes"></a>   
## Implementieren einer Klasse als Bindungsquelle  
 Sie können eigene Bindungsquellen erstellen.  In diesem Abschnitt erfahren Sie, wie Sie eine Klasse als Bindungsquelle implementieren können.  
  
### Bereitstellen von Änderungsbenachrichtigungen  
 Wenn Sie die <xref:System.Windows.Data.BindingMode>\-Bindung oder die <xref:System.Windows.Data.BindingMode>\-Bindung verwenden \(da die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] bei einer Änderung der Eigenschaften der Bindungsquelle dynamisch aktualisiert werden soll\), müssen Sie einen geeigneten Mechanismus für die Änderungsbenachrichtigung implementieren.  Empfohlen wird hierbei, dass die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Klasse oder die dynamische Klasse die <xref:System.ComponentModel.INotifyPropertyChanged>\-Schnittstelle implementiert.  Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Beim Erstellen eines [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekts, das <xref:System.ComponentModel.INotifyPropertyChanged> nicht implementiert, müssen Sie Ihr eigenes Benachrichtigungssystem einrichten, um sicherzustellen, dass die in einer Bindung verwendeten Daten immer aktuell sind.  Sie können Änderungsbenachrichtigungen bereitstellen, indem Sie das `PropertyChanged`\-Muster für jede Eigenschaft, für die Änderungsbenachrichtigungen ausgegeben werden sollen, unterstützen.  Um dieses Muster zu unterstützen, definieren Sie für jede Eigenschaft ein *Name\_der\_Eigenschaft*Changed\-Ereignis, wobei *Name\_der\_Eigenschaft* der Name der jeweiligen Eigenschaft ist.  Dieses Ereignis wird bei jeder Änderung der Eigenschaft ausgelöst.  
  
 Wenn die Bindungsquelle einen dieser Benachrichtigungsmechanismen implementiert, erfolgt die Aktualisierung des Ziels automatisch.  Falls die Bindungsquelle aus irgendeinem Grund keine ordnungsgemäße Benachrichtigung für Eigenschaftsänderungen bereitstellt, kann die Zieleigenschaft explizit mit der <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A>\-Methode aktualisiert werden.  
  
### Weitere Merkmale  
 In der folgenden Liste finden Sie weitere zu beachtende Punkte:  
  
-   Wenn Sie das Objekt mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellen möchten, muss die Klasse über einen Standardkonstruktor verfügen.  In einigen [!INCLUDE[TLA2#tla_net](../../../../includes/tla2sharptla-net-md.md)]\-Sprachen wie [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] wird der Standardkonstruktor eventuell automatisch erstellt.  
  
-   Die als Bindungsquelleigenschaften für eine Bindung verwendeten Eigenschaften müssen öffentliche Eigenschaften der Klasse sein.  Explizit definierte Schnittstelleneigenschaften sowie geschützte, private, interne und virtuelle Eigenschaften können nicht für eine Bindung herangezogen werden.  
  
-   An öffentliche Felder kann keine Bindung hergestellt werden.  
  
-   Der in der Klasse deklarierte Eigenschaftentyp ist der an die Bindung übergebene Typ.  Allerdings wird der letztendlich in der Bindung verwendete Typ durch die Eigenschaft des [Bindungsziels](GTMT) und nicht durch die Bindungsquelleigenschaft bestimmt.  Falls sich die Typen unterscheiden, können Sie ggf. einen Konverter erstellen, der vorgibt, wie die benutzerdefinierte Eigenschaft anfänglich an die Bindung übergeben wird.  Weitere Informationen finden Sie unter <xref:System.Windows.Data.IValueConverter>.  
  
<a name="objects"></a>   
## Verwenden von ganzen Objekten als Bindungsquelle  
 Sie können das gesamte Objekt als Bindungsquelle verwenden.  Sie können eine Bindungsquelle mit den Eigenschaften <xref:System.Windows.Data.Binding.Source%2A> oder <xref:System.Windows.FrameworkElement.DataContext%2A> angeben und dann eine leere Bindungsdeklaration bereitstellen: `{Binding}`.  Diese Vorgehensweise eignet sich zum Beispiel für Szenarien, bei denen die Bindung an string\-Objekte, an Objekte mit mehreren relevanten Eigenschaften oder an Auflistungsobjekte erfolgt.  Ein Beispiel für die Bindung an ein gesamtes Auflistungsobjekt finden Sie unter [Verwenden des Master\-\/Detailmusters mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Beachten Sie, dass Sie ggf. benutzerdefinierte Logik anwenden müssen, damit die Daten für die gebundene Zieleigenschaft sinnvoll sind.  Bei der benutzerdefinierten Logik kann es sich zum Beispiel um einen benutzerspezifischen Konverter \(falls keine Standardkonvertierung vorhanden ist\) oder um <xref:System.Windows.DataTemplate> handeln.  Weitere Informationen zu Konvertern finden Sie im Abschnitt zur Datenkonvertierung unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
<a name="collections"></a>   
## Verwenden von Auflistungsobjekten als Bindungsquelle  
 Häufig handelt es sich bei dem Objekt, das Sie verwenden möchten, um eine Auflistung benutzerdefinierter Objekte.  Jedes Objekt fungiert als Quelle für eine Instanz einer wiederholten Bindung.  So verfügen Sie vielleicht über eine `CustomerOrders`\-Auflistung mit `CustomerOrder`\-Objekten, die wiederholt von Ihrer Anwendung durchlaufen wird, um festzustellen, wie viele Bestellungen mit welchen Daten vorhanden sind.  
  
 Sie können jede Auflistung auflisten, die die <xref:System.Collections.IEnumerable>\-Schnittstelle implementiert.  Um dynamische Bindungen einzurichten, bei denen die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] automatisch nach Einfügungen oder Löschungen in der Auflistung aktualisiert wird, muss die Auflistung die <xref:System.Collections.Specialized.INotifyCollectionChanged>\-Schnittstelle implementieren.  Diese Schnittstelle macht ein Ereignis verfügbar, das bei jeder Änderung der zugrunde liegenden Auflistung ausgelöst werden muss.  
  
 Die <xref:System.Collections.ObjectModel.ObservableCollection%601>\-Klasse ist eine integrierte Implementierung einer Datensammlung, die die <xref:System.Collections.Specialized.INotifyCollectionChanged>\-Schnittstelle verfügbar macht.  Die einzelnen Datenobjekte in der Auflistung müssen die zuvor beschriebenen Anforderungen erfüllen.  Ein Beispiel finden Sie unter [Erstellen und Binden an ObservableCollection](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md).  Statt eigene Auflistungen zu implementieren, können Sie auch <xref:System.Collections.ObjectModel.ObservableCollection%601> bzw. eine vorhandene Auflistungsklasse wie <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> oder <xref:System.ComponentModel.BindingList%601> verwenden.  
  
 WPF wird nie direkt an eine Auflistung gebunden.  Wenn Sie eine Auflistung als Bindungsquelle angeben, wird WPF an die Standardansicht der Auflistung gebunden.  Weitere Informationen über Standardansichten finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Wenn Sie in einem erweiterten Szenario eine eigene Auflistung implementieren möchten, sollten Sie die Verwendung der <xref:System.Collections.IList>\-Schnittstelle in Erwägung ziehen.  <xref:System.Collections.IList> stellt eine nicht generische Auflistung von Objekten bereit, auf die einzeln nach Index zugegriffen werden kann. Dadurch kann die Leistung verbessert werden.  
  
<a name="permissions"></a>   
## Berechtigungsanforderungen bei der Datenbindung  
 Bei der Datenbindung muss die Vertrauensebene der Anwendung beachtet werden.  Die folgende Tabelle enthält eine Übersicht über die Eigenschaftstypen, mit denen in einer Anwendung, die mit voller oder teilweiser Vertrauenswürdigkeit ausgeführt wird, eine Bindung hergestellt werden kann:  
  
|Eigenschaftentyp<br /><br /> \(alle Zugriffsmodifizierer\)|Dynamische Objekteigenschaft|Dynamische Objekteigenschaft|CLR\-Eigenschaft|CLR\-Eigenschaft|Abhängigkeitseigenschaft|Abhängigkeitseigenschaft|  
|--------------------------------------------------------|----------------------------------|----------------------------------|----------------------|----------------------|------------------------------|------------------------------|  
|****Vertrauensebene****|****Volle Vertrauenswürdigkeit****|****Teilweise Vertrauenswürdigkeit****|****Volle Vertrauenswürdigkeit****|****Teilweise Vertrauenswürdigkeit****|****Volle Vertrauenswürdigkeit****|****Teilweise Vertrauenswürdigkeit****|  
|Öffentliche Klasse|Ja|Ja|Ja|Ja|Ja|Ja|  
|Nicht öffentliche Klasse|Ja|Nein|Ja|Nein|Ja|Ja|  
  
 In dieser Tabelle werden die folgenden wichtigen Punkte bezüglich der bei der Datenbindung erforderlichen Berechtigungen beschrieben:  
  
-   Bei [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaften funktioniert die Datenbindung, solange das Bindungsmodul mittels Reflektion auf die Bindungsquelleigenschaft zugreifen kann.  Andernfalls wird vom Bindungsmodul eine Warnung ausgegeben, dass die Eigenschaft nicht gefunden wurde. In diesem Fall wird der Fallbackwert bzw. der Standardwert \(sofern verfügbar\) verwendet.  
  
-   Sie können eine Bindung an Eigenschaften für dynamische Objekte herstellen, die zur Kompilierzeit oder Laufzeit definiert werden.  
  
-   Eine Bindung an [Abhängigkeitseigenschaften](GTMT) ist immer möglich.  
  
 Die erforderlichen Berechtigungen für [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Bindungen sind ähnlich: In einer teilweise vertrauenswürdigen Sandbox kann <xref:System.Windows.Data.XmlDataProvider> nur ausgeführt werden, wenn die Berechtigung zum Zugriff auf die angegebenen Daten besteht.  
  
 Objekte mit einem anonymen Typ sind intern.  Eine Bindung an Eigenschaften anonymer Typen kann nur bei der Ausführung mit voller Vertrauenswürdigkeit hergestellt werden.  Weitere Informationen zu anonymen Typen finden Sie unter [Anonyme Typen \(C\#\-Programmierhandbuch\)](../Topic/Anonymous%20Types%20\(C%23%20Programming%20Guide\).md) oder [Anonyme Typen \(Visual Basic\)](../Topic/Anonymous%20Types%20\(Visual%20Basic\).md) \(Visual Basic\).  
  
 Weitere Informationen zur Sicherheit bei teilweiser Vertrauenswürdigkeit finden Sie unter [WPF\-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
## Siehe auch  
 <xref:System.Windows.Data.ObjectDataProvider>   
 <xref:System.Windows.Data.XmlDataProvider>   
 [Angeben der Bindungsquelle](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Übersicht über die WPF\-Datenbindung mit LINQ to XML](../Topic/WPF%20Data%20Binding%20with%20LINQ%20to%20XML%20Overview.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)