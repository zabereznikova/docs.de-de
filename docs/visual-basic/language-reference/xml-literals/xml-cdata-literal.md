---
title: XML-CDATA-Literal (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
dev_langs:
- VB
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
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
ms.openlocfilehash: 24e52bf203ff3df57e26137da24abcc2cb7e8e20
ms.lasthandoff: 03/13/2017

---
# <a name="xml-cdata-literal-visual-basic"></a>XML-CDATA-Literal (Visual Basic)
Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XCData>Objekt.</xref:System.Xml.Linq.XCData>  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 Ein <xref:System.Xml.Linq.XCData>Objekt.</xref:System.Xml.Linq.XCData>  
  
## <a name="remarks"></a>Hinweise  
 XML-CDATA-Abschnitte enthalten unformatierten Text, der sollte enthalten, jedoch nicht analysiert werden, mit dem XML, das es enthält. Ein XML-CDATA-Abschnitt kann Text enthalten. Dies schließt reservierte XML-Zeichen. XML-CDATA-Abschnitt endet mit der Sequenz "]] >". Dies impliziert die folgenden Punkte:  
  
-   Sie können einen eingebetteten Ausdruck in einem CDATA-literal XML verwenden, da die Trennzeichen für eingebettete Ausdrücke gültiger XML-CDATA-Inhalt sind.  
  
-   XML-CDATA-Abschnitte können nicht geschachtelt werden, da `content` dürfen nicht den Wert "]] >".  
  
 Sie können ein CDATA-literal XML einer Variablen zuweisen oder in einem XML-Elementliteral eingeschlossen werden.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, aber keine Zeilenfortsetzungszeichen verwendet. Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert XML CDATA-literal in einen Aufruf der <xref:System.Xml.Linq.XCData.%23ctor%2A>Konstruktor.</xref:System.Xml.Linq.XCData.%23ctor%2A>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen CDATA-Abschnitt mit dem Text "literal darf \<XML > Tags".  
  
 [!code-vb[VbXMLSamples&23;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XCData></xref:System.Xml.Linq.XCData>   
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
