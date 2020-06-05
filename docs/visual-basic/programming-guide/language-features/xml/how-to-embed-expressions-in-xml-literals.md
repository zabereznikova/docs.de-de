---
title: 'Vorgehensweise: Einbetten von Ausdrücken in XML-Literale'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 59ba03be6e132203523427d3b7af5a163b6f05ac
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392313"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)
XML-Literale können mit eingebetteten Ausdrücken kombiniert werden, um XML-Dokumente, Fragmente oder Elemente zu erstellen, die zur Laufzeit erstellte Inhalte enthalten. In den folgenden Beispielen wird veranschaulicht, wie eingebettete Ausdrücke verwendet werden, um Elementinhalte, Attribute und Elementnamen zur Laufzeit aufzufüllen.  
  
 Die Syntax für einen eingebetteten Ausdruck ist, bei der es sich um `<%=` `exp` `%>` dieselbe Syntax handelt, die von ASP.NET verwendet wird. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](embedded-expressions-in-xml.md).  
  
 Sie können auch die- [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs verwenden, um-Objekte zu erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] . Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Prozeduren  
  
#### <a name="to-insert-text-as-element-content"></a>So fügen Sie Text als Element Inhalt ein  
  
- Im folgenden Beispiel wird gezeigt, wie der in der-Variable enthaltene Text `contactName` zwischen den öffnenden und schließenden namens Elementen eingefügt wird.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>So fügen Sie Text als Attribut Wert ein  
  
- Im folgenden Beispiel wird gezeigt, wie der in der-Variablen enthaltene Text `phoneType` als Wert des- `type` Attributs eingefügt wird.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>So fügen Sie Text für einen Elementnamen ein  
  
- Im folgenden Beispiel wird gezeigt, wie der in der Variablen enthaltene Text `elementName` als Name eines Elements eingefügt wird.  
  
     Wenn Sie Elemente mit dieser Technik erstellen, müssen Sie Sie mit dem- \</> Tag schließen.  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen von XML-Literalen](how-to-create-xml-literals.md)
- [Eingebettete Ausdrücke in XML](embedded-expressions-in-xml.md)
- [Erstellen von XML in Visual Basic](creating-xml.md)
- [XML](index.md)
