---
title: Übersicht über Bindungsquellen
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
ms.openlocfilehash: e7546021fbfde3fceea7fd4f1eba10cdc90dff8b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740614"
---
# <a name="binding-sources-overview"></a>Übersicht über Bindungsquellen
Bei der Datenbindung verweist das Bindungsquellenobjekt auf das Objekt, aus dem Sie Daten abrufen. In diesem Thema werden die Objekttypen vorgestellt, die als Bindungsquelle verwendet werden können.

<a name="binding_sources"></a>
## <a name="binding-source-types"></a>Typen von Bindungsquellen
 Bei der Datenbindung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden die folgenden Typen von Bindungsquellen unterstützt:

|Bindungsquelle|Beschreibung|
|--------------------|-----------------|
|Common Language Runtime (CLR)-Objekte|Sie können an die öffentlichen Eigenschaften, unter Eigenschaften und Indexer eines beliebigen Common Language Runtime (CLR)-Objekts binden. Die Bindungs-Engine verwendet die CLR-Reflektion, um die Werte der Eigenschaften zu erhalten. Alternativ können Objekte, die <xref:System.ComponentModel.ICustomTypeDescriptor> oder ein registriertes <xref:System.ComponentModel.TypeDescriptionProvider> implementieren, auch mit der Bindungs-Engine verwendet werden.<br /><br /> Weitere Informationen zum Implementieren einer Klasse, die als Bindungsquelle dienen kann, finden Sie weiter unten in diesem Thema unter [Implementieren einer Klasse als Bindungsquelle](#classes).|
|Dynamische Objekte|Sie können eine Bindung an verfügbare Eigenschaften und Indexer eines Objekts herstellen, das die <xref:System.Dynamic.IDynamicMetaObjectProvider>-Schnittstelle implementiert. Wenn Sie auf den Member im Code zugreifen können, kann daran eine Bindung erfolgen. Wenn Sie z. B. mithilfe eines dynamischen Objekts auf einen Member im Code über `someObjet.AProperty` zugreifen können, können Sie durch Festlegen des Bindungspfads auf `AProperty` eine Bindung herstellen.|
|ADO.NET-Objekte|Sie können an ADO.NET-Objekte binden, z. b. <xref:System.Data.DataTable>. Die ADO.net-<xref:System.Data.DataView> implementiert die <xref:System.ComponentModel.IBindingList>-Schnittstelle, die Änderungs Benachrichtigungen bereitstellt, auf die die Bindungs-Engine lauscht.|
|XML-Objekte|Sie können eine Bindung an eine <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlDocument>oder <xref:System.Xml.XmlElement>an `XPath` Abfragen ausführen und diese ausführen. Eine bequeme Möglichkeit, auf XML-Daten zuzugreifen, die die Bindungs Quelle im Markup ist, ist die Verwendung eines <xref:System.Windows.Data.XmlDataProvider> Objekts. Weitere Informationen finden Sie unter [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).<br /><br /> Sie können auch eine Bindung an eine <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>oder an die Ergebnisse von Abfragen, die für Objekte dieser Typen ausgeführt werden, mithilfe von LINQ to XML binden. Eine bequeme Möglichkeit, LINQ to XML für den Zugriff auf XML-Daten zu verwenden, die die Bindungs Quelle im Markup ist, ist die Verwendung eines <xref:System.Windows.Data.ObjectDataProvider> Objekts. Weitere Informationen finden Sie unter [Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).|
|<xref:System.Windows.DependencyObject>-Objekte|Sie können eine Bindung an Abhängigkeits Eigenschaften beliebiger <xref:System.Windows.DependencyObject>herstellen. Ein Beispiel finden Sie unter [Binden der Eigenschaften von zwei Steuerelementen](how-to-bind-the-properties-of-two-controls.md).|

<a name="classes"></a>
## <a name="implementing-a-class-for-the-binding-source"></a>Implementieren einer Klasse als Bindungsquelle
 Sie können eigene Bindungsquellen erstellen. In diesem Abschnitt erfahren Sie, wie Sie eine Klasse als Bindungsquelle implementieren.

### <a name="providing-change-notifications"></a>Bereitstellen von Änderungsbenachrichtigungen
 Wenn Sie entweder <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Bindung verwenden (da Sie möchten, dass Ihr [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aktualisiert wird, wenn sich die Bindungs Quell Eigenschaften dynamisch ändern), müssen Sie einen geeigneten Benachrichtigungs Mechanismus für geänderte Eigenschaften implementieren. Der empfohlene Mechanismus besteht darin, dass die CLR-Klasse oder die dynamische Klasse die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementiert. Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](how-to-implement-property-change-notification.md).

 Wenn Sie ein CLR-Objekt erstellen, das <xref:System.ComponentModel.INotifyPropertyChanged>nicht implementiert, müssen Sie für Ihr eigenes Benachrichtigungssystem anordnen, um sicherzustellen, dass die in einer Bindung verwendeten Daten aktuell bleiben. Sie können Änderungsbenachrichtigungen bereitstellen, indem Sie das `PropertyChanged`-Muster für jede Eigenschaft unterstützen, für die Änderungsbenachrichtigungen ausgegeben werden sollen. Um dieses Muster zu unterstützen, definieren Sie für jede Eigenschaft ein *Name_der_EigenschaftChanged*-Ereignis, wobei *Name_der_Eigenschaft* der Name der jeweiligen Eigenschaft ist. Dieses Ereignis wird bei jeder Änderung der Eigenschaft ausgelöst.

 Wenn die Bindungsquelle einen dieser Benachrichtigungsmechanismen implementiert, erfolgt die Aktualisierung des Ziels automatisch. Wenn die Bindungs Quelle aus irgendeinem Grund die richtigen Benachrichtigungen über geänderte Eigenschaften nicht bereitstellt, haben Sie die Möglichkeit, die <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A>-Methode zu verwenden, um die Ziel Eigenschaft explizit zu aktualisieren.

### <a name="other-characteristics"></a>Weitere Merkmale
 In der folgenden Liste finden Sie weitere zu beachtende Punkte:

- Wenn Sie das Objekt in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]erstellen möchten, muss die Klasse über einen Parameter losen Konstruktor verfügen. In einigen .NET-Sprachen, wie C#z. b., kann der Parameter lose Konstruktor für Sie erstellt werden.

- Die als Bindungsquelleigenschaften für eine Bindung verwendeten Eigenschaften müssen öffentliche Eigenschaften der Klasse sein. Explizit definierte Schnittstelleneigenschaften sowie geschützte, private, interne und virtuelle Eigenschaften können nicht für eine Bindung herangezogen werden.

- An öffentliche Felder kann keine Bindung erfolgen.

- Der in der Klasse deklarierte Eigenschaftentyp ist der an die Bindung übergebene Typ. Allerdings wird der letztendlich in der Bindung verwendete Typ durch die Eigenschaft des Bindungsziels und nicht durch die Bindungsquelleigenschaft bestimmt. Falls sich die Typen unterscheiden, können Sie ggf. einen Konverter erstellen, der vorgibt, wie die benutzerdefinierte Eigenschaft anfänglich an die Bindung übergeben wird. Weitere Informationen finden Sie unter <xref:System.Windows.Data.IValueConverter>.

<a name="objects"></a>
## <a name="using-entire-objects-as-a-binding-source"></a>Verwenden von gesamten Objekten als Bindungsquelle
 Sie können das gesamte Objekt als Bindungsquelle verwenden. Sie können eine Bindungs Quelle angeben, indem Sie die <xref:System.Windows.Data.Binding.Source%2A> oder die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft verwenden und dann eine leere Bindungs Deklaration angeben: `{Binding}`. Diese Vorgehensweise eignet sich zum Beispiel für Szenarien, bei denen die Bindung an „string“-Objekte, an Objekte mit mehreren relevanten Eigenschaften oder an Auflistungsobjekte erfolgt. Ein Beispiel für die Bindung an ein gesamtes Auflistungsobjekt finden Sie unter [Verwenden des Master/Detail-Musters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).

 Beachten Sie, dass Sie ggf. benutzerdefinierte Logik anwenden müssen, damit die Daten für die gebundene Zieleigenschaft sinnvoll sind. Die benutzerdefinierte Logik kann ein benutzerdefinierter Konverter sein (wenn keine standardmäßige Typkonvertierung vorhanden ist) oder eine <xref:System.Windows.DataTemplate>. Weitere Informationen zu Konvertern finden Sie im Abschnitt „Datenkonvertierung“ in der [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md). Weitere Informationen zu Datenvorlagen finden Sie in der [Übersicht über Datenvorlagen](data-templating-overview.md).

<a name="collections"></a>
## <a name="using-collection-objects-as-a-binding-source"></a>Verwenden von Auflistungsobjekten als Bindungsquelle
 Häufig handelt es sich bei dem Objekt, das Sie verwenden möchten, um eine Auflistung benutzerdefinierter Objekte. Jedes Objekt fungiert als Quelle für eine Instanz einer wiederholten Bindung. So verfügen Sie vielleicht über eine `CustomerOrders`-Auflistung mit `CustomerOrder`-Objekten, die wiederholt von Ihrer Anwendung durchlaufen wird, um festzustellen, wie viele Bestellungen mit welchen Daten vorhanden sind.

 Sie können jede Auflistung auflisten, die die <xref:System.Collections.IEnumerable>-Schnittstelle implementiert. Wenn Sie jedoch dynamische Bindungen einrichten möchten, sodass die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von Einfügungen oder Löschungen in der Auflistung automatisch aktualisiert werden, muss die-Auflistung die <xref:System.Collections.Specialized.INotifyCollectionChanged>-Schnittstelle implementieren. Diese Schnittstelle macht ein Ereignis verfügbar, das bei jeder Änderung der zugrunde liegenden Auflistung ausgelöst werden muss.

 Die <xref:System.Collections.ObjectModel.ObservableCollection%601>-Klasse ist eine integrierte Implementierung einer Datensammlung, die die <xref:System.Collections.Specialized.INotifyCollectionChanged>-Schnittstelle verfügbar macht. Die einzelnen Datenobjekte in der Auflistung müssen die zuvor beschriebenen Anforderungen erfüllen. Ein Beispiel finden Sie unter [Erstellen und Binden an ObservableCollection](how-to-create-and-bind-to-an-observablecollection.md). Bevor Sie eine eigene Auflistung implementieren, erwägen Sie <xref:System.Collections.ObjectModel.ObservableCollection%601> oder einer vorhandenen Sammlung Klassen, z. B. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, und <xref:System.ComponentModel.BindingList%601>, a.

 WPF wird nie direkt an eine Auflistung gebunden. Wenn Sie eine Auflistung als Bindungsquelle angeben, wird WPF an die Standardansicht der Auflistung gebunden. Weitere Informationen zu Standardansichten finden Sie in der [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).

 Wenn Sie ein erweitertes Szenario haben und eine eigene Sammlung implementieren möchten, sollten Sie die Verwendung der <xref:System.Collections.IList>-Schnittstelle in Erwägung gezogen. <xref:System.Collections.IList> bietet eine nicht generische Auflistung von Objekten, auf die einzeln über einen Index zugegriffen werden kann. Dies kann die Leistung verbessern.

<a name="permissions"></a>
## <a name="permission-requirements-in-data-binding"></a>Berechtigungsanforderungen bei der Datenbindung
 Bei der Datenbindung muss die Vertrauensebene der Anwendung beachtet werden. Die folgende Tabelle enthält eine Übersicht über die Eigenschaftstypen, mit denen in einer Anwendung, die mit voller oder teilweiser Vertrauenswürdigkeit ausgeführt wird, eine Bindung hergestellt werden kann:

|Eigenschaftentyp<br /><br /> (alle Zugriffsmodifizierer)|Dynamische Objekteigenschaft|Dynamische Objekteigenschaft|CLR-Eigenschaft|CLR-Eigenschaft|Abhängigkeitseigenschaft|Abhängigkeitseigenschaft|
|------------------------------------------------|-----------------------------|-----------------------------|------------------|------------------|-------------------------|-------------------------|
|**Vertrauensebene**|**Volle Vertrauenswürdigkeit**|**Teilweise Vertrauenswürdigkeit**|**Volle Vertrauenswürdigkeit**|**Teilweise Vertrauenswürdigkeit**|**Volle Vertrauenswürdigkeit**|**Teilweise Vertrauenswürdigkeit**|
|Öffentliche Klasse|Ja|Ja|Ja|Ja|Ja|Ja|
|Nicht öffentliche Klasse|Ja|Nein|Ja|Nein|Ja|Ja|

 In dieser Tabelle werden die folgenden wichtigen Punkte bezüglich der bei der Datenbindung erforderlichen Berechtigungen beschrieben:

- Für CLR-Eigenschaften funktioniert die Datenbindung so lange, wie die Bindungs-Engine über Reflektion auf die Bindungs Quell Eigenschaft zugreifen kann. Andernfalls wird von der Bindungs-Engine eine Warnung ausgegeben, dass die Eigenschaft nicht gefunden wurde. In diesem Fall wird der Fallbackwert bzw. der Standardwert (sofern verfügbar) verwendet.

- Sie können eine Bindung an Eigenschaften für dynamische Objekte herstellen, die zur Kompilier- oder Laufzeit definiert werden.

- Eine Bindung an Abhängigkeitseigenschaften ist immer möglich.

 Die Berechtigungs Anforderung für die XML-Bindung ist ähnlich. In einer teilweise vertrauenswürdigen sandbox schlägt <xref:System.Windows.Data.XmlDataProvider> fehl, wenn er nicht über Berechtigungen für den Zugriff auf die angegebenen Daten verfügt.

 Objekte mit einem anonymen Typ sind intern. Eine Bindung an Eigenschaften anonymer Typen kann nur bei der Ausführung mit voller Vertrauenswürdigkeit hergestellt werden. Weitere Informationen zu anonymen Typen finden Sie unter [Anonyme Typen (C#-Programmierhandbuch)](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) oder [Anonyme Typen (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

 Weitere Informationen zur Sicherheit bei teilweiser Vertrauenswürdigkeit finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.ObjectDataProvider>
- <xref:System.Windows.Data.XmlDataProvider>
- [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über WPF-Datenbindung mit LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Optimieren der Daten bindungsleistung](../advanced/optimizing-performance-data-binding.md)
