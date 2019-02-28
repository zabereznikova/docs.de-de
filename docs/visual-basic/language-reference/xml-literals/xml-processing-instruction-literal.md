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
ms.openlocfilehash: 1906c9101f9a53bde13698d0ed17b7b8d0988c1d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981373"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>XML-Verarbeitungsanweisungsliteral (Visual Basic)
Ein Zeichenfolgenliteral, ein <xref:System.Xml.Linq.XProcessingInstruction> Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Teile  
 `<?`  
 Erforderlich. Gibt den Anfang der XML-Verarbeitungsanweisungsliteral an.  
  
 `piName`  
 Erforderlich. Namen Sie, der angibt, welche Anwendung die Verarbeitungsanweisungszielen an. Nicht beginnen mit "Xml" oder "XML".  
  
 `piData`  
 Dies ist optional. Zeichenfolge, der angibt, wie die Anwendung von soll `piName` das XML-Dokument verarbeitet werden soll.  
  
 `?>`  
 Erforderlich. Kennzeichnet das Ende der verarbeitungsanweisung.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XProcessingInstruction>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 XML-Verarbeitung Anweisung Literale geben an, wie Anwendungen ein XML-Dokument verarbeitet werden soll. Wenn eine Anwendung ein XML-Dokument geladen wird, kann die Anwendung die XML-verarbeitungsanweisungen zu bestimmen, wie zum Verarbeiten des Dokuments überprüfen. Die Anwendung interpretiert die Bedeutung von `piName` und `piData`.  
  
 Das XML-Dokumentliteral verwendet die Syntax, die vergleichbar mit der XML-verarbeitungsanweisung ist. Weitere Informationen finden Sie unter [XML-Dokument-Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  Die `piName` Element darf nicht mit den Zeichenfolgen "Xml" oder "XML", beginnen, da diese Bezeichner für XML 1.0-Spezifikation reserviert sind.  
  
 Sie können eine XML-Verarbeitungsanweisungsliteral einer Variablen zuweisen oder ihn in einem XML-Dokumentliteral.  
  
> [!NOTE]
>  Ein XML-Literal kann mehrere Zeilen umfassen, ohne der Fortsetzung-Zeile-Zeichen. Dadurch können Sie zum Kopieren von Inhalt aus einem XML-Dokument, und fügen ihn direkt in Visual Basic-Programms.  
  
 Visual Basic-Compiler konvertiert die XML-Verarbeitungsanweisungsliteral in einen Aufruf der <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> Konstruktor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine verarbeitungsanweisung, ein Stylesheet für ein XML-Dokument zu identifizieren.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Xml.Linq.XProcessingInstruction>
- [XML-Dokumentliteral](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
