---
title: XML-Kommentarliteral (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d5bb8c10c28a4ab864220c1b4ce4702622e55c92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="xml-comment-literal-visual-basic"></a>XML-Kommentarliteral (Visual Basic)
Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XComment> Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`<!--`|Erforderlich. Kennzeichnet den Anfang des XML-Kommentars.|  
|`content`|Erforderlich. Text, der in der XML-Kommentar angezeigt werden. Eine Reihe von zwei Bindestriche (-) oder das Ende mit einem Bindestrich angrenzend an das Endtag darf keine enthalten werden.|  
|`-->`|Erforderlich. Kennzeichnet das Ende des XML-Kommentars.|  
  
## <a name="return-value"></a>Rückgabewert  
 Ein <xref:System.Xml.Linq.XComment>-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 XML-Kommentarliterale enthalten keine Dokumentinhalt; Sie enthalten Informationen über das Dokument. Der XML-Kommentarabschnitt endet mit der Sequenz "-->". Dies impliziert die folgenden Punkte:  
  
-   Sie können einen eingebetteten Ausdruck in einem XML-Kommentarliteral verwenden, da die Trennzeichen für eingebettete Ausdrücke gültiger XML-Kommentar Inhalt sind.  
  
-   XML-Kommentarabschnitte können nicht geschachtelt werden, da `content` darf keine enthalten den Wert "-->".  
  
 Sie können eine Variable einem XML-Kommentarliteral zuweisen, oder kann in einem XML-Elementliteral eingeschlossen wird.  
  
> [!NOTE]
>  Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen verwenden. Diese Funktion können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein Visual Basic-Programm.  
  
 Visual Basic-Compiler konvertiert die XML-Kommentarliteral in einen Aufruf der <xref:System.Xml.Linq.XComment.%23ctor%2A> Konstruktor.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt einen XML-Kommentar mit dem Text "This is einen Kommentar".  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Linq.XComment>  
 [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
