---
title: 'Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06e5c6923c26f3cb84b38475d6680523853d727d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>Gewusst wie: Erstellen einer Zeichenfolge aus einem Array mit Char-Werten (Visual Basic)
In diesem Beispiel erstellt die Zeichenfolge "Abcd" aus einzelnen Zeichen.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Diese Methode hat keine besonderen Anforderungen.  
  
 Die Syntax `"a"c`, wobei eine einzelne `c` ein einzelnes Zeichen in Anführungszeichen folgt, wird verwendet, um ein Zeichenliteral erstellt.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 NULL-Zeichen (entspricht `Chr(0)`) in der Zeichenfolge nach zu unerwarteten Ergebnissen führen, wenn die Zeichenfolge verwenden. Das Null-Zeichen werden mit der Zeichenfolge enthalten, aber das Nullzeichen folgen Zeichen in einigen Situationen nicht angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.String>  
 [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
