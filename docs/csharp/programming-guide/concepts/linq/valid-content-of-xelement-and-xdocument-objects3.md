---
title: Gültiger Inhalt von XElement- und XDocument-Objekten
description: Erfahren Sie mehr über die gültigen Argumente, die an die Konstruktoren und Methoden übergeben werden können, die Sie zum Hinzufügen von Inhalt zu Elementen und Dokumenten verwenden.
ms.date: 07/20/2015
ms.assetid: 0d253586-2b97-459f-b1a7-f30f38f3ed9f
ms.openlocfilehash: dfafbe76b078db6c22b475770ebadaff38c75ba8
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302255"
---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a>Gültiger Inhalt von XElement- und XDocument-Objekten
In diesem Thema werden die gültigen Argumente beschrieben, die an die Konstruktoren und Methoden übergeben werden können, die Sie zum Hinzufügen von Inhalt zu Elementen und Dokumenten verwenden.  
  
## <a name="valid-content"></a>Gültiger Inhalt  
 Abfragen ergeben häufig <xref:System.Collections.Generic.IEnumerable%601> für <xref:System.Xml.Linq.XElement> oder <xref:System.Collections.Generic.IEnumerable%601> für <xref:System.Xml.Linq.XAttribute>. Sie können Auflistungen mit <xref:System.Xml.Linq.XElement>- oder <xref:System.Xml.Linq.XAttribute>-Objekten an den <xref:System.Xml.Linq.XElement>-Konstruktor übergeben. Aus diesem Grund bietet es sich an, die Ergebnisse einer Abfrage als Inhalt an Methoden und Konstruktoren zu übergeben, mit denen Sie XML-Strukturen auffüllen können.  
  
 Beim Hinzufügen einfachen Inhalts können dieser Methode verschiedene Typen übergeben werden. Gültige Typen sind:  
  
- <xref:System.String>  
  
- <xref:System.Double>  
  
- <xref:System.Single>  
  
- <xref:System.Decimal>  
  
- <xref:System.Boolean>  
  
- <xref:System.DateTime>  
  
- <xref:System.TimeSpan>  
  
- <xref:System.DateTimeOffset>  
  
- Alle Typen, die `Object.ToString` implementieren.  
  
- Alle Typen, die <xref:System.Collections.Generic.IEnumerable%601> implementieren.  
  
 Beim Hinzufügen komplexen Inhalts können an diese Methode verschiedene Typen übergeben werden:  
  
- <xref:System.Xml.Linq.XObject>  
  
- <xref:System.Xml.Linq.XNode>  
  
- <xref:System.Xml.Linq.XAttribute>  
  
- alle Typen, die eine <xref:System.Collections.Generic.IEnumerable%601> implementieren  
  
 Wenn ein Objekt eine <xref:System.Collections.Generic.IEnumerable%601> implementiert, wird die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung werden hinzugefügt. Wenn die Auflistung <xref:System.Xml.Linq.XNode>-Objekte oder <xref:System.Xml.Linq.XAttribute>-Objekte enthält, wird jedes Element in der Auflistung getrennt hinzugefügt. Wenn die Auflistung Text (oder Objekte, die in Text umgewandelt wurden) enthält, wird der Text in der Auflistung verkettet und als einzelner Textknoten hinzugefügt.  
  
 Wenn der Inhalt `null` ist, wird nichts hinzugefügt. Bei der Übergabe einer Auflistung können Elemente der Auflistung `null` sein. Ein `null`-Element in der Auflistung hat keine Auswirkungen auf die Struktur.  
  
 Ein hinzugefügtes Attribut muss innerhalb des Elements, in dem es enthalten ist, einen eindeutigen Namen besitzen.  
  
 Wenn der neue Inhalt beim Hinzufügen von <xref:System.Xml.Linq.XNode>-Objekten oder <xref:System.Xml.Linq.XAttribute>-Objekten kein übergeordnetes Element besitzt, werden die Objekte einfach an die XML-Struktur angefügt. Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird der neue Inhalt geklont, und der neu geklonte Inhalt wird an die XML-Struktur angefügt.  
  
## <a name="valid-content-for-documents"></a>Gültiger Inhalt für Dokumente  
 Es ist nicht möglich, einem Dokument Attribute und einfachen Inhalt hinzuzufügen.  
  
 Die Anzahl der Szenarios, in denen Sie ein <xref:System.Xml.Linq.XDocument> erstellen müssen, ist sehr begrenzt. Stattdessen können Sie i. d. R. die XML-Strukturen mit einem <xref:System.Xml.Linq.XElement>-Stammknoten erstellen. Sofern es keine bestimmte Anforderung für das Erstellen eines Dokuments gibt (z. B., weil Sie Verarbeitungsanweisungen und Kommentare auf der obersten Ebene erstellen oder Dokumenttypen unterstützen müssen), ist es oft bequemer, <xref:System.Xml.Linq.XElement> als Stammknoten zu verwenden.  
  
 Als gültiger Inhalt für Dokumente gilt z. B.:  
  
- kein oder ein <xref:System.Xml.Linq.XDocumentType>-Objekt: Die Dokumenttypen müssen vor dem Element kommen.  
  
- kein oder ein Element  
  
- keine oder mehrere Kommentare  
  
- keine oder mehrere Verarbeitungsanweisungen  
  
- keine oder mehrere Textknoten, die nur Leerraum enthalten  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a>Konstruktoren und Funktionen, die das Hinzufügen von Inhalt erlauben  
 Die folgenden Methoden ermöglichen es Ihnen, einem <xref:System.Xml.Linq.XElement>-Objekt oder <xref:System.Xml.Linq.XDocument>-Objekt untergeordneten Inhalt hinzuzufügen:  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A>|Konstruiert ein <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A>|Erstellt ein Objekt vom Typ <xref:System.Xml.Linq.XDocument>.|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Fügt Inhalt am Ende des untergeordneten Inhalts des <xref:System.Xml.Linq.XElement>- oder <xref:System.Xml.Linq.XDocument>-Objekts hinzu.|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Fügt Inhalt nach dem <xref:System.Xml.Linq.XNode> hinzu.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Fügt Inhalt vor dem <xref:System.Xml.Linq.XNode> hinzu.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Fügt Inhalt vor dem untergeordneten Inhalt des <xref:System.Xml.Linq.XContainer> hinzu.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A>|Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|Ersetzt die Attribute eines <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|Ersetzt die untergeordneten Knoten durch neuen Inhalt.|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A>|Ersetzt einen Knoten durch neuen Inhalt.|  
  
## <a name="see-also"></a>Siehe auch

- [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](./linq-to-xml-overview.md)
