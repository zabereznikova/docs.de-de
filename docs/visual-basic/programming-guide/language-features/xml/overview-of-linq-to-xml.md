---
title: "Übersicht über LINQ to XML in Visual Basic | Microsoft-Dokumentation"
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 508d4a97b0636f10607326eb35c4c5d8c7860873
ms.lasthandoff: 03/13/2017

---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Übersicht über LINQ to XML in Visual Basic
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet Unterstützung für [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] durch XML-Literale und XML-Achseneigenschaften. Dadurch können Sie eine vertraute und praktische Syntax zu verwenden, für die Arbeit mit XML-Code in Ihre [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Code. *XML-Literale* können Sie XML direkt in den Code einfügen. *XML-Achseneigenschaften* ermöglichen es Ihnen, den Zugriff auf untergeordnete Knoten, nachfolgende Knoten und Attribute eines XML-Literals. Weitere Informationen finden Sie unter [Übersicht über XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) und [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]ist eine speicherinterne XML-Programmier-API, die vor allem zum Nutzen [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Obwohl Sie aufrufen können, die [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] APIs direkt nur [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können Sie XML-Literale deklarieren und direkt auf XML-Achseneigenschaften zugreifen.  
  
> [!NOTE]
>  XML-Literale und XML-Achseneigenschaften werden in deklarativem Code in einer ASP.NET-Seite nicht unterstützt. Um Visual Basic-XML-Funktionen verwenden, platzieren Sie Code in einer Code-Behind-Seite in einer ASP.NET-Anwendung.  
  
 ![Link zu Video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") verwandte Videodemos, finden Sie unter [How Do I erste Schritte mit LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) und [Gewusst wie: Erstellen Sie Excel-Tabellen mit LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).  
  
## <a name="creating-xml"></a>Erstellen von XML  
 Es gibt zwei Methoden zum Erstellen von XML-Strukturen in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Sie können XML-Literale direkt im Code deklarieren, oder Sie können die [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] APIs zum Erstellen der Struktur. Mit beiden Vorgehensweisen kann der Code die endgültige Struktur der XML-Struktur entsprechen. Beispielsweise wird im folgenden Codebeispiel wird ein XML-Element erstellt:  
  
 [!code-vb[VbXmlSamples&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Weitere Informationen finden Sie unter [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Zugreifen auf und Navigieren in XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]enthält die XML-Achseneigenschaften zum Zugreifen auf und Navigieren in XML-Strukturen. Diese Eigenschaften können Sie XML-Elemente und Attribute zugreifen, indem die XML-untergeordneten Elementnamen angeben. Alternativ können Sie explizit aufrufen der [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Methoden für die Navigation und Suche nach Elementen und Attributen. Im folgenden Codebeispiel werden z. B. XML-Achseneigenschaften zum Verweisen auf die Attribute und untergeordneten Elemente eines XML-Elements verwendet. Das Codebeispiel verwendet eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] Abfrage zum Abrufen von untergeordneten Elementen und als XML-Elemente, wobei eine Transformation ausgegeben.  
  
 [!code-vb[VbXmlSamples&#8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Weitere Informationen finden Sie unter [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]ermöglicht es Ihnen, geben Sie einen Alias für einen globalen XML-Namespace mithilfe der `Imports` Anweisung. Das folgende Beispiel zeigt, wie Sie die `Imports` Anweisung, um einen XML-Namespace zu importieren:  
  
 [!code-vb[VbXMLSamples&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Sie können einen XML-Namespace-Alias verwenden, beim Zugriff auf XML-Achseneigenschaften und XML-Literale für XML-Dokumente und Elemente deklarieren.  
  
 Können Sie abrufen, ein <xref:System.Xml.Linq.XNamespace>-Objekt für ein bestimmtes Namespacepräfix mithilfe der [GetXmlNamespace-Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).</xref:System.Xml.Linq.XNamespace>  
  
 Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Verwenden von XML-Namespaces in XML-Literalen  
 Das folgende Beispiel zeigt, wie Sie erstellen ein <xref:System.Xml.Linq.XElement>-Objekt, das den globalen Namespace verwendet `ns`:</xref:System.Xml.Linq.XElement>  
  
 [!code-vb[VbXMLSamples&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Compiler übersetzt XML-Literale, die XML-Namespacealiase in entsprechenden Code, die die XML-Notation verwendet wird enthalten, für die Verwendung von XML-Namespaces, mit der `xmlns` Attribut. Beim Kompilieren erzeugt der Code im Beispiel des vorherigen Abschnitts im Wesentlichen den gleichen ausführbaren Code wie im folgenden Beispiel:  
  
 [!code-vb[VbXMLSamples&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Verwenden von XML-Namespaces in XML-Achseneigenschaften  
 XML-Namespaces in XML-Literalen deklariert sind nicht verfügbar für die Verwendung in XML-Achseneigenschaften. Globale Namespaces können jedoch mit den XML-Achseneigenschaften verwendet werden. Verwenden Sie einen Doppelpunkt, um das XML-Namespacepräfix vom lokalen Elementnamen trennen. Beachten Sie folgendes Beispiel:  
  
 [!code-vb[VbXMLSamples&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
