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
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a><span data-ttu-id="eb16b-102">Gewusst wie: Konvertieren zwischen Legacycodierungen und Unicode (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="eb16b-102">How to: Convert Between Legacy Encodings and Unicode (C# Programming Guide)</span></span>
<span data-ttu-id="eb16b-103">In C# werden alle Zeichenfolgen im Arbeitsspeicher als Unicode (UTF-16) codiert.</span><span class="sxs-lookup"><span data-stu-id="eb16b-103">In C#, all strings in memory are encoded as Unicode (UTF-16).</span></span> <span data-ttu-id="eb16b-104">Wenn Sie Daten aus einem Speicher in ein `string`-Objekt abrufen, werden die Daten automatisch in UTF-16 konvertiert.</span><span class="sxs-lookup"><span data-stu-id="eb16b-104">When you bring data from storage into a `string` object, the data is automatically converted to UTF-16.</span></span> <span data-ttu-id="eb16b-105">Falls die Daten lediglich ASCII-Werte von 0 bis 127 enthalten, ist für die Konvertierung kein zusätzlicher Aufwand erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eb16b-105">If the data contains only ASCII values from 0 through 127, the conversion requires no extra effort on your part.</span></span> <span data-ttu-id="eb16b-106">Falls der Quelltext jedoch erweiterte ASCII-Bytewerte (128 bis 255) enthält, werden die erweiterten Zeichen standardmäßig entsprechend der aktuellen Codeseite interpretiert.</span><span class="sxs-lookup"><span data-stu-id="eb16b-106">However, if the source text contains extended ASCII byte values (128 through 255), the extended characters will be interpreted by default according to the current code page.</span></span> <span data-ttu-id="eb16b-107">Um festzulegen, dass der Quelltext entsprechend einer anderen Codeseite interpretiert werden soll, verwenden Sie wie im folgenden Beispiel dargestellt die Klasse <xref:System.Text.Encoding?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="eb16b-107">To specify that the source text should be interpreted according to a different code page, use the <xref:System.Text.Encoding?displayProperty=fullName> class as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb16b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb16b-108">Example</span></span>  
 <span data-ttu-id="eb16b-109">Im folgenden Beispiel wird dargestellt, wie eine Textdatei, die in 8-Bit-ASCII codiert wurde, konvertiert und der Quelltext entsprechend der Windows-Codepage 737 interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="eb16b-109">The following example shows how to convert a text file that has been encoded in 8-bit ASCII, interpreting the source text according to Windows Code Page 737.</span></span>  
  
 <span data-ttu-id="eb16b-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb16b-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb16b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb16b-111">See Also</span></span>  
 [<span data-ttu-id="eb16b-112">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="eb16b-112">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

