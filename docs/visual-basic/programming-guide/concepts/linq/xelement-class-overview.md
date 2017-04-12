---
title: "Übersicht über die XElement-Klasse (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4b46f3cb5e0d59105fbc31424a0408c3421d9cac
ms.lasthandoff: 03/13/2017

---
# <a name="xelement-class-overview-visual-basic"></a>Übersicht über die XElement-Klasse (Visual Basic)
Die <xref:System.Xml.Linq.XElement>-Klasse ist eine der wichtigsten Klassen in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Xml.Linq.XElement> Sie stellt ein XML-Element dar. Diese Klasse kann zum Erstellen von Elementen, zum Ändern des Inhalts des Elements, zum Hinzufügen, Ändern oder Löschen untergeordneter Elemente, zum Hinzufügen von Attributen zu einem Element oder zum Serialisieren des Inhalts eines Elements in Textform verwendet werden. Sie können außerdem Interoperabilität mit anderen Klassen in <xref:System.Xml?displayProperty=fullName>, wie z. B. <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, und <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> </xref:System.Xml?displayProperty=fullName>  
  
## <a name="xelement-functionality"></a>"XElement"-Funktionalität  
 In diesem Thema wird beschrieben, die Funktionalität von der <xref:System.Xml.Linq.XElement>Klasse.</xref:System.Xml.Linq.XElement>  
  
### <a name="constructing-xml-trees"></a>Konstruieren von XML-Strukturen  
 Für das Konstruieren von XML-Strukturen stehen Ihnen verschiedene Möglichkeiten zur Verfügung. So können Sie z. B. Folgendes tun:  
  
-   XML-Strukturen in Code konstruieren Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
-   Sie können XML-Daten aus verschiedenen Quellen, z. B. Analysieren einer <xref:System.IO.TextReader>, Textdateien oder Internetadressen (URLs).</xref:System.IO.TextReader> Weitere Informationen finden Sie unter [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).  
  
-   Sie können eine <xref:System.Xml.XmlReader>um die Struktur aufzufüllen.</xref:System.Xml.XmlReader> Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
-   Wenn Sie ein Modul haben, den Inhalt zu schreiben, können ein <xref:System.Xml.XmlWriter>, können Sie die <xref:System.Xml.Linq.XContainer.CreateWriter%2A>-Methode einen Writer erstellen, den Writer an das Modul übergeben und verwenden Sie die Inhalte, um die die <xref:System.Xml.XmlWriter>Auffüllen der XML-Struktur.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> </xref:System.Xml.XmlWriter>  
  
 Die verbreitetste Variante, eine XML-Struktur zu erstellen, sieht aber wie folgt aus:  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 Umfasst die anderen häufig verwendeten Technik zum Erstellen einer XML-Struktur mit den Ergebnissen einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage um eine XML-Struktur aufzufüllen, wie im folgenden Beispiel gezeigt:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a>Serialisieren von XML-Strukturen  
 Sie können die XML-Struktur Serialisieren einer <xref:System.IO.File>, <xref:System.IO.TextWriter>, oder eine <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File>  
  
 Weitere Informationen finden Sie unter [Serialisieren von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Abrufen von XML-Daten über Achsenmethoden  
 Mit Achsenmethoden können Sie Attribute, untergeordnete Elemente, Nachfolgerelemente und Vorgängerelemente abrufen. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen verwenden Achsenmethoden und bieten verschiedene flexible und leistungsstarke Möglichkeiten zum Navigieren durch eine XML-Struktur und zu deren Verarbeitung.  
  
 Weitere Informationen finden Sie unter [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Abfragen von XML-Strukturen  
 Sie können schreiben [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfragen, die Daten aus einer XML-Struktur zu extrahieren.  
  
 Weitere Informationen finden Sie unter [Abfragen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Ändern von XML-Strukturen  
 Sie können ein Element auf unterschiedliche Weise ändern, z. B. durch Ändern seines Inhalts oder seiner Attribute. Sie können ein Element auch aus seinem übergeordneten Element entfernen.  
  
 Weitere Informationen finden Sie unter [Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML-Programmierung (Übersicht) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
