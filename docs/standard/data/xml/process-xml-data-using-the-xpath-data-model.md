---
title: Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells
ms.date: 03/30/2017
ms.assetid: 536c6fce-1453-4654-9c72-bca54d47e081
ms.openlocfilehash: cc35b570c592557658cd3dda0c844847c8b23763
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829283"
---
# <a name="process-xml-data-using-the-xpath-data-model"></a>Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells
Der <xref:System.Xml?displayProperty=nameWithType>-Namespace bietet mithilfe der <xref:System.Xml.XmlDocument>-Klasse oder der <xref:System.Xml.XPath.XPathDocument>-Klasse eine programmgesteuerte Darstellung von XML-Dokumenten, XML-Fragmenten, XML-Knoten oder XML-Knotengruppen im Speicher.  
  
 Die <xref:System.Xml.XPath.XPathDocument>-Klasse bietet eine schnelle, schreibgeschützte Darstellung eines XML-Dokuments im Speicher mithilfe des XPath-Datenmodells. Die <xref:System.Xml.XmlDocument>-Klasse stellt eine editierbare speicherresidente Darstellung eines XML-Dokuments bereit, die das DOM Level 1 Core und das DOM Level 2 Core des W3C implementiert. Beide Klassen implementieren die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle und geben ein <xref:System.Xml.XPath.XPathNavigator>-Objekt zurück, das verwendet wird, um die zugrunde liegenden XML-Daten auszuwählen, auszuwerten, darin zu navigieren und in einigen Fällen zu bearbeiten.  
  
 In den folgenden Abschnitten werden die Funktionen der <xref:System.Xml.XPath.XPathNavigator>-Klasse beschrieben, die auf der Klasse basiert, von der sie zurückgegeben wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 Beschreibt die Erstellung eines schreibgeschützten Objekts der <xref:System.Xml.XPath.XPathDocument>-Klasse zum Lesen eines XML-Dokuments sowie die Erstellung eines editierbaren Objekts der <xref:System.Xml.XmlDocument>-Klasse zum Lesen und Bearbeiten eines XML-Dokuments. In diesem Thema wird auch beschrieben, wie ein <xref:System.Xml.XPath.XPathNavigator>-Objekt aus jeder Klasse zum Navigieren und Bearbeiten eines XML-Dokuments zurückgegeben wird.  
  
 [Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 Beschreibt die Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse für das Auswählen von Knoten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt mithilfe einer XPath-Abfrage, für das Auswerten und Überprüfen der Ergebnisse eines XPath-Ausdrucks sowie zum Bestimmen, ob ein Knoten in einem XML-Dokument mit einem angegebenen XPath-Ausdruck übereinstimmt.  
  
 [Zugreifen auf XML-Daten mit XPathNavigator](accessing-xml-data-using-xpathnavigator.md)  
 Beschreibt die Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse für das Navigieren von Knoten, das Extrahieren von XML-Daten und das Zugreifen auf stark typisierte XML-Daten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt bereit.  
  
 [Bearbeiten von XML-Daten mit XPathNavigator](editing-xml-data-using-xpathnavigator.md)  
 Beschreibt die Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse für das Einfügen, Ändern oder Entfernen von Knoten und Werten aus einem XML-Dokument, das in einem <xref:System.Xml.XmlDocument>-Objekt enthalten ist.  
  
 [Schemavalidierung mithilfe von „XPathNavigator“](schema-validation-using-xpathnavigator.md)  
 Beschreibt die Möglichkeiten zum Validieren der XML-Inhalte, die in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt enthalten sind.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des DOM](process-xml-data-using-the-dom-model.md)
