---
title: 'Vorgehensweise: Konvertieren einer Zeichenfolge in ein Array von Zeichen'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: e1f634fcdb23f16e794449f8fe7b53c451c8c5b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059170"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Gewusst wie: Konvertieren einer Zeichenfolge in ein Zeichenfolgenarray in Visual Basic

Manchmal ist es sinnvoll, Daten über die Zeichen in der Zeichenfolge und die Positionen der Zeichen in der Zeichenfolge zu erhalten, z. b. Wenn Sie eine Zeichenfolge in eine Zeichenfolge schreiben. Dieses Beispiel zeigt, wie Sie ein Array von Zeichen in einer Zeichenfolge abrufen können, indem Sie die-Methode der Zeichenfolge aufrufen <xref:System.String.ToCharArray%2A> .  
  
## <a name="example"></a>Beispiel  

 Dieses Beispiel zeigt, wie Sie eine Zeichenfolge in ein `Char` -Array aufteilen und eine Zeichenfolge in ein `String` Array von Unicode-Textzeichen aufteilen können. Der Grund für diesen Unterschied besteht darin, dass Unicode-Textzeichen aus mindestens zwei `Char` Zeichen bestehen können (z. b. ein Ersatz Zeichenpaar oder eine kombinierte Zeichen Sequenz). Weitere Informationen finden Sie unter <xref:System.Globalization.TextElementEnumerator> und [im Unicode-Standard](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a>Beispiel  

 Es ist schwieriger, eine Zeichenfolge in die Unicode-Textzeichen aufzuteilen, aber dies ist erforderlich, wenn Sie Informationen zur visuellen Darstellung einer Zeichenfolge benötigen. In diesem Beispiel wird die- <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> Methode verwendet, um Informationen über die Unicode-Textzeichen, die eine Zeichenfolge bilden, zu erhalten.  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Vorgehensweise: Zugreifen auf Zeichen in Zeichenfolgen](how-to-access-characters-in-strings.md)
- [Konvertieren zwischen Zeichenfolgen und anderen Datentypen in Visual Basic](converting-between-strings-and-other-data-types.md)
- [Zeichenfolgen](index.md)
