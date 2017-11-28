---
title: 'Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54d604fc08dd97e0e31f9bcec148431374e8ef8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic
In diesem Beispiel wird veranschaulicht, wie die <xref:System.String.Chars%2A> -Eigenschaft auf das Zeichen an der angegebenen Position in einer Zeichenfolge.  
  
## <a name="example"></a>Beispiel  
 Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der diese Zeichen innerhalb der Zeichenfolge zu verwenden. Sie können eine Zeichenfolge vorstellen, als ein Array von Zeichen (`Char` Instanzen); Sie können ein bestimmtes Zeichen abrufen, indem Sie auf den Index des Zeichens durch Verweisen der <xref:System.String.Chars%2A> Eigenschaft.  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 Die `index` Parameter von der <xref:System.String.Chars%2A> Eigenschaft ist nullbasiert.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die <xref:System.String.Chars%2A> Eigenschaft gibt das Zeichen an der angegebenen Position zurück. Allerdings können einige Unicode-Zeichen durch mehr als ein Zeichen dargestellt werden. Weitere Informationen zum Arbeiten mit Unicode-Zeichen, finden Sie unter [wie: Konvertieren einer Zeichenfolge in ein Array von Zeichen](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).  
  
 Die <xref:System.String.Chars%2A> -Eigenschaft löst eine <xref:System.IndexOutOfRangeException> Ausnahme wenn die `index` Parameter ist größer als oder gleich der Länge der Zeichenfolge ist, oder wenn er kleiner als 0 (null)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.String.Chars%2A>  
 [Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
