---
title: XML-CDATA-Literal
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 72e899e7bd30f2edf0e88207bb3b75bdf36fa11c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349436"
---
# <a name="xml-cdata-literal-visual-basic"></a>XML-CDATA-Literal (Visual Basic)
Ein literalobjekt, das ein <xref:System.Xml.Linq.XCData> Objekt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>-Komponenten  
 `<![CDATA[`  
 Erforderlich Bezeichnet den Anfang des XML-CDATA-Abschnitts.  
  
 `content`  
 Erforderlich Text Inhalt, der im XML-CDATA-Abschnitt angezeigt werden soll.  
  
 `]]>`  
 Erforderlich Bezeichnet das Ende des Abschnitts.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XCData>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 XML-CDATA-Abschnitte enthalten Rohtext, der eingeschlossen, aber nicht analysiert werden soll, mit dem XML-Code, der ihn enthält. Ein XML-CDATA-Abschnitt kann beliebigen Text enthalten. Dies schließt reservierte XML-Zeichen ein. Der XML-CDATA-Abschnitt endet mit der Sequenz "]] >". Dies impliziert die folgenden Punkte:  
  
- Sie können keinen eingebetteten Ausdruck in einem XML-CDATA-Literalformat verwenden, da die eingebetteten Ausdrucks Trennzeichen gültige XML-CDATA-Inhalte sind.  
  
- XML-CDATA-Abschnitte können nicht eingebettet werden, da `content` den Wert "]] >" nicht enthalten kann.  
  
 Sie können eine XML-CDATA-Literale einer Variablen zuweisen oder in ein XML-Elementliteral einschließen.  
  
> [!NOTE]
> XML-Literale können sich über mehrere Zeilen erstrecken, verwenden jedoch keine Zeilen Fortsetzungs Zeichen. Auf diese Weise können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.  
  
 Der Visual Basic Compiler konvertiert das XML-CDATA-Literale in einen-auf<xref:System.Xml.Linq.XCData.%23ctor%2A> rufkonstruktor.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein CDATA-Abschnitt erstellt, der den Text "kann Literale \<XML-> Tags enthalten" enthält.  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XCData>
- [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
