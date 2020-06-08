---
title: Vergleich von Knoten mit XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
ms.openlocfilehash: 47b0ba7e705ad602825dcca3f24c207362174a4c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289121"
---
# <a name="matching-nodes-using-xpathnavigator"></a>Vergleich von Knoten mit XPathNavigator
Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode bereit, um zu bestimmen, ob ein Knoten einem XPath-Ausdruck entspricht. Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode verwendet einen XPath-Ausdruck als Eingabe und gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob der aktuelle Knoten dem angegebenen XPath-Ausdruck oder dem angegebenen kompilierten <xref:System.Xml.XPath.XPathExpression>-Objekt entspricht.  
  
## <a name="matching-nodes"></a>Vergleich von Knoten  
 Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode gibt `true` zurück, wenn der aktuelle Knoten dem angegebenen XPath-Ausdruck entspricht. Im folgenden Codebeispiel gibt z. B. die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode `true` zurück, wenn es sich beim aktuellen Knoten um das `b`-Element handelt und das `b`-Element ein `c`-Attribut aufweist.  
  
> [!NOTE]
> Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode ändert den Status des <xref:System.Xml.XPath.XPathNavigator> nicht.  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Auswählen von XML-Daten mit XPathNavigator](select-xml-data-using-xpathnavigator.md)
- [Auswerten von XPath-Ausdrücken mit XPathNavigator](evaluate-xpath-expressions-using-xpathnavigator.md)
- [In XPath-Abfragen erkannte Knotentypen](node-types-recognized-with-xpath-queries.md)
- [XPath-Abfragen und Namespaces](xpath-queries-and-namespaces.md)
- [Kompilierte XPath-Ausdrücke](compiled-xpath-expressions.md)
