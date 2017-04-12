---
title: XML-Kommentarliteral (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
dev_langs:
- VB
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
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
ms.openlocfilehash: 88cfb984be42345ae1e5c998cf82aa1415d2455e
ms.lasthandoff: 03/13/2017

---
# <a name="xml-comment-literal-visual-basic"></a>XML-Kommentarliteral (Visual Basic)
Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XComment>Objekt.</xref:System.Xml.Linq.XComment>  
  
## <a name="syntax"></a>Syntax  
  
```  
<!-- content -->  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`<!--`|Erforderlich. Kennzeichnet den Anfang des XML-Kommentars.|  
|`content`|Erforderlich. Text, der in der XML-Kommentar angezeigt werden. Dürfen keine Reihe von zwei Bindestriche (-) oder mit einem neben dem Endtag ein Bindestrich enden.|  
|`-->`|Erforderlich. Kennzeichnet das Ende des XML-Kommentars.|  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XComment>Objekt.</xref:System.Xml.Linq.XComment>  
  
## <a name="remarks"></a>Hinweise  
 XML-Kommentarliterale enthalten keine Dokumentinhalt; Sie enthalten Informationen über das Dokument. Der XML-Kommentarabschnitt endet mit der Sequenz "-->". Dies impliziert die folgenden Punkte:  
  
-   Sie können einen eingebetteten Ausdruck in einem XML-Kommentarliteral verwenden, da die Trennzeichen für eingebettete Ausdrücke gültiger XML-Kommentar Inhalt sind.  
  
-   XML-Kommentarabschnitte können nicht geschachtelt werden, da `content` kann nicht den Wert "-->" enthalten.  
  
 Sie können eine Variable ein XML-Kommentarliteral zuweisen, oder in einem XML-Elementliteral eingeschlossen wird.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen. Dieses Feature können Sie Inhalt aus einem XML-Dokument kopieren und Einfügen direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert das XML-Kommentarliteral in einen Aufruf der <xref:System.Xml.Linq.XComment.%23ctor%2A>Konstruktor.</xref:System.Xml.Linq.XComment.%23ctor%2A>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen XML-Kommentar mit dem Text "Dies ist ein Kommentar".  
  
 [!code-vb[VbXMLSamples&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>   
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
