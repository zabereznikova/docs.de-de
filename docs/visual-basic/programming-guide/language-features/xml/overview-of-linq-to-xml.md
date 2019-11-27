---
title: Übersicht über LINQ to XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: 80d94ecb7dcc196ad831be7418bfecc785015cf9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346238"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Übersicht über LINQ to XML in Visual Basic
Visual Basic bietet Unterstützung für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] über XML-Literale und XML-Achsen Eigenschaften. Dies ermöglicht es Ihnen, eine vertraute, praktische Syntax zum Arbeiten mit XML in Ihrem Visual Basic Code zu verwenden. *XML-Literale* ermöglichen es Ihnen, XML direkt in Ihren Code einzubeziehen. *XML-Achsen Eigenschaften* ermöglichen den Zugriff auf untergeordnete Knoten, Nachfolger Knoten und Attribute eines XML-Literals. Weitere Informationen finden Sie unter [Übersicht über XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) und [zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist eine XML-Programmier-API im Arbeitsspeicher, die speziell für die Nutzung von [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]entworfen wurde. Obwohl Sie die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-APIs direkt aufrufen können, ermöglicht Ihnen nur Visual Basic das Deklarieren von XML-Literalen und den direkten Zugriff auf die XML-Achsen Eigenschaften.  
  
> [!NOTE]
> XML-Literale und XML-Achsen Eigenschaften werden in deklarativem Code auf einer ASP.NET-Seite nicht unterstützt. Wenn Sie Visual Basic XML-Funktionen verwenden möchten, platzieren Sie den Code in der ASP.NET-Anwendung auf einer Code Behind-Seite.  
  
 [Wiedergabe Schaltfläche](./media/overview-of-linq-to-xml/play-video-icon-example.gif) Weitere Informationen zu verwandten Videos finden Sie unter [How do i started with LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) und [How do i create Excel Spreadsheets using LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).   
  
## <a name="creating-xml"></a>Erstellen von XML  
 Es gibt zwei Möglichkeiten zum Erstellen von XML-Strukturen in Visual Basic. Sie können ein XML-Literale direkt im Code deklarieren, oder Sie können die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-APIs verwenden, um die Struktur zu erstellen. Beide Prozesse ermöglichen es dem Code, die endgültige Struktur der XML-Struktur widerzuspiegeln. Im folgenden Codebeispiel wird z. b. ein XML-Element erstellt:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Weitere Informationen finden Sie unter [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Zugreifen auf und Navigieren in XML  
 Visual Basic stellt XML-Achsen Eigenschaften zum Zugreifen auf und Navigieren in XML-Strukturen bereit. Mithilfe dieser Eigenschaften können Sie auf XML-Elemente und-Attribute zugreifen, indem Sie die untergeordneten XML-Elementnamen angeben. Alternativ können Sie die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Methoden zum Navigieren und suchen von Elementen und Attributen explizit aufzurufen. Im folgenden Codebeispiel werden z. b. die XML-Achsen Eigenschaften verwendet, um auf die Attribute und untergeordneten Elemente eines XML-Elements zu verweisen. Im Codebeispiel wird eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage verwendet, um untergeordnete Elemente abzurufen und als XML-Elemente auszugeben, wodurch eine Transformation durchgeführt wird.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Weitere Informationen finden Sie unter [zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Visual Basic ermöglicht es Ihnen, mit der `Imports`-Anweisung einen Alias für einen globalen XML-Namespace anzugeben. Im folgenden Beispiel wird gezeigt, wie Sie die `Imports`-Anweisung verwenden, um einen XML-Namespace zu importieren:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 Sie können einen XML-Namespace-Alias verwenden, wenn Sie auf XML-Achsen Eigenschaften zugreifen und XML-Literale für XML-Dokumente und-Elemente deklarieren.  
  
 Sie können ein <xref:System.Xml.Linq.XNamespace> Objekt für ein bestimmtes Namespace Präfix mit dem [GetXmlNamespace-Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)abrufen.  
  
 Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Verwenden von XML-Namespaces in XML-Literalen  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Xml.Linq.XElement>-Objekt erstellt wird, das den globalen Namespace `ns`verwendet:  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Der Visual Basic-Compiler übersetzt XML-Literale, die XML-Namespace Aliase enthalten, in äquivalenten Code, der die XML-Notation zum Verwenden von XML-Namespaces mit dem `xmlns`-Attribut verwendet. Bei der Kompilierung erzeugt der Code im Beispiel des vorherigen Abschnitts im Grunde denselben ausführbaren Code wie im folgenden Beispiel:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Verwenden von XML-Namespaces in XML-Achsen Eigenschaften  
 XML-Namespaces, die in XML-Literalen deklariert sind, sind nicht für die Verwendung in XML-Achsen Eigenschaften verfügbar. Globale Namespaces können jedoch mit den XML-Achsen Eigenschaften verwendet werden. Verwenden Sie einen Doppelpunkt, um das XML-Namespace Präfix vom lokalen Elementnamen zu trennen. Beachten Sie folgendes Beispiel:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
