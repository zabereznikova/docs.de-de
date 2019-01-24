---
title: XML-Kommentarliteral (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 96a7281cde546c3077cf15c625c6e09d2d0ee46f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624677"
---
# <a name="xml-comment-literal-visual-basic"></a>XML-Kommentarliteral (Visual Basic)
Ein Zeichenfolgenliteral, ein <xref:System.Xml.Linq.XComment> Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`<!--`|Erforderlich. Kennzeichnet den Anfang des XML-Kommentar.|  
|`content`|Erforderlich. Text, der in der XML-Kommentar angezeigt werden. Eine Reihe von zwei Bindestriche (-) oder das Ende mit einem Bindestrich neben dem schließenden Tag darf keine enthalten werden.|  
|`-->`|Erforderlich. Kennzeichnet das Ende des XML-Kommentar.|  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XComment>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 XML-Kommentarliterale enthalten nicht den Inhalt des Dokuments; Sie enthalten Informationen über das Dokument. Der Abschnitt der XML-Kommentar endet mit der Sequenz "-->". Dies bedeutet Folgendes:  
  
-   Sie können keinen eingebetteten Ausdruck in einem XML-Kommentarliteral verwenden, da die Trennzeichen für eingebettete Ausdrücke gültigen XML-Kommentar Inhalt sind.  
  
-   Abschnitte der XML-Kommentar können nicht geschachtelt werden, da `content` "kann nicht den Wert-->" enthalten.  
  
 Sie können eine Variable einem XML-Kommentarliteral zuweisen, oder Sie können es in ein XML-Elementliteral einschließen.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, ohne das Zeilenfortsetzungszeichen verwenden. Dieses Feature können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in Visual Basic-Programms.  
  
 Visual Basic-Compiler konvertiert die XML-Kommentarliteral in einen Aufruf der <xref:System.Xml.Linq.XComment.%23ctor%2A> Konstruktor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen XML-Kommentar mit dem Text "Dies ist ein Kommentar".  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Xml.Linq.XComment>
- [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
