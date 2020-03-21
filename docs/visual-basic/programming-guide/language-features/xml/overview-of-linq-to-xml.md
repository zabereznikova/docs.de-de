---
title: Übersicht über LINQ to XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 0481a140541a7f45c682c5150bc1c3d647de90bd
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266897"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Übersicht über LINQ to XML in Visual Basic
Visual Basic bietet [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Unterstützung durch XML-Literale und XML-Achseneigenschaften. Auf diese Weise können Sie eine vertraute, bequeme Syntax für die Arbeit mit XML in Ihrem Visual Basic-Code verwenden. *Mit XML-Literalen* können Sie XML direkt in Ihren Code aufnehmen. Mithilfe von *XML-Achseneigenschaften* können Sie auf untergeordnete Knoten, abhängige Knoten und Attribute eines XML-Literals zugreifen. Weitere Informationen finden Sie unter [XML-Literalübersicht](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) und [Zugriff auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]ist eine In-Memory-XML-Programmier-API, die speziell entwickelt wurde, um die Vorteile von Language-Integrated Query (LINQ) zu nutzen. Obwohl Sie die LINQ-APIs direkt aufrufen können, können Sie nur mit Visual Basic XML-Literale deklarieren und direkt auf XML-Achseneigenschaften zugreifen.  
  
> [!NOTE]
> XML-Literale und XML-Achseneigenschaften werden in deklarativem Code auf einer ASP.NET Seite nicht unterstützt. Um Visual Basic XML-Features zu verwenden, legen Sie Ihren Code in einer CodeBehind-Seite in Der ASP.NET-Anwendung ab.  
  
 [Play-Taste](./media/overview-of-linq-to-xml/play-video-icon-example.gif) Informationen zu verwandten Videodemonstrationen finden Sie unter [Wie kann ich mit LINQ to XML beginnen?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) und Wie [erstelle ich Excel-Tabellen mit LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).
  
## <a name="creating-xml"></a>Erstellen von XML  
 Es gibt zwei Möglichkeiten, XML-Strukturen in Visual Basic zu erstellen. Sie können ein XML-Literal direkt im Code deklarieren oder die LINQ-APIs verwenden, um die Struktur zu erstellen. Beide Prozesse ermöglichen es dem Code, die endgültige Struktur der XML-Struktur widerzuspiegeln. Im folgenden Codebeispiel wird beispielsweise ein XML-Element erstellt:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Weitere Informationen finden Sie unter [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Zugreifen und Navigieren in XML  
 Visual Basic stellt XML-Achseneigenschaften für den Zugriff auf und die Navigation auf XML-Strukturen bereit. Mit diesen Eigenschaften können Sie auf XML-Elemente und -Attribute zugreifen, indem Sie die untergeordneten XML-Elementnamen angeben. Alternativ können Sie explizit die LINQ-Methoden zum Navigieren und Suchen von Elementen und Attributen aufrufen. Im folgenden Codebeispiel werden beispielsweise XML-Achseneigenschaften verwendet, um auf die Attribute und untergeordneten Elemente eines XML-Elements zu verweisen. Im Codebeispiel wird eine LINQ-Abfrage verwendet, um untergeordnete Elemente abzurufen und als XML-Elemente auszugeben, wodurch eine Transformation effektiv ausgeführt wird.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Weitere Informationen finden Sie [unter Zugriff auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Mit Visual Basic können Sie mithilfe der `Imports` Anweisung einen Alias für einen globalen XML-Namespace angeben. Das folgende Beispiel zeigt, `Imports` wie die Anweisung zum Importieren eines XML-Namespace verwendet wird:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 Sie können einen XML-Namespace-Alias verwenden, wenn Sie auf XML-Achseneigenschaften zugreifen und XML-Literale für XML-Dokumente und -Elemente deklarieren.  
  
 Sie können <xref:System.Xml.Linq.XNamespace> ein Objekt für ein bestimmtes Namespacepräfix abrufen, indem Sie den [GetXmlNamespace-Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)verwenden.  
  
 Weitere Informationen finden Sie unter [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Verwenden von XML-Namespaces in XML-Literalen  
 Das folgende Beispiel zeigt, <xref:System.Xml.Linq.XElement> wie Sie ein `ns`Objekt erstellen, das den globalen Namespace verwendet:  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Der Visual Basic-Compiler übersetzt XML-Literale, die XML-Namespacealiase enthalten, in gleichwertigen `xmlns` Code, der die XML-Notation für die Verwendung von XML-Namespaces verwendet, mit dem Attribut. Beim Kompilieren erzeugt der Code im Beispiel des vorherigen Abschnitts im Wesentlichen denselben ausführbaren Code wie das folgende Beispiel:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Verwenden von XML-Namespaces in XML-Achseneigenschaften  
 XML-Namespaces, die in XML-Literalen deklariert sind, sind für die Verwendung in XML-Achseneigenschaften nicht verfügbar. Globale Namespaces können jedoch mit den XML-Achseneigenschaften verwendet werden. Verwenden Sie einen Doppelpunkt, um das XML-Namespacepräfix vom namen des lokalen Elements zu trennen. Dies ist ein Beispiel:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Xml](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
