---
title: "Overview of LINQ to XML in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LINQ to XML [Visual Basic], about LINQ to XML"
  - "LINQ [Visual Basic], LINQ to XML"
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Overview of LINQ to XML in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] unterstützt [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] durch XML\-Literale und XML\-Achseneigenschaften.  Dies ermöglicht Ihnen, im [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Code mit vertrauter, zweckmäßiger Syntax in XML zu arbeiten. *XML\-Literale* ermöglichen die direkte Aufnahme von XML in den Code.  *XML\-Achseneigenschaften* ermöglichen den Zugriff auf untergeordnete Knoten, nachfolgende Knoten und Attribute eines XML\-Literals.  Weitere Informationen finden Sie unter [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) und unter [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] ist eine XML\-Programmier\-API im Speicher, die speziell entworfen wurde, um die Vorteile von [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] zu nutzen.  Sie können zwar [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-APIs direkt aufrufen, Sie können jedoch nur in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] XML\-Literale deklarieren und direkt auf XML\-Achseneigenschaften zugreifen.  
  
> [!NOTE]
>  In einer ASP.NET\-Seite werden XML\-Literale und XML\-Achseneigenschaften in deklarativem Code nicht unterstützt.  Sie können XML\-Features von Visual Basic verwenden, indem Sie in der ASP.NET\-Anwendung den Code in eine Code\-Behind\-Seite einfügen.  
  
 ![Link zu Video](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Unter [How Do I Get Started with LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) und [How Do I Create Excel Spreadsheets using LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536) finden Sie Videodemonstrationen.  
  
## Erstellen von XML  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] gibt es zwei Möglichkeiten zum Erstellen von XML\-Strukturen.  Sie können XML\-Literale direkt im Code deklarieren oder die Struktur mithilfe der [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-APIs erstellen.  Mit beiden Vorgehensweisen kann die endgültige XML\-Struktur im Code abgebildet werden.  So wird beispielsweise mit dem folgenden Codebeispiel ein XML\-Element erstellt:  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Weitere Informationen finden Sie unter [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## Zugreifen auf und Navigieren in XML  
 Mit den XML\-Achseneigenschaften von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] kann auf XML\-Strukturen zugegriffen und darin navigiert werden.  Diese Eigenschaften ermöglichen den Zugriff auf XML\-Elemente und \-Attribute mittels Namensangabe untergeordneter XML\-Elemente.  Sie können die [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Methoden auch explizit aufrufen, um zwischen Elementen und Attributen zu navigieren und nach diesen zu suchen.  Im folgenden Codebeispiel wird beispielsweise mit XML\-Achseneigenschaften auf Attribute und untergeordnete Elemente eines XML\-Elements Bezug genommen.  Mit einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfrage werden in diesem Beispiel untergeordnete Elemente abgerufen und als XML\-Elemente ausgegeben, wobei eine Transformation stattfindet.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Weitere Informationen finden Sie unter [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## XML\-Namespaces  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] können Sie mit der `Imports`\-Anweisung einen Alias für einen globalen XML\-Namespace angeben.  Im folgenden Beispiel wird gezeigt, wie mit der `Imports`\-Anweisung ein XML\-Namespace importiert werden kann:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Sie können einen Alias für einen XML\-Namespace verwenden, wenn Sie auf XML\-Achseneigenschaften zugreifen und XML\-Literale für XML\-Dokumente und –Elemente deklarieren.  
  
 Sie können ein <xref:System.Xml.Linq.XNamespace>\-Objekt für ein bestimmtes Namespacepräfix abrufen, indem Sie den [GetXmlNamespace Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md) verwenden.  
  
 Weitere Informationen finden Sie unter [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### Verwenden von XML\-Namespaces in XML\-Literalen  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Xml.Linq.XElement>\-Objekt erstellt wird, das den globalen Namespace `ns` verwendet:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 Der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler übersetzt XML\-Literale, die XML\-Namespacealiase enthalten, mit dem `xmlns`\-Attribut in entsprechenden Code, der die XML\-Notation für XML\-Namespaces verwendet.  Beim Kompilieren des Beispielcodes aus dem vorangegangenen Abschnitt wird im Wesentlichen der gleiche ausführbare Code erzeugt wie im folgenden Beispiel:  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### Verwenden von XML\-Namespaces in XML\-Achseneigenschaften  
 In XML\-Literalen deklarierte XML\-Namespaces lassen sich in XML\-Achseneigenschaften nicht verwenden.  Globale Namespaces können jedoch mit den XML\-Achseneigenschaften verwendet werden.  Mit einem Doppelpunkt können Sie das XML\-Namespacepräfix vom lokalen Elementnamen trennen.  Beachten Sie folgendes Beispiel:  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## Siehe auch  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)