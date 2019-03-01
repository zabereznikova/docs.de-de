---
title: 'Vorgehensweise: Suchen innerhalb einer Zeichenfolge (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: c150299efe07809d0d33edf882771f552c3e5b63
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982010"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Vorgehensweise: Suchen innerhalb einer Zeichenfolge (Visual Basic)
Dieses Beispiel ruft die <xref:System.String.IndexOf%2A> Methode für eine <xref:System.String> Objekt, das den Index des ersten Vorkommens einer Teilzeichenfolge gemeldet.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein `Imports` angeben der Anweisung die <xref:System> Namespace. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die <xref:System.String.IndexOf%2A> -Methode gibt den Speicherort des ersten Zeichens des ersten Vorkommens der Teilzeichenfolge. Der Index ist 0-basiert, dies bedeutet, dass das erste Zeichen einer Zeichenfolge mit den Index 0 hat.  
  
 Wenn <xref:System.String.IndexOf%2A> findet nicht die Teilzeichenfolge, wird-1 zurückgegeben.  
  
 Die <xref:System.String.IndexOf%2A> -Methode wird die Groß-/Kleinschreibung beachtet und die aktuelle Kultur verwendet.  
  
 Zur optimalen Fehlerbehandlung, Sie möchten die Zeichenfolgensuche in der `Try` -Block eine [testen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) Konstruktion.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.String.IndexOf%2A>
- [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
