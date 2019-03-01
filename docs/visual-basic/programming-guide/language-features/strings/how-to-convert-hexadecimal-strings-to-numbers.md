---
title: 'Vorgehensweise: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: c8ef615b6874642fa9ad1b22fe9d7f7745d4ffde
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201000"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="c5b10-102">Vorgehensweise: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5b10-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="c5b10-103">In diesem Beispiel wird eine hexadezimale Zeichenfolge konvertiert, um eine ganze Zahl mit dem <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="c5b10-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="c5b10-104">Zum Konvertieren einer hexadezimalen Zeichenfolge in eine Zahl</span><span class="sxs-lookup"><span data-stu-id="c5b10-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="c5b10-105">Verwenden der <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode, um die Anzahl, ausgedrückt in Base-16 in eine ganze Zahl zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c5b10-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="c5b10-106">Das erste Argument von der <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode ist die zu konvertierende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c5b10-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="c5b10-107">Das zweite Argument wird beschrieben, welche Basis der Zahl ausgedrückt wird; hexadezimale Basis 16 ist.</span><span class="sxs-lookup"><span data-stu-id="c5b10-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]  

- <span data-ttu-id="c5b10-108">Beachten Sie, dass die hexadezimale Zeichenfolge die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="c5b10-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="c5b10-109">Es darf keine enthalten die `&h` Präfix.</span><span class="sxs-lookup"><span data-stu-id="c5b10-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="c5b10-110">Es darf keine enthalten die `_` Zifferntrennzeichen.</span><span class="sxs-lookup"><span data-stu-id="c5b10-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="c5b10-111">Wenn das Präfix oder Zifferntrennzeichen vorhanden ist, den Aufruf der <xref:System.Convert.ToInt32(System.String,System.Int32)> -Methode löst eine <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="c5b10-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5b10-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5b10-112">See also</span></span>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
