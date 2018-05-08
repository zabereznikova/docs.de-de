---
title: XML-Verarbeitungsanweisungsliteral (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: e6d4c200822f58c7dbe5bf423282740d4aa86ac3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>XML-Verarbeitungsanweisungsliteral (Visual Basic)
Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XProcessingInstruction> Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Teile  
 `<?`  
 Erforderlich. Kennzeichnet den Anfang des XML-Verarbeitungsanweisungsliteral.  
  
 `piName`  
 Erforderlich. Namen Sie, der angibt, welche Anwendung die Verarbeitung Anweisung Ziele an. Nicht beginnen mit "Xml" oder "XML".  
  
 `piData`  
 Dies ist optional. Zeichenfolge, der angibt, wie die Anwendung Ziel `piName` sollte das XML-Dokument verarbeitet.  
  
 `?>`  
 Erforderlich. Kennzeichnet das Ende der verarbeitungsanweisung.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XProcessingInstruction>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 XML-Verarbeitung Anweisung Literale geben an, wie ein XML-Dokument Anwendungen verarbeitet werden soll. Wenn eine Anwendung ein XML-Dokument geladen wird, kann die Anwendung bestimmen, wie das Dokument verarbeitet die XML-verarbeitungsanweisungen überprüfen. Die Anwendung interpretiert die Bedeutung der `piName` und `piData`.  
  
 Der XML-Dokumentliteral verwendet die Syntax, ähnlich dem Konzept der XML-verarbeitungsanweisung ist. Weitere Informationen finden Sie unter [XML-Dokument-Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  Die `piName` Element darf nicht mit den Zeichenfolgen "Xml" oder "XML", beginnen, da die XML 1.0-Spezifikation diese Bezeichner reserviert sind.  
  
 Sie können eine XML-Verarbeitungsanweisungsliteral einer Variablen zuweisen oder in einem XML-Dokumentliteral eingeschlossen wird.  
  
> [!NOTE]
>  Ein XML-Literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen. Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein Visual Basic-Programm.  
  
 Visual Basic-Compiler konvertiert XML-Verarbeitungsanweisungsliteral in einen Aufruf der <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> Konstruktor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine verarbeitungsanweisung, ein Stylesheet für ein XML-Dokument identifiziert.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [XML-Dokumentliteral](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
