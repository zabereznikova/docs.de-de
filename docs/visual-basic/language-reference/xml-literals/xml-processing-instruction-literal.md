---
title: XML-Verarbeitungsanweisungsliteral (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 2903297fa22cd8dc10bc4b12abaa754d4f6284f2
ms.lasthandoff: 03/13/2017

---
# <a name="xml-processing-instruction-literal-visual-basic"></a>XML-Verarbeitungsanweisungsliteral (Visual Basic)
Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XProcessingInstruction>Objekt.</xref:System.Xml.Linq.XProcessingInstruction>  
  
## <a name="syntax"></a>Syntax  
  
```  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Teile  
 `<?`  
 Erforderlich. Kennzeichnet den Anfang des XML-Verarbeitungsanweisungsliteral.  
  
 `piName`  
 Erforderlich. Name, der angibt, welche Anwendung die Verarbeitungsanweisungszielen an. Nicht beginnen mit "Xml" oder "XML".  
  
 `piData`  
 Optional. Zeichenfolge, die angibt, wie die Anwendung Ziel `piName` das XML-Dokument verarbeiten soll.  
  
 `?>`  
 Erforderlich. Kennzeichnet das Ende der verarbeitungsanweisung.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XProcessingInstruction>Objekt.</xref:System.Xml.Linq.XProcessingInstruction>  
  
## <a name="remarks"></a>Hinweise  
 XML-Verarbeitung Anweisung Literale geben an, wie die Anwendung ein XML-Dokument verarbeiten soll. Wenn eine Anwendung ein XML-Dokument geladen wird, kann die Anwendung die XML-verarbeitungsanweisungen zu entscheiden, wie das Dokument verarbeitet überprüfen. Die Anwendung interpretiert die Bedeutung von `piName` und `piData`.  
  
 Das XML-Dokumentliteral verwendet Syntax ähnelt der von der XML-verarbeitungsanweisung. Weitere Informationen finden Sie unter [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  Das `piName` -Element darf nicht mit den Zeichenfolgen "Xml" oder "XML" beginnen, da diese Bezeichner für XML 1.0-Spezifikation reserviert sind.  
  
 Sie können eine XML-Verarbeitungsanweisungsliteral einer Variablen zuweisen oder ihn in ein XML-Dokumentliteral.  
  
> [!NOTE]
>  Ein XML-Literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen. Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert das XML-Verarbeitungsanweisungsliteral in einen Aufruf der <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>Konstruktor.</xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine verarbeitungsanweisung, eine Stylesheet für ein XML-Dokument identifiziert.  
  
 [!code-vb[VbXMLSamples&#28;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>   
 [XML-Dokumentliteral](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
