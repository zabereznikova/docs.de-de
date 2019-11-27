---
title: 'Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347174"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="2da8f-102">Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2da8f-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>

<span data-ttu-id="2da8f-103">In diesem Beispiel wird eine hexadezimale Zeichenfolge mithilfe der <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>-Methode in eine ganze Zahl konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2da8f-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="2da8f-104">So konvertieren Sie eine hexadezimale Zeichenfolge in eine Zahl</span><span class="sxs-lookup"><span data-stu-id="2da8f-104">To convert a hexadecimal string to a number</span></span>

- <span data-ttu-id="2da8f-105">Verwenden Sie die <xref:System.Convert.ToInt32(System.String,System.Int32)>-Methode, um die in Base-16 ausgedrückte Zahl in eine ganze Zahl zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2da8f-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>

  <span data-ttu-id="2da8f-106">Das erste Argument der <xref:System.Convert.ToInt32(System.String,System.Int32)>-Methode ist die Zeichenfolge, die konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2da8f-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="2da8f-107">Das zweite Argument beschreibt die Basis, in der die Zahl ausgedrückt wird. Hexadezimalwert ist Basis 16.</span><span class="sxs-lookup"><span data-stu-id="2da8f-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- <span data-ttu-id="2da8f-108">Beachten Sie, dass für die hexadezimale Zeichenfolge die folgenden Einschränkungen gelten:</span><span class="sxs-lookup"><span data-stu-id="2da8f-108">Note that the hexadecimal string has the following restrictions:</span></span>

  - <span data-ttu-id="2da8f-109">Das `&h` Präfix darf nicht enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2da8f-109">It cannot include the `&h` prefix.</span></span>
  - <span data-ttu-id="2da8f-110">Das `_` Ziffern Trennzeichen kann nicht enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="2da8f-110">It cannot include the `_` digit separator.</span></span>

  <span data-ttu-id="2da8f-111">Wenn das Präfix oder ein Ziffern Trennzeichen vorhanden ist, löst der aufzurufende <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode eine <xref:System.FormatException>aus.</span><span class="sxs-lookup"><span data-stu-id="2da8f-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="2da8f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2da8f-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
