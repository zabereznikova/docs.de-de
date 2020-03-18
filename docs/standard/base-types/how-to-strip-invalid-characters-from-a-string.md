---
title: 'Gewusst wie: Entfernen von ungültigen Zeichen aus einer Zeichenfolge'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- cleaning input
- user input, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
ms.openlocfilehash: cc90e6609f9335b7e2f08271e5540b182901e8c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127650"
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a>Gewusst wie: Entfernen von ungültigen Zeichen aus einer Zeichenfolge
Im folgenden Beispiel wird die statische <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>-Methode verwendet, um ungültige Zeichen aus einer Zeichenfolge zu entfernen.  
  
## <a name="example"></a>Beispiel  
 Mit der in diesem Beispiel definierten `CleanInput`-Methode können Sie potenziell schädliche Zeichen entfernen, die in ein Textfeld eingegeben wurden, das Benutzereingaben akzeptiert. In diesem Fall entfernt `CleanInput` alle nicht alphanumerischen Zeichen außer Punkten (.), at-Symbolen (@) und Bindestrichen (-) und gibt die verbleibende Zeichenfolge zurück. Allerdings können Sie Muster für reguläre Ausdrücke ändern, sodass alle Zeichen entfernt werden, die in einer Eingabezeichenfolge nicht enthalten sein sollen.  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 Das Muster für reguläre Ausdrücke `[^\w\.@-]` gleicht alle Zeichen ab, bei denen es sich nicht um Wortzeichen, Punkte, @-Zeichen oder Bindestriche handelt. Wortzeichen sind alle Buchstaben, Dezimalziffern oder verbindende Satzzeichen wie Unterstriche. Alle Zeichen, die diesem Muster entsprechen, werden durch <xref:System.String.Empty?displayProperty=nameWithType> ersetzt. Dies ist die durch das Ersatzmuster definierte Zeichenfolge. Um zusätzliche Zeichen in der Benutzereingabe zu ermöglichen, fügen Sie diese Zeichen der Zeichenklasse im Muster für reguläre Ausdrücke hinzu. Beispiel: Das Muster für reguläre Ausdrücke `[^\w\.@-\\%]` lässt auch ein Prozentsymbol und einen umgekehrten Schrägstrich in einer Eingabezeichenfolge zu.  
  
## <a name="see-also"></a>Weitere Informationen

- [Reguläre Ausdrücke von .NET](../../../docs/standard/base-types/regular-expressions.md)
