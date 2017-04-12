---
title: "Übersicht zu XML-Literalen (Visual Basic) | Microsoft-Dokumentation"
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
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: 27
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
ms.openlocfilehash: 57d036910ba9e49385caca28de222a8a8e28ec56
ms.lasthandoff: 03/13/2017

---
# <a name="xml-literals-overview-visual-basic"></a>Übersicht zu XML-Literalen (Visual Basic)
Ein *XML-Literal* kann XML direkt in integriert Ihre [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Code. Stellt die XML-Literale Syntax [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekte und ähnelt der XML 1.0-Syntax. Dies erleichtert die XML-Elemente und Dokumente programmgesteuert erstellt werden, da der Code dieselbe Struktur wie die endgültigen XML enthält.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]kompiliert XML-Literale in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekte. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Stellt ein einfaches Objektmodell zur Erstellung und Bearbeitung von XML und dieses Modell integriert auch mit [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>  
  
 Sie können Einbetten einer [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Ausdruck in einem XML-Literal. Zur Laufzeit erstellt die Anwendung ein [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -Objekt für jedes Literal, die Werte von eingebetteten Ausdrücken einbinden. Dadurch können Sie die dynamischen Inhalt in einem XML-literal angeben. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Weitere Informationen zu den Unterschieden zwischen der XML-Literalen Syntax und die XML 1.0-Syntax finden Sie unter [XML-Literale und die XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Einfache Literale  
 Können eine [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -Objekt in Ihrem [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] durch eingeben oder Einfügen von gültigen XML-Code. Ein XML-Elementliteral gibt ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> Weitere Informationen finden Sie unter [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Literale und die XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). Das folgende Beispiel erstellt ein XML‑Element, das mehrere untergeordnete Elemente verfügt.  
  
 [!code-vb[VbXMLSamples&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Sie können ein XML-Dokument erstellen, indem ein XML-literal ab `<?xml version="1.0"?>`, wie im folgenden Beispiel gezeigt. Ein XML-Dokumentliteral gibt ein <xref:System.Xml.Linq.XDocument>Objekt.</xref:System.Xml.Linq.XDocument> Weitere Informationen finden Sie unter [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples&6;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  Die Syntax der XML-Literale in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ist nicht identisch mit der Syntax in der XML 1.0-Spezifikation. Weitere Informationen finden Sie unter [XML-Literale und die XML 1.0-Spezifikation](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Zeilenfortsetzungszeichen  
 Ein XML-Literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen (die Leerzeichen-Unterstrich-EINGABETASTE-Sequenz). Dies erleichtert die XML-Literale in Code mit XML-Dokumenten zu vergleichen.  
  
 Der Compiler behandelt Zeilenfortsetzungszeichen als Teil eines XML-Literals. Daher sollten Sie die Leerzeichen-Unterstrich-EINGABETASTE-Sequenz verwenden, nur, wenn sie Teil der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekt.  
  
 Allerdings benötigen Sie Zeilenfortsetzungszeichen, wenn einen mehrzeiligen Ausdruck in einem eingebetteten Ausdruck. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Einbetten von Abfragen in XML-Literalen  
 Sie können eine Abfrage in einem eingebetteten Ausdruck verwenden. Wenn Sie dies tun, werden die Elemente, die von der Abfrage zurückgegebenen XML-Elements hinzugefügt. Damit können Sie dynamischen Inhalte, z. B. das Ergebnis der Abfrage eines Benutzers auf ein XML-literal hinzufügen.  
  
 Z. B. der folgende Code eine eingebettete Abfrage verwendet zum Erstellen von XML-Elemente aus den Elementen der `phoneNumbers2` array erstellt und dann diese Elemente als untergeordnete Elemente hinzufügen `contact2`.  
  
 [!code-vb[VbXMLSamples&#7;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Der Compiler erstellt wie Objekte aus XML-Literalen  
 Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Compiler übersetzt XML-Literale in Aufrufe der entsprechenden [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Konstruktoren zum Erstellen der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekt. Z. B. die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler übersetzt im folgenden Codebeispiel wird in einen Aufruf der <xref:System.Xml.Linq.XProcessingInstruction>Konstruktor für die XML-Version-Anweisung aufruft, um die <xref:System.Xml.Linq.XElement>Konstruktor für die `<contact>`, `<name>`, und `<phone>` Elemente und Aufrufe der <xref:System.Xml.Linq.XAttribute>Konstruktor für die `type` Attribut.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XProcessingInstruction> Insbesondere anhand der Attribute im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler Ruft die <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29>Konstruktor zweimal.</xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> Der erste Aufruf übergibt den Wert `type` für die `name` -Parameter und den Wert `home` für die `value` Parameter. Der zweite übergibt ebenfalls den Wert `type` für die `name` -Parameter, aber der Wert `work` für die `value` Parameter.  
  
 [!code-vb[VbXMLSamples&6;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-Literale](../../../../visual-basic/language-reference/xml-literals/index.md)
