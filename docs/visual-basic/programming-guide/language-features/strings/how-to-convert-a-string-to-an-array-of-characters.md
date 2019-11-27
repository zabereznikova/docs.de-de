---
title: 'Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: d2f7128f97e576d37216d3aa9736921f13f77004
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352445"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray in Visual Basic
Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der Zeichen in der Zeichenfolge zu erhalten, z. b. Wenn Sie eine Zeichenfolge in eine Zeichenfolge schreiben. Dieses Beispiel zeigt, wie Sie ein Array von Zeichen in einer Zeichenfolge abrufen können, indem Sie die <xref:System.String.ToCharArray%2A>-Methode der Zeichenfolge aufrufen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie Sie eine Zeichenfolge in ein `Char` Array aufteilen und eine Zeichenfolge in ein `String` Array ihrer Unicode-Textzeichen aufteilen. Der Grund für diesen Unterschied besteht darin, dass Unicode-Textzeichen aus mindestens zwei `Char` Zeichen bestehen können (z. b. ein Ersatz Zeichenpaar oder eine kombinierte Zeichen Sequenz). Weitere Informationen finden Sie unter <xref:System.Globalization.TextElementEnumerator> und [im Unicode-Standard](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Beispiel  
 Es ist schwieriger, eine Zeichenfolge in die Unicode-Textzeichen aufzuteilen, aber dies ist erforderlich, wenn Sie Informationen zur visuellen Darstellung einer Zeichenfolge benötigen. In diesem Beispiel wird die <xref:System.Globalization.StringInfo.SubstringByTextElements%2A>-Methode verwendet, um Informationen über die Unicode-Textzeichen, die eine Zeichenfolge bilden, zu erhalten.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Gewusst wie: Zugreifen auf Zeichen in Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Zeichenfolgen](../../../../visual-basic/programming-guide/language-features/strings/index.md)
