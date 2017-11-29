---
title: "Übersicht über LINQ to XML in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: baa60939654857f40d323b6412978ed4ff918177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Übersicht über LINQ to XML in Visual Basic
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]bietet Unterstützung für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] über XML-Literale und XML-Achseneigenschaften. Dadurch können Sie eine vertraute und praktische Syntax verwenden, für die Arbeit mit XML-Code in Ihrem [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Code. *XML-Literale* ermöglichen es Ihnen, XML direkt im Code enthalten. *XML-Achseneigenschaften* ermöglichen es Ihnen, die Zugriff auf untergeordnete Knoten untergeordneten Knoten und Attribute eines XML-Literals. Weitere Informationen finden Sie unter [Übersicht über XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) und [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]ist eine speicherinterne XML-Programmier-API, die speziell dazu entwickelt, nutzen [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Obwohl Sie aufrufen können, die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] APIs direkt nur [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ermöglicht es Ihnen, deklarieren von XML-Literale und XML-Achseneigenschaften direkt zugreifen.  
  
> [!NOTE]
>  XML-Literale und XML-Achseneigenschaften werden im deklarativen Code auf einer ASP.NET-Seite nicht unterstützt. Fügen Sie Code zur Verwendung von Visual Basic-XML-Funktionen in einer Code-Behind-Seite in einer ASP.NET-Anwendung.  
  
 ![Link zu Video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") verwandte Videodemonstrationen, finden Sie unter [How Do I erste Schritte mit LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) und [Gewusst wie: Erstellen Sie Excel-Kalkulationstabellen mit LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).  
  
## <a name="creating-xml"></a>Erstellen von XML  
 Es gibt zwei Möglichkeiten zum Erstellen von XML-Strukturen in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Sie können XML-Literale direkt im Code deklarieren, oder Sie können die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] APIs zum Erstellen der Struktur. Beide Prozesse aktivieren Sie den Code entsprechend die endgültige Struktur der XML-Struktur. Beispielsweise wird im folgenden Codebeispiel wird ein XML-Element erstellt:  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Weitere Informationen finden Sie unter [Erstellen von XML-Code in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Zugreifen auf und das Navigieren in XML  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Stellt XML-Achseneigenschaften für den Zugriff, und Navigieren in XML-Strukturen. Diese Eigenschaften ermöglichen es Ihnen, auf XML-Elemente und Attribute durch Angeben von XML-Namen für die untergeordneten Elemente zuzugreifen. Alternativ können Sie explizit aufrufen der [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Methoden zum Navigieren und Suchen von Elementen und Attributen. Das folgende Codebeispiel verwendet z. B. XML-Achseneigenschaften zum Verweisen auf die Attribute und untergeordneten Elemente eines XML-Elements an. Das Codebeispiel verwendet eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage zum Abrufen von untergeordneten Elementen und als XML-Elemente, die effektiv Ausführen einer Transformation ausgegeben.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Weitere Informationen finden Sie unter [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]ermöglicht es Ihnen, geben Sie einen Alias für einen globalen XML-Namespace mithilfe der `Imports` Anweisung. Das folgende Beispiel zeigt, wie Sie die `Imports` Anweisung, um einen XML-Namespace zu importieren:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Sie können einen XML-Namespace-Alias verwenden, beim Zugriff auf XML-Achseneigenschaften und XML-Literale für XML-Dokumente und Elemente deklarieren.  
  
 Können Sie abrufen eine <xref:System.Xml.Linq.XNamespace> -Objekt für ein bestimmtes Namespacepräfix mithilfe der [GetXmlNamespace-Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Verwenden von XML-Namespaces in XML-Literalen  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Xml.Linq.XElement> -Objekt, das den globalen Namespace verwendet `ns`:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler übersetzt XML-Literale, die XML-Namespacealiase in den entsprechenden Code, die der XML-Schreibweise verwendet wird enthalten, für die Verwendung von XML-Namespaces, mit der `xmlns` Attribut. Bei der Kompilierung, erzeugt der Code im Beispiel im vorherigen Abschnitt im Wesentlichen die gleichen ausführbaren Code wie im folgenden Beispiel:  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Verwenden von XML-Namespaces in XML-Achseneigenschaften  
 XML-Namespaces in XML-Literalen deklariert sind nicht für die Verwendung in XML-Achseneigenschaften verfügbar. Allerdings können globale Namespaces mit XML-Achseneigenschaften verwendet werden. Verwenden Sie einen Doppelpunkt, um das XML-Namespacepräfix aus den lokalen Namen zu trennen. Beachten Sie folgendes Beispiel:  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
