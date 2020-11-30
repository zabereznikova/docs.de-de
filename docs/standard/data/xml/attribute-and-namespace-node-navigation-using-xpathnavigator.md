---
title: Das Navigieren durch Attribut- und Namespaceknoten mit "XPathNavigator"
ms.date: 03/30/2017
ms.assetid: 23975f88-e0af-4b88-93de-9e20e11880ad
ms.openlocfilehash: d561afdc477119a6d9d04eacfcd6a6bdb9d0e2d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725390"
---
# <a name="attribute-and-namespace-node-navigation-using-xpathnavigator"></a>Das Navigieren durch Attribut- und Namespaceknoten mit "XPathNavigator"

Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt zwei Gruppen von Navigationsmethoden bereit: Die erste Gruppe, die unter dem Thema [Navigieren in Knotengruppen mit XPathNavigator](node-set-navigation-using-xpathnavigator.md) beschrieben wird, wird zum Navigieren durch *Knotengruppen* in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder <xref:System.Xml.XmlDocument>-Objekt verwendet. Die zweite Gruppe, die in diesem Thema beschrieben wird, wird zum Navigieren durch *Attribut- und Namespaceknoten* in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder <xref:System.Xml.XmlDocument>-Objekt verwendet.  
  
## <a name="attribute-node-navigation"></a>Navigieren durch Attributknoten  

 Attribute sind Eigenschaften eines Elements und keine untergeordneten Elemente des entsprechenden Elements. Diese Unterscheidung ist wegen der zum Navigieren durch nebengeordnete, übergeordnete und untergeordnete Knoten verwendeten Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse wichtig.  
  
 Die <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>-Methode werden z. B. nicht zum Navigieren von einem Element zu einem Attribut oder zwischen Attributen verwendet. Für Attribute gibt es andere Navigationsmethoden.  
  
 Es folgen die die Navigationsmethoden für Attribute der <xref:System.Xml.XPath.XPathNavigator>-Klasse.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNextAttribute%2A>  
  
 Wenn es sich bei dem aktuellen Knoten um ein Element handelt, können Sie mit der <xref:System.Xml.XPath.XPathNavigator.HasAttributes%2A>-Eigenschaft überprüfen, ob Attribute mit dem Element verbunden sind. Wenn bekannt ist, dass ein Element Attribute besitzt, bestehen mehrere Möglichkeiten, um auf die Attribute zuzugreifen. Verwenden Sie die <xref:System.Xml.XPath.XPathNavigator.GetAttribute%2A>-Methode zum Abrufen eines einzelnen Attributs aus dem Element. Verwenden Sie die <xref:System.Xml.XPath.XPathNavigator>-Methode, um den <xref:System.Xml.XPath.XPathNavigator.MoveToAttribute%2A> auf ein bestimmtes Attribute zu positionieren. Sie können auch mit der <xref:System.Xml.XPath.XPathNavigator.MoveToFirstAttribute%2A>-Methode alle Attribute eines Elements durchlaufen und dann mehrmals die <xref:System.Xml.XPath.XPathNavigator.MoveToNextAttribute%2A>-Methode aufrufen.  
  
> [!NOTE]
> Wenn das <xref:System.Xml.XPath.XPathNavigator>-Objekt auf einem Attribut- oder Namespaceknoten positioniert ist, geben die Methoden  <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> und <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> immer `false` zurück und haben keine Auswirkungen auf die Position des <xref:System.Xml.XPath.XPathNavigator>. Die einzigen Ausnahmen sind die Methoden <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A> und <xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>.  
  
## <a name="namespace-node-navigation"></a>Navigation durch Namespaceknoten  

 Jedes Element verfügt über zugeordnete Namespaceknoten, einen für jedes eindeutige Namespacepräfix, das an einen Namespace-URI im Gültigkeitsbereich des Elements gebunden ist (einschließlich des an den `http://www.w3.org/XML/1998/namespace`-Namespace gebundenen XML-Präfixes, das in jedem XML-Dokument implizit deklariert wird), und einen für den Standardnamespace, wenn sich ein solcher im Gültigkeitsbereich des Elements befindet. Das Element ist der übergeordnete Knoten jedes dieser Namespaceknoten. Ein Namespaceknoten ist jedoch kein untergeordneter Knoten seines übergeordneten Elements.  
  
 Wie bei Attributen werden die <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>-Methode nicht zum Navigieren von einem Element zu einem Namespaceknoten oder zwischen Namespaceknoten verwendet. Für Namespaceknoten gibt es andere Navigationsmethoden.  
  
 Es folgen die Navigationsmethoden für Namspaces der <xref:System.Xml.XPath.XPathNavigator>-Klasse.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNamespace%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>  
  
 Jedes Element eines XML-Dokuments befindet sich im Gültigkeitsbereich mindestens eines Namspaceknotens. Dies ist der Namespaceknoten mit dem Präfix `xml` und dem Namespace-URI `http://www.w3.org/XML/1998/namespace`. Verwenden Sie die <xref:System.Xml.XPath.XPathNavigator.GetNamespace%2A>-Methode zum Abrufen eines gültigen Namespace-URIs anhand eines bestimmten Präfixes. Verwenden Sie die <xref:System.Xml.XPath.XPathNavigator>-Methode, um das <xref:System.Xml.XPath.XPathNavigator.MoveToNamespace%2A>-Objekt auf einen bestimmten Namespaceknoten zu verschieben. Sie können auch mit der <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>-Methode alle gültigen Namespaceknoten eines Elements durchlaufen und dann mehrmals die <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>-Methode aufrufen.  
  
> [!NOTE]
> Wenn das <xref:System.Xml.XPath.XPathNavigator>-Objekt auf einem Attribut- oder Namespaceknoten positioniert ist, geben die Methoden  <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A> und <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A> immer `false` zurück und haben keine Auswirkungen auf die Position des <xref:System.Xml.XPath.XPathNavigator>. Die einzigen Ausnahmen sind die Methoden <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>, <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A> und <xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>.  
  
### <a name="the-xpathnamespacescope-enumeration"></a>Die XPathNamespaceScope-Enumeration  

 Beim Navigieren durch Namespaceknoten können die <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>-Methode mit dem <xref:System.Xml.XPath.XPathNamespaceScope>-Parameter aufgerufen werden. Das Verhalten dieser Methoden unterscheidet sich von dem ihrer Gegenstücke, die ohne Parameter aufgerufen werden. Die <xref:System.Xml.XPath.XPathNamespaceScope>-Enumeration enthält die Werte von <xref:System.Xml.XPath.XPathNamespaceScope.All>, <xref:System.Xml.XPath.XPathNamespaceScope.ExcludeXml> oder <xref:System.Xml.XPath.XPathNamespaceScope.Local>.  
  
 In den folgenden Beispielen wird veranschaulicht, welche Namespaces von der <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>-Methode und der <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>-Methode in den verschiedenen Gültigkeitsbereichen eines XML-Dokuments zurückgegeben werden.  
  
```xml  
<root>  
    <element1 xmlns="http://www.contoso.com" xmlns:books="http://www.contoso.com/books">  
        <element2 />  
    </element1>  
</root>  
```  
  
 Die Reihenfolge der Namespaces (der Namespace, auf dem der <xref:System.Xml.XPath.XPathNavigator> nach dem Aufruf der <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>-Methode positioniert ist, gefolgt von Aufrufen der <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>-Methode) lautet wie folgt.  
  
- Bei Positionierung auf `element2`: `xmlns:books="http://www.contoso.com/books"`, `xmlns="http://www.contoso.com"` und `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- Bei Positionierung auf `element1`: `xmlns:books="http://www.contoso.com/books"`, `xmlns="http://www.contoso.com"` und `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- Bei Positionierung auf `root`: `xmlns:xml="http://www.w3.org/XML/1998/namespace".`  
  
> [!NOTE]
> Die <xref:System.Xml.XPath.XPathNavigator>-Klasse gibt Namespaceknoten in umgekehrter Dokumentreihenfolge zurück. Daher erfolgt mit <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> in Wirklichkeit ein Verschiebevorgang auf den letzten Namespaceknoten im aktuellen Gültigkeitsbereich.  
  
 In den folgenden Beispielen wird veranschaulicht, welche Namespaces von der <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>-Methode und der <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>-Methode bei Angabe der <xref:System.Xml.XPath.XPathNamespaceScope>-Enumeration in den verschiedenen Gültigkeitsbereichen eines XML-Dokuments zurückgegeben werden.  
  
```xml  
<root xmlns="http://www.contoso.com" xmlns:a="http://www.contoso.com/a" xmlns:b="http://www.contoso.com/b">  
    <child1 xmlns="" xmlns:a="urn:a">  
        <child2 xmlns:c="urn:c" />  
    </child1>  
</root>  
```  
  
 Bei Positionierung auf `child2` lautet die Reihenfolge der Namespaces (der Namespace, auf dem der <xref:System.Xml.XPath.XPathNavigator> nach dem Aufruf der <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A>-Methode positioniert ist, gefolgt von Aufrufen der <xref:System.Xml.XPath.XPathNavigator.MoveToNextNamespace%2A>-Methode) wie folgt.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.All>: `xmlns:c="urn:c"`, `xmlns:a="urn:a"`, `xmlns=""`, `xmlns:b="http://www.contoso.com/b"`, `xmlns:a="http://www.contoso.com/a"`, `xmlns="http://www.contoso.com"` und `xmlns:xml="http://www.w3.org/XML/1998/namespace"`.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.ExcludeXml>: `xmlns:c="urn:c"`, `xmlns:a="urn:a"`, `xmlns=""`, `xmlns:b="http://www.contoso.com/b"`, `xmlns:a="http://www.contoso.com/a"` und `xmlns="http://www.contoso.com"`.  
  
- <xref:System.Xml.XPath.XPathNamespaceScope.Local>: `xmlns:c="urn:c"`.  
  
> [!NOTE]
> Die <xref:System.Xml.XPath.XPathNavigator>-Klasse gibt Namespaceknoten in umgekehrter Dokumentreihenfolge zurück. Daher erfolgt mit <xref:System.Xml.XPath.XPathNavigator.MoveToFirstNamespace%2A> in Wirklichkeit ein Verschiebevorgang auf den letzten Namespaceknoten im aktuellen Gültigkeitsbereich.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Navigieren in Knotengruppen mit XPathNavigator](node-set-navigation-using-xpathnavigator.md)
- [Extrahieren von XML-Daten mit XPathNavigator](extract-xml-data-using-xpathnavigator.md)
- [Zugreifen auf streng typisierte XML-Daten mit XPathNavigator](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
