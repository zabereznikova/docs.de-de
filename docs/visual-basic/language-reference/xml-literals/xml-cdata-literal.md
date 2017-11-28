---
title: XML-CDATA-Literal (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 906fd2494dd952c08088b9b7e38dba4505780481
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-cdata-literal-visual-basic"></a>XML-CDATA-Literal (Visual Basic)
Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XCData> Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Teile  
 `<![CDATA[`  
 Erforderlich. Kennzeichnet den Anfang des XML-CDATA-Abschnitts.  
  
 `content`  
 Erforderlich. Text-Inhalt im XML-CDATA-Abschnitt angezeigt werden.  
  
 `]]>`  
 Erforderlich. Kennzeichnet das Ende des Abschnitts.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XCData>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 XML-CDATA-Abschnitte enthalten unformatierten Text, der sollten enthalten, jedoch nicht analysiert werden, mit der XML-Code, die es enthält. Ein XML-CDATA-Abschnitt kann es sich um einen beschreibenden Text enthalten. Dies schließt die folgenden reservierte XML-Zeichen. Die XML-CDATA-Abschnitt endet mit der Sequenz "]] >". Dies impliziert die folgenden Punkte:  
  
-   Sie können einen eingebetteten Ausdruck in eine XML CDATA-literal verwenden, da die Trennzeichen für eingebettete Ausdrücke gültigen XML-CDATA-Inhalt sind.  
  
-   XML-CDATA-Abschnitte können nicht geschachtelt werden, da `content` dürfen nicht den Wert "]] >".  
  
 Sie können eine XML CDATA-literal kann einer Variablen zugewiesen oder in einem XML-Elementliteral eingeschlossen wird.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen jedoch Zeilenfortsetzungszeichen nicht verwendet. Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in eine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Programm.  
  
 Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler konvertiert XML CDATA-literal in einem Aufruf der <xref:System.Xml.Linq.XCData.%23ctor%2A> Konstruktor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen CDATA-Abschnitt mit dem Text "darf Literale \<XML > Tags".  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XCData>  
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
