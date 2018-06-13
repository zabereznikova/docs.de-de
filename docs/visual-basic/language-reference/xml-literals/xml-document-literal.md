---
title: XML-Dokumentliteral (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: bd2ecfb93cfcdb7cf9c115f9a44ac47dd74c4b53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604353"
---
# <a name="xml-document-literal-visual-basic"></a>XML-Dokumentliteral (Visual Basic)
Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XDocument> Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`encoding`|Dies ist optional. Literaltext deklarieren, welche Codierung des Dokuments verwendet.|  
|`standalone`|Dies ist optional. Literaltext. Muss "yes" oder "no".|  
|`piCommentList`|Dies ist optional. Liste der XML-verarbeitungsanweisungen und XML-Kommentare. Weist das folgende Format:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Jede `piComment` kann eines der folgenden sein:<br /><br /> -   [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Erforderlich. Das Stammelement des Dokuments. Das Format ist eines der folgenden:<br /><br /> <ul><li>[XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Eingebetteter Ausdruck der Form `<%=` `elementExp` `%>`. Die `elementExp` gibt einen der folgenden zurück:<br /><br /> <ul><li>Ein <xref:System.Xml.Linq.XElement>-Objekt.</li><li>Eine Auflistung, die einen enthält <xref:System.Xml.Linq.XElement> -Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> und <xref:System.Xml.Linq.XComment> Objekte.</li></ul></li></ul><br /> Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XDocument>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Ein XML-Dokumentliteral wird durch die XML-Deklaration zu Beginn des Literals identifiziert. Obwohl jede XML-Dokumentliteral genau eine XML-Stammelement benötigen, können sie eine beliebige Anzahl von XML-verarbeitungsanweisungen und XML-Kommentare haben.  
  
 Ein XML-Dokumentliteral kann nicht in ein XML-Element angezeigt.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen verwenden. Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein Visual Basic-Programm.  
  
 Visual Basic-Compiler konvertiert die XML-Dokumentliteral in Aufrufe an die <xref:System.Xml.Linq.XDocument.%23ctor%2A> und <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> Konstruktoren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine XML-Dokument, dessen eine XML-Deklaration, eine verarbeitungsanweisung, einen Kommentar und ein Element, das ein anderes Element enthält.  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 <xref:System.Xml.Linq.XComment>  
 <xref:System.Xml.Linq.XDocument>  
 [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)  
 [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
