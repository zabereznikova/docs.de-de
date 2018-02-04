---
title: 'Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)'
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: petrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: c35ac615e3f87710f934a1cf66e6546625298bd0
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="9d3b1-102">Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d3b1-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="9d3b1-103">In diesem Beispiel konvertiert eine hexadezimale Zeichenfolge in eine ganze Zahl mit der <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="9d3b1-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="9d3b1-104">Um eine hexadezimale Zeichenfolge in eine Zahl zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9d3b1-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="9d3b1-105">Verwenden der <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode, um die Anzahl, ausgedrückt in Base-16 in eine ganze Zahl zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9d3b1-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="9d3b1-106">Das erste Argument der <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode ist die zu konvertierende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9d3b1-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="9d3b1-107">Das zweite Argument wird beschrieben, welche Basis der Zahl ausgedrückt ist; hexadezimale Basis 16 ist.</span><span class="sxs-lookup"><span data-stu-id="9d3b1-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- <span data-ttu-id="9d3b1-108">Beachten Sie, dass die hexadezimale Zeichenfolge die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="9d3b1-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="9d3b1-109">Es darf keine enthalten die `&h` Präfix.</span><span class="sxs-lookup"><span data-stu-id="9d3b1-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="9d3b1-110">Es darf keine enthalten die `_` Ziffer Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="9d3b1-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="9d3b1-111">Wenn das Präfix oder ein Ziffer Trennzeichen vorhanden ist, den Aufruf der <xref:System.Convert.ToInt32(System.String,System.Int32)> -Methode löst eine <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="9d3b1-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d3b1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d3b1-112">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
