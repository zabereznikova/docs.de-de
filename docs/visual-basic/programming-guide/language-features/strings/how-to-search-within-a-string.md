---
title: 'Gewusst wie: Suchen innerhalb einer Zeichenfolge (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c828d0b32fdf90e121e9d5da0bb60ab11c212f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
