---
title: XML-Verarbeitungsanweisungsliteral
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 9bd1781e01bc4cbf1ce5da8c454ab2f5a679aead
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400175"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>XML-Verarbeitungsanweisungsliteral (Visual Basic)
Ein Literalwert, der ein <xref:System.Xml.Linq.XProcessingInstruction> Objekt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Bestandteile  
 `<?`  
 Erforderlich. Bezeichnet den Anfang des XML-Verarbeitungsanweisungs-Literals.  
  
 `piName`  
 Erforderlich. Name, der angibt, welche Anwendung die Verarbeitungsanweisung als Ziel hat. Darf nicht mit "XML" oder "XML" beginnen.  
  
 `piData`  
 Optional. Zeichenfolge, die angibt, wie die von Zielanwendung `piName` das XML-Dokument verarbeiten soll.  
  
 `?>`  
 Erforderlich. Bezeichnet das Ende der Verarbeitungsanweisung.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XProcessingInstruction>-Objekt.  
  
## <a name="remarks"></a>Bemerkungen  
 XML-Verarbeitungs Anweisungs Literale geben an, wie Anwendungen ein XML-Dokument verarbeiten sollen. Wenn eine Anwendung ein XML-Dokument lädt, kann die Anwendung die XML-Verarbeitungsanweisungen überprüfen, um zu bestimmen, wie das Dokument verarbeitet wird. Die Anwendung interpretiert die Bedeutung von `piName` und `piData` .  
  
 Das XML-dokumentliterale verwendet eine Syntax, die der XML-Verarbeitungsanweisung ähnelt. Weitere Informationen finden Sie unter [XML Document Literale](xml-document-literal.md).  
  
> [!NOTE]
> Das `piName` Element darf nicht mit den Zeichen folgen "XML" oder "XML" beginnen, da die XML 1,0-Spezifikation diese IDs reserviert.  
  
 Sie können eine XML-Verarbeitungsanweisungs-Literale einer Variablen zuweisen oder Sie in ein XML-Dokumentliteral einschließen.  
  
> [!NOTE]
> Ein XML-Literale kann mehrere Zeilen umfassen, ohne dass Zeilen Fortsetzungs Zeichen erforderlich sind. Auf diese Weise können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.  
  
 Der Visual Basic Compiler konvertiert das XML-Verarbeitungsanweisungsliteral in einen <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> aufrufkonstruktor.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Verarbeitungsanweisung erstellt, die ein Stylesheet für ein XML-Dokument identifiziert.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.Linq.XProcessingInstruction>
- [XML-Dokumentliteral](xml-document-literal.md)
- [XML-Literale](index.md)
- [Erstellen von XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
