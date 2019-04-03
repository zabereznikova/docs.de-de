---
title: Übersicht über LINQ to XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 91f622b9eecdd1aec8b9361493095e92a851988e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816173"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Übersicht über LINQ to XML in Visual Basic
Visual Basic bietet Unterstützung für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] über XML-Literale und XML-Achseneigenschaften. Dadurch können Sie eine vertraute, bequeme Syntax für die Arbeit mit XML in Visual Basic-Code verwenden. *XML-Literale* ermöglichen es Ihnen, XML direkt in Ihrem Code enthalten. *XML-Achseneigenschaften* ermöglichen Ihnen Zugriff auf untergeordnete Knoten untergeordneten Knoten und Attribute eines XML-Literals. Weitere Informationen finden Sie unter [Übersicht über die XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) und [den Zugriff auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist eine speicherinterne XML-Programmier-API, die speziell dazu entwickelt, nutzen [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Obwohl Sie aufrufen können die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] APIs direkt, nur Visual Basic ermöglicht es Ihnen, deklarieren von XML-Literale und XML-Achseneigenschaften direkt zugreifen.  
  
> [!NOTE]
>  XML-Literale und XML-Achseneigenschaften sind in deklarativem Code in einer ASP.NET-Seite nicht unterstützt. Um Visual Basic-XML-Funktionen verwenden, fügen Sie Ihren Code in einer CodeBehind-Seite in Ihrer ASP.NET-Anwendung.  
  
 ![Link zum Video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") verknüpfte video-Vorführungen, finden Sie unter [wie führen ich erste Schritte mit LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) und [durchführen erstellen Excel-Tabellen mithilfe von LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).  
  
## <a name="creating-xml"></a>Erstellen von XML  
 Es gibt zwei Möglichkeiten zum Erstellen von XML-Strukturen in Visual Basic. Sie können XML-Literale direkt im Code deklarieren, oder Sie können die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] APIs, um die Objektstruktur zu erstellen. Beide Prozesse aktivieren Sie den Code, um die endgültige Struktur der XML-Struktur wiederzugeben. Beispielsweise wird im folgenden Codebeispiel wird ein XML-Element erstellt:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Weitere Informationen finden Sie unter [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Zugreifen auf, und Navigieren in XML  
 Visual Basic bietet XML-Achseneigenschaften für den Zugriff, und Navigieren in XML-Strukturen. Diese Eigenschaften können Sie XML-Elemente und Attribute, die durch Angeben von XML--Namen für die untergeordneten Elemente zuzugreifen. Alternativ können Sie explizit aufrufen der [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Methoden für die Navigation und Suche nach Elementen und Attributen. Das folgende Codebeispiel verwendet z. B. XML-Achseneigenschaften zum Verweisen auf die Attribute und untergeordneten Elemente eines XML-Elements an. Das Codebeispiel verwendet einen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage zum Abrufen von untergeordneten Elementen und als XML-Elemente, die Durchführung effektiv einer Transformation ausgegeben.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Weitere Informationen finden Sie unter [den Zugriff auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Visual Basic ermöglicht es Ihnen, geben Sie einen Alias für einen globalen XML-Namespace mithilfe der `Imports` Anweisung. Das folgende Beispiel zeigt, wie Sie mit der `Imports` Anweisung, um ein XML-Namespace importieren:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 Sie können einen XML-Namespace-Alias verwenden, wenn Sie Zugriff auf XML-Achseneigenschaften, und deklarieren die XML-Literale für XML-Dokumente und Elemente.  
  
 Können Sie Abrufen einer <xref:System.Xml.Linq.XNamespace> -Objekt für ein bestimmtes Namespacepräfix mithilfe der [GetXmlNamespace-Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Verwenden von XML-Namespaces in XML-Literalen  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Xml.Linq.XElement> Objekt, das den globalen Namespace verwendet `ns`:  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Visual Basic-Compiler übersetzt XML-Literale, die XML-Namespace-Aliase in entsprechenden Code, die die XML-Notation verwendet wird enthalten, für die Verwendung von XML-Namespaces, mit der `xmlns` Attribut. Beim Kompilieren erzeugt der Code im Beispiel des vorherigen Abschnitts im Wesentlichen die gleichen ausführbaren Code wie im folgenden Beispiel aus:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Verwenden von XML-Namespaces in XML-Achseneigenschaften  
 XML-Namespaces in XML-Literalen deklariert sind nicht verfügbar, für die Verwendung in XML-Achseneigenschaften. Globale Namespaces können jedoch mit der XML-Achseneigenschaften verwendet werden. Verwenden Sie einen Doppelpunkt, um die XML-Namespacepräfixe vom Namen lokalen zu trennen. Beachten Sie folgendes Beispiel:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
