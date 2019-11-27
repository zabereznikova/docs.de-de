---
title: XML-Dokumentliteral
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: db77cccd26c87e271d6db45ce514ab6dabbc53e3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349386"
---
# <a name="xml-document-literal-visual-basic"></a>XML-Dokumentliteral (Visual Basic)
Ein literalobjekt, das ein <xref:System.Xml.Linq.XDocument> Objekt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`encoding`|Optional. Literaler Text, der deklariert, welche Codierung das Dokument verwendet.|  
|`standalone`|Optional. LiteralText. Muss "yes" oder "No" lauten.|  
|`piCommentList`|Optional. Die Liste der XML-Verarbeitungsanweisungen und XML-Kommentare. Hat das folgende Format:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Jede `piComment` kann eine der folgenden sein:<br /><br /> -   [XML-Verarbeitungs Anweisungs Literale](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML-Kommentarliterals](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Erforderlich Das Stamm Element des Dokuments. Das Format ist einer der folgenden:<br /><br /> <ul><li>[XML-Elementliterale](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Der eingebettete Ausdruck der Form `<%=` `elementExp` `%>`. Der `elementExp` gibt eine der folgenden zurück:<br /><br /> <ul><li>Ein <xref:System.Xml.Linq.XElement>-Objekt.</li><li>Eine Auflistung, die ein <xref:System.Xml.Linq.XElement> Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> und <xref:System.Xml.Linq.XComment> Objekten enthält.</li></ul></li></ul><br /> Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XDocument>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Ein XML-Dokumentliteral wird durch die XML-Deklaration am Anfang des Literals identifiziert. Obwohl jedes XML-Dokumentliteral genau ein XML-Stamm Element aufweisen muss, kann es eine beliebige Anzahl von XML-Verarbeitungsanweisungen und XML-Kommentaren enthalten.  
  
 Ein XML-Dokumentliteral darf nicht in einem XML-Element vorkommen.  
  
> [!NOTE]
> Ein XML-Literale kann mehrere Zeilen umfassen, ohne Zeilen Fortsetzungs Zeichen zu verwenden. Auf diese Weise können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.  
  
 Der Visual Basic Compiler konvertiert das XML-dokumentliterale in Aufrufe der <xref:System.Xml.Linq.XDocument.%23ctor%2A>-und <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>-Konstruktoren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein XML-Dokument erstellt, das eine XML-Deklaration, eine Verarbeitungsanweisung, einen Kommentar und ein-Element enthält, das ein anderes-Element enthält.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
