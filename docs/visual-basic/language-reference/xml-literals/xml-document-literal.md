---
title: XML-Dokumentliteral (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
dev_langs:
- VB
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
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
ms.openlocfilehash: 5d64faddad66eba4029969654388ba7df17e5854
ms.lasthandoff: 03/13/2017

---
# <a name="xml-document-literal-visual-basic"></a>XML-Dokumentliteral (Visual Basic)
Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XDocument>Objekt.</xref:System.Xml.Linq.XDocument>  
  
## <a name="syntax"></a>Syntax  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`encoding`|Optional. Literaltext, der deklariert, welche Codierung das Dokument verwendet.|  
|`standalone`|Optional. Normaler Text. Muss "Ja" oder "no".|  
|`piCommentList`|Optional. Liste der XML-verarbeitungsanweisungen und XML-Kommentare. Hat das folgende Format:<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> Jede `piComment`kann einer der folgenden sein:<br /><br /> -   [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|Erforderlich. Das Stammelement des Dokuments. Das Format ist eines der folgenden:<br /><br /> <ul><li>[XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>Eingebetteter Ausdruck der Form `<%=` `elementExp` `%>`. Die `elementExp` gibt einen der folgenden zurück:<br /><br /> <ul><li>Ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></li><li>Eine Auflistung mit einem <xref:System.Xml.Linq.XElement>-Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>und <xref:System.Xml.Linq.XComment>Objekte.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></li></ul></li></ul><br /> Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).|  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XDocument>Objekt.</xref:System.Xml.Linq.XDocument>  
  
## <a name="remarks"></a>Hinweise  
 Ein XML-Dokumentliteral wird durch die XML-Deklaration am Anfang des Literals identifiziert. Obwohl jedes XML-Dokumentliteral genau ein XML-Stammelement verfügen muss, können sie eine beliebige Anzahl von XML-verarbeitungsanweisungen und XML-Kommentare.  
  
 Ein XML-Dokumentliteral kann nicht in ein XML-Element angezeigt.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen. Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert das XML-Dokumentliteral in Aufrufe an die <xref:System.Xml.Linq.XDocument.%23ctor%2A>und <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>Konstruktoren.</xref:System.Xml.Linq.XDeclaration.%23ctor%2A> </xref:System.Xml.Linq.XDocument.%23ctor%2A>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine XML-Dokument mit einer XML-Deklaration, eine Anweisung zur Verarbeitung, einen Kommentar und ein Element, ein anderes Element enthält.  
  
 [!code-vb[VbXMLSamples&#30;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>   
 <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>   
 <xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument>   
 [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)   
 [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
