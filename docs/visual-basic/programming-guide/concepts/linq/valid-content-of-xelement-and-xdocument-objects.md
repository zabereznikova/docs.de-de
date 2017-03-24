---
title: "Gültiger Inhalt von XElement- und XDocument-Objekte2 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f752ae346167709b95e758d15c1785ba7b6fcc5f
ms.lasthandoff: 03/13/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a>Gültiger Inhalt von XElement- und XDocument-Objekten
In diesem Thema werden die gültigen Argumente beschrieben, die an die Konstruktoren und Methoden übergeben werden können, die Sie zum Hinzufügen von Inhalt zu Elementen und Dokumenten verwenden.  
  
## <a name="valid-content"></a>Gültiger Inhalt  
 Abfragen ergeben häufig <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Xml.Linq.XElement> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Sie können Sammlungen von übergeben <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>Objekte, die <xref:System.Xml.Linq.XElement>Konstruktor.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Aus diesem Grund bietet es sich an, die Ergebnisse einer Abfrage als Inhalt an Methoden und Konstruktoren zu übergeben, mit denen Sie XML-Strukturen auffüllen können.  
  
 Beim Hinzufügen einfachen Inhalts können dieser Methode verschiedene Typen übergeben werden. Gültige Typen sind:  
  
-   <xref:System.String></xref:System.String>  
  
-   <xref:System.Double></xref:System.Double>  
  
-   <xref:System.Single></xref:System.Single>  
  
-   <xref:System.Decimal></xref:System.Decimal>  
  
-   <xref:System.Boolean></xref:System.Boolean>  
  
-   <xref:System.DateTime></xref:System.DateTime>  
  
-   <xref:System.TimeSpan></xref:System.TimeSpan>  
  
-   <xref:System.DateTimeOffset></xref:System.DateTimeOffset>  
  
-   Alle Typen, die `Object.ToString` implementieren.  
  
-   Jeder Typ, <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> implementiert  
  
 Beim Hinzufügen komplexen Inhalts können an diese Methode verschiedene Typen übergeben werden:  
  
-   <xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObject>  
  
-   <xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XNode>  
  
-   <xref:System.Xml.Linq.XAttribute>  
  
-   Jeder Typ, implementiert<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>  
  
 Wenn ein Objekt implementiert <xref:System.Collections.Generic.IEnumerable%601>, die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung hinzugefügt werden.</xref:System.Collections.Generic.IEnumerable%601> Wenn die Auflistung enthält <xref:System.Xml.Linq.XNode>oder <xref:System.Xml.Linq.XAttribute>Objekte, die jedes Element in der Auflistung getrennt hinzugefügt.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode> Wenn die Auflistung Text (oder Objekte, die in Text umgewandelt wurden) enthält, wird der Text in der Auflistung verkettet und als einzelner Textknoten hinzugefügt.  
  
 Wenn der Inhalt `null` ist, wird nichts hinzugefügt. Bei der Übergabe einer Auflistung können Elemente der Auflistung `null` sein. Ein `null`-Element in der Auflistung hat keine Auswirkungen auf die Struktur.  
  
 Ein hinzugefügtes Attribut muss innerhalb des Elements, in dem es enthalten ist, einen eindeutigen Namen besitzen.  
  
 Beim Hinzufügen von <xref:System.Xml.Linq.XNode>oder <xref:System.Xml.Linq.XAttribute>-Objekten der neue Inhalt kein übergeordnetes Element besitzt, klicken Sie dann die Objekte werden einfach angefügt der XML-Struktur.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode> Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird der neue Inhalt geklont, und der neu geklonte Inhalt wird an die XML-Struktur angefügt.  
  
## <a name="valid-content-for-documents"></a>Gültiger Inhalt für Dokumente  
 Es ist nicht möglich, einem Dokument Attribute und einfachen Inhalt hinzuzufügen.  
  
 Es gibt nicht viele Szenarios, die Sie erstellen eine <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> erfordern Sie können in der Regel erstellen Sie stattdessen die XML-Strukturen mit einem <xref:System.Xml.Linq.XElement>Stammknoten.</xref:System.Xml.Linq.XElement> Es sei denn, Sie haben eine bestimmte Anforderung zum Erstellen eines Dokuments (z. B., weil Sie verarbeitungsanweisungen und Kommentare auf der obersten Ebene zu erstellen, oder Sie Dokumenttypen unterstützen müssen), ist es oft hilfreich, <xref:System.Xml.Linq.XElement>als Stammknoten.</xref:System.Xml.Linq.XElement>  
  
 Als gültiger Inhalt für Dokumente gilt z. B.:  
  
-   NULL oder eins <xref:System.Xml.Linq.XDocumentType>Objekte.</xref:System.Xml.Linq.XDocumentType> Die Dokumenttypen müssen vor dem Element kommen.  
  
-   kein oder ein Element  
  
-   keine oder mehrere Kommentare  
  
-   keine oder mehrere Verarbeitungsanweisungen  
  
-   keine oder mehrere Textknoten, die nur Leerraum enthalten  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a>Konstruktoren und Funktionen, die das Hinzufügen von Inhalt erlauben  
 Die folgenden Methoden können Sie das untergeordnete Element ein <xref:System.Xml.Linq.XElement>oder ein <xref:System.Xml.Linq.XDocument>:</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> hinzugefügt.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A></xref:System.Xml.Linq.XElement.%23ctor%2A>|Erstellt eine <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A></xref:System.Xml.Linq.XDocument.%23ctor%2A>|Erstellt eine <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument>|  
|<xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A>|Fügt am Ende des untergeordneten Inhalts des <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> hinzu|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Fügt Inhalt nach dem <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Fügt Inhalt vor dem <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A>|Fügt Inhalt am Anfang des untergeordneten Inhalts des <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A></xref:System.Xml.Linq.XElement.ReplaceAll%2A>|Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eine <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|Ersetzt die Attribute einer <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|Ersetzt die untergeordneten Knoten durch neuen Inhalt.|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A></xref:System.Xml.Linq.XNode.ReplaceWith%2A>|Ersetzt einen Knoten durch neuen Inhalt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
