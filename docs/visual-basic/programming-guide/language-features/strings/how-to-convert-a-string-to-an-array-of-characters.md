---
title: 'Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: 921d7ad62545d3a29870aee6c6b354fdadeb0500
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823310"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen in Visual Basic
Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der diese Zeichen in der Zeichenfolge ein, z. B. Wenn Sie eine Zeichenfolge analysieren. Dieses Beispiel zeigt, wie Sie ein Array von Zeichen in einer Zeichenfolge abrufen können, durch den Aufruf der Zeichenfolge <xref:System.String.ToCharArray%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie zum Aufteilen einer Zeichenfolge in eine `Char` Array und das Aufteilen eine Zeichenfolge in eine `String` Array von Unicode-Textzeichen. Der Grund für diese Unterscheidung ist, dass es sich bei der zwei oder mehr Unicode-Textzeichen zusammengesetzt werden können `Char` Zeichen (z. B. ein Ersatzzeichenpaar oder eine Kombination von Zeichenfolge). Weitere Informationen finden Sie unter <xref:System.Globalization.TextElementEnumerator> und [im Unicode-Standard](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Beispiel  
 Es ist schwieriger, Aufteilen einer Zeichenfolge in Unicode-Textzeichen, aber dies ist erforderlich, wenn Sie Informationen über die visuelle Darstellung einer Zeichenfolge benötigen. Dieses Beispiel verwendet die <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> -Methode zum Abrufen von Informationen über die Unicode-Textzeichen, die eine Zeichenfolge zu bilden.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
