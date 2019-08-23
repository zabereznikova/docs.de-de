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
ms.openlocfilehash: 91369392f33f2a86a7a4cb5ffb3faa668c113348
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965413"
---
# <a name="xml-comment-literal-visual-basic"></a>XML-Kommentarliteral (Visual Basic)
Ein Literalwert <xref:System.Xml.Linq.XComment> , der ein Objekt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`<!--`|Erforderlich. Gibt den Anfang des XML-Kommentars an.|  
|`content`|Erforderlich. Text, der im XML-Kommentar angezeigt werden soll. Kann keine Reihe von zwei Bindestrichen (--) enthalten oder auf einen Bindestrich neben dem schließenden Tag enden.|  
|`-->`|Erforderlich. Bezeichnet das Ende des XML-Kommentars.|  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XComment>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 XML-Kommentar Literale enthalten keinen Dokumentinhalt. Sie enthalten Informationen über das Dokument. Der XML-Kommentar Abschnitt endet mit der Sequenz "-->". Dies impliziert die folgenden Punkte:  
  
- Ein eingebetteter Ausdruck kann nicht in einem XML-kommentarliteralausdruck verwendet werden, da die eingebetteten Ausdrucks Trennzeichen gültige XML-Kommentar Inhalte sind.  
  
- XML-Kommentar Abschnitte können nicht eingebettet werden, `content` da den Wert "-->" nicht enthalten kann.  
  
 Sie können einer Variablen einen XML-Kommentarliterals zuweisen, oder Sie können Sie in ein XML-Elementliteral einschließen.  
  
> [!NOTE]
> Ein XML-Literale kann mehrere Zeilen umfassen, ohne Zeilen Fortsetzungs Zeichen zu verwenden. Mit dieser Funktion können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.  
  
 Der Visual Basic Compiler konvertiert das XML-kommentarliteralzeichen in <xref:System.Xml.Linq.XComment.%23ctor%2A> einen-Konstruktor-Konstruktor.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein XML-Kommentar erstellt, der den Text "This is a comment" enthält.  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XComment>
- [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
