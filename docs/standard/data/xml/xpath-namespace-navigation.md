---
title: XPath-Namespacenavigation
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 06cc7abb-7416-415c-9dd6-67751b8cabd5
ms.openlocfilehash: f35318b1439b762bf7c87cff217ed1787e8d007c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156321"
---
# <a name="xpath-namespace-navigation"></a>XPath-Namespacenavigation
Zum Verwenden von XPath-Abfragen mit XML-Dokumenten müssen Sie XML-Namespaces und die darin enthaltenen Elemente korrekt adressieren. Mithilfe von Namespaces werden Zweideutigkeiten vermieden, die auftreten können, wenn Namen in mehr als einem Kontext verwendet werden. Der Name `ID` kann beispielsweise auf mehrere ID-Bezeichner verweisen, die unterschiedlichen Elementen eines XML-Dokuments zugewiesen sind. In der Namespace-Syntax werden URIs, Namen und Präfixe zur Unterscheidung der Elemente in einem XML-Dokument definiert.  
  
 Anhand des Beispiels in diesem Thema wird gezeigt, wie Präfixe beim Navigieren in einem XML-Dokument mit dem <xref:System.Xml.XPath.XPathNavigator> verwendet werden. Weitere Informationen zu Namespaces und ihrer Syntax finden Sie unter [XML-Dateien: Einführung in XML-Namespaces](https://docs.microsoft.com/previous-versions/dotnet/articles/bb986013(v=msdn.10)).  
  
## <a name="namespace-declarations"></a>Namespacedeklarationen  
 Mithilfe von Namespacedeklarationen werden die Elemente in einem XML-Dokument beim Verwenden einer Instanz des <xref:System.Xml.XPath.XPathNavigator> unterscheidbar und adressierbar gemacht. Namespacepräfixe stellen eine kurze Syntax für Adressierungsnamespaces bereit.  
  
 Präfixe werden durch folgende Form definiert: `<e:Envelope xmlns:e=http://schemas.xmlsoap.org/soap/envelope/>.` In dieser Syntax ist das Präfix `e` eine Abkürzung für den formalen URI des Namespaces. Sie können das `Body`-Element mit folgender Syntax als Member des `Envelope`-Namespaces kennzeichnen: `e:Body`.  
  
 Im Navigationsbeispiel im nächsten Abschnitt wird auf das folgende XML-Dokument als `response.xml` verwiesen.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<e:Envelope xmlns:e="http://schemas.xmlsoap.org/soap/envelope/">  
  <e:Body>  
    <s:Search xmlns:s="http://schemas.microsoft.com/v1/Search">  
      <r:request xmlns:r="http://schemas.microsoft.com/v1/Search/metadata"
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance">  
      </r:request>  
    </s:Search>  
  </e:Body>  
</e:Envelope>  
```  
  
## <a name="navigation-by-namespace-prefix"></a>Navigation nach Namespace-Präfix  
 Im Code in diesem Abschnitt werden das <xref:System.Xml.XPath.XPathNavigator>-Objekt und das <xref:System.Xml.XmlNamespaceManager>-Objekt verwendet, um das `Search`-Element im XML-Dokument vom vorherigen Abschnitt auszuwählen. Die Abfrage `xpath` enthält Namespace-Präfixe für jedes Element im Pfad. Durch die Angabe der genauen Identität der Namespaces, die die einzelnen Elemente enthalten, wird die korrekte Navigation zum `Search`-Element durch die <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>-Methode sichergestellt.  
  
```csharp  
using (XmlReader reader = XmlReader.Create("response.xml"))  
{  
    XPathDocument doc = new XPathDocument(reader);  
    XPathNavigator nav = doc.CreateNavigator();
  
    XmlNamespaceManager nsmgr = new XmlNamespaceManager(nav.NameTable);  
    nsmgr.AddNamespace("e", @"http://schemas.xmlsoap.org/soap/envelope/");  
    nsmgr.AddNamespace("s", @"http://schemas.microsoft.com/v1/Search");  
    nsmgr.AddNamespace("r", @"http://schemas.microsoft.com/v1/Search/metadata");  
    nsmgr.AddNamespace("i", @"http://www.w3.org/2001/XMLSchema-instance");  
  
    string xpath = "/e:Envelope/e:Body/s:Search";  
  
    XPathNavigator element = nav.SelectSingleNode(xpath, nsmgr);  
  
    Console.WriteLine("Element Prefix:" + element.Prefix +
    " Local name:" + element.LocalName);  
    Console.WriteLine("Namespace URI: " + element.NamespaceURI);  
}  
```  
  
 Die Präzision vollqualifizierter Namespaces und Namen dient nicht nur der Bequemlichkeit. Wenn Sie ein wenig mit der Dokumentdefinition und dem Code in den voranstehenden Beispielen experimentieren, können Sie feststellen, dass bei der Navigation ohne vollqualifizierte Elementnamen Ausnahmen ausgelöst werden. Beispiel: Die Elementdefinition `<Search xmlns="http://schemas.microsoft.com/v1/Search">` und die Abfragezeichenfolge `xpath = "/s:Envelope/s:Body/Search";` würde ohne den Namespacepräfix für das `Search`-Element `null` statt des `Search`-Elements zurückgeben.  
  
## <a name="see-also"></a>Siehe auch

- [Zugreifen auf XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
