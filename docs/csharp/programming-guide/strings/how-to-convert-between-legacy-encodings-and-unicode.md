---
title: 'Gewusst wie: Konvertieren zwischen Legacycodierungen und Unicode (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], legacy to unicode encoding
- strings [C#], converting between encodings
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a016f4ab7de25eec408243cb9b467f9255556bba
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a>Gewusst wie: Konvertieren zwischen Legacycodierungen und Unicode (C#-Programmierhandbuch)
In C# werden alle Zeichenfolgen im Arbeitsspeicher als Unicode (UTF-16) codiert. Wenn Sie Daten aus einem Speicher in ein `string`-Objekt abrufen, werden die Daten automatisch in UTF-16 konvertiert. Falls die Daten lediglich ASCII-Werte von 0 bis 127 enthalten, ist für die Konvertierung kein zusätzlicher Aufwand erforderlich. Falls der Quelltext jedoch erweiterte ASCII-Bytewerte (128 bis 255) enthält, werden die erweiterten Zeichen standardmäßig entsprechend der aktuellen Codeseite interpretiert. Um festzulegen, dass der Quelltext entsprechend einer anderen Codeseite interpretiert werden soll, verwenden Sie wie im folgenden Beispiel dargestellt die Klasse <xref:System.Text.Encoding?displayProperty=fullName>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dargestellt, wie eine Textdatei, die in 8-Bit-ASCII codiert wurde, konvertiert und der Quelltext entsprechend der Windows-Codepage 737 interpretiert wird.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)

