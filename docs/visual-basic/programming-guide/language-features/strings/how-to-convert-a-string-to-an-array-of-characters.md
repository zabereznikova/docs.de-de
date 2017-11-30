---
title: 'Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59d0da52c8f78b93c76325e6242156c106deeaf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray in Visual Basic
Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der diese Zeichen innerhalb der Zeichenfolge, z. B. beim Analysieren einer Zeichenfolge zu verwenden. In diesem Beispiel wird gezeigt, wie Sie ein Array von Zeichen in einer Zeichenfolge abrufen können, durch Aufrufen der Zeichenfolge <xref:System.String.ToCharArray%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie zum Aufteilen einer Zeichenfolge in eine `Char` Array sowie zum Aufteilen einer Zeichenfolge in eine `String` Array von Unicode-Textzeichen. Der Grund für diese Unterscheidung ist, dass von zwei oder mehr Unicode-Textzeichen zusammengesetzt werden können `Char` Zeichen (z. B. ein Ersatzzeichenpaar oder eine Kombination von Zeichen der Sequenz). Weitere Informationen finden Sie unter <xref:System.Globalization.TextElementEnumerator> und "Im Unicode-Standard" auf http://www.unicode.org.  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Es ist schwieriger, eine Zeichenfolge in Unicode-Textzeichen aufgeteilt, aber dies ist erforderlich, wenn Sie Informationen über die visuelle Darstellung einer Zeichenfolge benötigen. Dieses Beispiel verwendet die <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> Methode zum Abrufen von Informationen über die Unicode-Zeichen, die eine Zeichenfolge zu bilden.  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
