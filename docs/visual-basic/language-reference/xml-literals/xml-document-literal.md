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
ms.openlocfilehash: bd1b2f43fce563af431d67b3817b05c7c1048314
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866017"
---
# <a name="xml-document-literal-visual-basic"></a>XML-Dokumentliteral (Visual Basic)

Ein Literalwert, der ein <xref:System.Xml.Linq.XDocument> Objekt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`encoding`|Dies ist optional. Literaler Text, der deklariert, welche Codierung das Dokument verwendet.|  
|`standalone`|Dies ist optional. LiteralText. Muss "yes" oder "No" lauten.|  
|`piCommentList`|Dies ist optional. Die Liste der XML-Verarbeitungsanweisungen und XML-Kommentare. Hat das folgende Format:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Dabei kann es sich um `piComment` einen der folgenden handeln:<br /><br /> -   [XML-Verarbeitungs Anweisungs Literale](xml-processing-instruction-literal.md).<br />-   [XML-Kommentarliteral.](xml-comment-literal.md)|  
|`rootElement`|Erforderlich. Das Stamm Element des Dokuments. Das Format ist einer der folgenden:<br /><br /> <ul><li>[XML-Elementliterale](xml-element-literal.md).</li><li>Eingebetteter Ausdruck des Formulars `<%=` `elementExp` `%>` . Der `elementExp` gibt eine der folgenden zurück:<br /><br /> <ul><li>Ein <xref:System.Xml.Linq.XElement>-Objekt.</li><li>Eine Auflistung, die ein <xref:System.Xml.Linq.XElement> -Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> -Objekten und- <xref:System.Xml.Linq.XComment> Objekten enthält.</li></ul></li></ul><br /> Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Rückgabewert  

 Ein <xref:System.Xml.Linq.XDocument>-Objekt.  
  
## <a name="remarks"></a>Bemerkungen  

 Ein XML-Dokumentliteral wird durch die XML-Deklaration am Anfang des Literals identifiziert. Obwohl jedes XML-Dokumentliteral genau ein XML-Stamm Element aufweisen muss, kann es eine beliebige Anzahl von XML-Verarbeitungsanweisungen und XML-Kommentaren enthalten.  
  
 Ein XML-Dokumentliteral darf nicht in einem XML-Element vorkommen.  
  
> [!NOTE]
> Ein XML-Literale kann mehrere Zeilen umfassen, ohne Zeilen Fortsetzungs Zeichen zu verwenden. Auf diese Weise können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.  
  
 Der Visual Basic Compiler konvertiert das XML-Dokumentliteral in Aufrufe der <xref:System.Xml.Linq.XDocument.%23ctor%2A> -und- <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> Konstruktoren.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird ein XML-Dokument erstellt, das eine XML-Deklaration, eine Verarbeitungsanweisung, einen Kommentar und ein-Element enthält, das ein anderes-Element enthält.  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [XML-Verarbeitungsanweisungsliteral](xml-processing-instruction-literal.md)
- [XML-Kommentarliteral](xml-comment-literal.md)
- [XML-Elementliteral](xml-element-literal.md)
- [XML-Literale](index.md)
- [Erstellen von XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Eingebettete Ausdrücke in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
