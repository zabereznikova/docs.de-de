---
title: "Gültiger Inhalt von XElement- und XDocument-Objekten3 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 0d253586-2b97-459f-b1a7-f30f38f3ed9f
caps.latest.revision: 5
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3db6b15d2b95016db0814f202143ec198425e2ad
ms.lasthandoff: 03/13/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a>Gültiger Inhalt von XElement- und XDocument-Objekten
In diesem Thema werden die gültigen Argumente beschrieben, die an die Konstruktoren und Methoden übergeben werden können, die Sie zum Hinzufügen von Inhalt zu Elementen und Dokumenten verwenden.  
  
## <a name="valid-content"></a>Gültiger Inhalt  
 Abfragen ergeben häufig <xref:System.Collections.Generic.IEnumerable%601> des <xref:System.Xml.Linq.XElement> oder <xref:System.Collections.Generic.IEnumerable%601> des <xref:System.Xml.Linq.XAttribute>. Sie können Auflistungen von <xref:System.Xml.Linq.XElement>- oder <xref:System.Xml.Linq.XAttribute>-Objekten an den <xref:System.Xml.Linq.XElement>-Konstruktor weitergeben. Aus diesem Grund bietet es sich an, die Ergebnisse einer Abfrage als Inhalt an Methoden und Konstruktoren zu übergeben, mit denen Sie XML-Strukturen auffüllen können.  
  
 Beim Hinzufügen einfachen Inhalts können dieser Methode verschiedene Typen übergeben werden. Gültige Typen sind:  
  
-   <xref:System.String>  
  
-   <xref:System.Double>  
  
-   <xref:System.Single>  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Boolean>  
  
-   <xref:System.DateTime>  
  
-   <xref:System.TimeSpan>  
  
-   <xref:System.DateTimeOffset>  
  
-   Alle Typen, die `Object.ToString` implementieren.  
  
-   Alle Typen, die <xref:System.Collections.Generic.IEnumerable%601> implementieren.  
  
 Beim Hinzufügen komplexen Inhalts können an diese Methode verschiedene Typen übergeben werden:  
  
-   <xref:System.Xml.Linq.XObject>  
  
-   <xref:System.Xml.Linq.XNode>  
  
-   <xref:System.Xml.Linq.XAttribute>  
  
-   Alle Typen, die <xref:System.Collections.Generic.IEnumerable%601> implementieren  
  
 Wenn ein Objekt <xref:System.Collections.Generic.IEnumerable%601> implementiert, wird die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung werden hinzugefügt. Wenn die Auflistung <xref:System.Xml.Linq.XNode> oder <xref:System.Xml.Linq.XAttribute>-Objekte enthält, wird jedes Element in der Auflistung getrennt hinzugefügt. Wenn die Auflistung Text (oder Objekte, die in Text umgewandelt wurden) enthält, wird der Text in der Auflistung verkettet und als einzelner Textknoten hinzugefügt.  
  
 Wenn der Inhalt `null` ist, wird nichts hinzugefügt. Bei der Übergabe einer Auflistung können Elemente der Auflistung `null` sein. Ein `null`-Element in der Auflistung hat keine Auswirkungen auf die Struktur.  
  
 Ein hinzugefügtes Attribut muss innerhalb des Elements, in dem es enthalten ist, einen eindeutigen Namen besitzen.  
  
 Beim Hinzufügen von <xref:System.Xml.Linq.XNode>- oder <xref:System.Xml.Linq.XAttribute>-Objekten werden Objekte einfach an die XML-Struktur angefügt, wenn der neue Inhalt kein übergeordnetes Element besitzt. Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird der neue Inhalt geklont, und der neu geklonte Inhalt wird an die XML-Struktur angefügt.  
  
## <a name="valid-content-for-documents"></a>Gültiger Inhalt für Dokumente  
 Es ist nicht möglich, einem Dokument Attribute und einfachen Inhalt hinzuzufügen.  
  
 Die Anzahl der Szenarios, in denen Sie ein <xref:System.Xml.Linq.XDocument> erstellen müssen, ist sehr begrenzt. Stattdessen können Sie i.d.R. die XML-Strukturen mit einem <xref:System.Xml.Linq.XDocument>-Stammknoten erstellen. Sofern es keine bestimmte Anforderung für das Erstellen eines Dokuments gibt (z.B., weil Sie Verarbeitungsanweisungen und Kommentare auf der obersten Ebene erstellen oder Dokumenttypen unterstützen müssen), ist es oft bequemer, <xref:System.Xml.Linq.XElement> als Stammknoten zu verwenden.  
  
 Als gültiger Inhalt für Dokumente gilt z. B.:  
  
-   0 oder ein <xref:System.Xml.Linq.XDocumentType>-Objekt. Die Dokumenttypen müssen vor dem Element kommen.  
  
-   kein oder ein Element  
  
-   keine oder mehrere Kommentare  
  
-   keine oder mehrere Verarbeitungsanweisungen  
  
-   keine oder mehrere Textknoten, die nur Leerraum enthalten  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a>Konstruktoren und Funktionen, die das Hinzufügen von Inhalt erlauben  
 Die folgenden Methoden erlauben Ihnen, untergeordneten Inhalt zu einem <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> hinzuzufügen:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|Erstellt ein <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|Erstellt ein <xref:System.Xml.Linq.XDocument>.|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Fügt Inhalt am Ende des untergeordneten Inhalts von <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> hinzu.|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Fügt Inhalt nach dem <xref:System.Xml.Linq.XNode> hinzu.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Fügt Inhalt vor dem <xref:System.Xml.Linq.XNode> hinzu.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Fügt Inhalt am Anfang des untergeordneten Inhalts des <xref:System.Xml.Linq.XContainer> hinzu.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|Ersetzt die Attribute aus <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|Ersetzt die untergeordneten Knoten durch neuen Inhalt.|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|Ersetzt einen Knoten durch neuen Inhalt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
