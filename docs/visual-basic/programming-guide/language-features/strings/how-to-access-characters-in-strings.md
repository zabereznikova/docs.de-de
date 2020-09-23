---
title: 'Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 4ea37c4393a8ece5513327b22c6c0ba4b027c781
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059183"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen in Visual Basic

In diesem Beispiel wird veranschaulicht, wie die-Eigenschaft verwendet wird <xref:System.String.Chars%2A> , um auf das Zeichen an der angegebenen Position in einer Zeichenfolge zuzugreifen.  
  
## <a name="example"></a>Beispiel  

 Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen dieser Zeichen in der Zeichenfolge zu erhalten. Sie können sich eine Zeichenfolge als Zeichen Array vorstellen `Char` . Sie können ein bestimmtes Zeichen abrufen, indem Sie über die-Eigenschaft auf den Index dieses Zeichens verweisen <xref:System.String.Chars%2A> .  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 Der `index` -Parameter der- <xref:System.String.Chars%2A> Eigenschaft ist NULL basiert.  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Die- <xref:System.String.Chars%2A> Eigenschaft gibt das Zeichen an der angegebenen Position zurück. Einige Unicode-Zeichen können jedoch durch mehr als ein Zeichen dargestellt werden. Weitere Informationen zum Arbeiten mit Unicode-Zeichen finden Sie unter Gewusst [wie: Konvertieren einer Zeichenfolge in ein Zeichen Array](how-to-convert-a-string-to-an-array-of-characters.md).  
  
 Die- <xref:System.String.Chars%2A> Eigenschaft löst eine <xref:System.IndexOutOfRangeException> Ausnahme aus, wenn der- `index` Parameter größer oder gleich der Länge der Zeichenfolge ist, oder wenn er kleiner als 0 (null) ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String.Chars%2A>
- [Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen](how-to-convert-a-string-to-an-array-of-characters.md)
- [Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic](converting-between-strings-and-other-data-types.md)
- [Zeichenfolgen](index.md)
