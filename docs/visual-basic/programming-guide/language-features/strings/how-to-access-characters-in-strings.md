---
title: 'Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 48507cade639660e6ce36697975d09fb29206c20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649151"
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
