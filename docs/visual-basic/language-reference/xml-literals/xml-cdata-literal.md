---
title: XML-CDATA-Literal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 71769c023ba77d40099ba0ba29ef363091e96831
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521555"
---
# <a name="xml-cdata-literal-visual-basic"></a>XML-CDATA-Literal (Visual Basic)
Ein Zeichenfolgenliteral, ein <xref:System.Xml.Linq.XCData> Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Teile  
 `<![CDATA[`  
 Erforderlich. Kennzeichnet den Anfang des XML-CDATA-Abschnitts.  
  
 `content`  
 Erforderlich. Der Textinhalt in einem XML-CDATA-Abschnitt angezeigt werden.  
  
 `]]>`  
 Erforderlich. Kennzeichnet das Ende des Abschnitts.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XCData>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 XML-CDATA-Abschnitten enthalten die unformatierten Text, der sollten enthalten, aber nicht analysiert werden, mit dem XML, das es enthält. Ein XML-CDATA-Abschnitt kann es sich um einen beliebigen Text enthalten. Dies schließt die reservierte XML-Zeichen. Die XML-CDATA-Abschnitt endet mit der Sequenz "]] >". Dies bedeutet Folgendes:  
  
-   Sie können keinen eingebetteten Ausdruck in eine XML CDATA-literal verwenden, da die Trennzeichen für eingebettete Ausdrücke gültige XML-CDATA-Inhalt sind.  
  
-   XML-CDATA-Abschnitte können nicht geschachtelt werden, da `content` dürfen nicht den Wert "]] >".  
  
 Sie können eine XML CDATA-literal einer Variablen zuweisen oder in einem XML-Elementliteral einzuschließen.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, aber keine Zeilenfortsetzungszeichen verwendet. Dadurch können Sie zum Kopieren von Inhalt aus einem XML-Dokument, und fügen ihn direkt in Visual Basic-Programms.  
  
 Visual Basic-Compiler konvertiert XML CDATA-literal in einem Aufruf der <xref:System.Xml.Linq.XCData.%23ctor%2A> Konstruktor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen CDATA-Abschnitt mit dem Text "darf Literale \<XML > Tags".  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Xml.Linq.XCData>
- [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
