---
title: 'Gewusst wie: Suchen innerhalb einer Zeichenfolge (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 08a005f2927a76c9b29c1ff0092ea8282188b2b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647682"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Gewusst wie: Suchen innerhalb einer Zeichenfolge (Visual Basic)
Dieses Beispiel ruft die <xref:System.String.IndexOf%2A> Methode auf eine <xref:System.String> Objekt, das den Index des ersten Vorkommens einer Teilzeichenfolge gemeldet.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein `Imports` Anweisung Angabe der <xref:System> Namespace. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die <xref:System.String.IndexOf%2A> -Methode gibt den Speicherort des ersten Zeichens des ersten Vorkommens der Teilzeichenfolge. Der Index ist 0-basierte, was bedeutet, dass das erste Zeichen einer Zeichenfolge mit den Index 0 hat.  
  
 Wenn <xref:System.String.IndexOf%2A> findet nicht die Teilzeichenfolge, wird-1 zurückgegeben.  
  
 Die <xref:System.String.IndexOf%2A> Methode Groß-/Kleinschreibung beachtet, und die aktuelle Kultur verwendet.  
  
 Für eine optimale Fehlersteuerung, möchten Sie möglicherweise die Zeichenfolgensuche in der `Try` -Block ein [versuchen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) Konstruktion.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.String.IndexOf%2A>  
 [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
