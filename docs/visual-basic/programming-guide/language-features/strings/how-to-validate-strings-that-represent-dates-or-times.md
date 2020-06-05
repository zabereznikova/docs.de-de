---
title: 'Vorgehensweise: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5d153ac29039375386b3cd5f03609b1e4bd1d5bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410566"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="4d7da-102">Gewusst wie: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d7da-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="4d7da-103">Im folgenden Codebeispiel wird ein `Boolean` Wert festgelegt, der angibt, ob eine Zeichenfolge ein gültiges Datum oder eine gültige Uhrzeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="4d7da-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d7da-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d7da-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="4d7da-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4d7da-105">Compile the code</span></span>  
 <span data-ttu-id="4d7da-106">Ersetzen `("01/01/03")` `"9:30 PM"` Sie und durch das Datum und die Uhrzeit, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="4d7da-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="4d7da-107">Sie können die Zeichenfolge durch eine andere hart codierte Zeichenfolge, durch eine `String` Variable oder durch eine Methode ersetzen, die eine Zeichenfolge zurückgibt, wie z `InputBox` . b..</span><span class="sxs-lookup"><span data-stu-id="4d7da-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4d7da-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="4d7da-108">Robust Programming</span></span>  
 <span data-ttu-id="4d7da-109">Verwenden Sie diese Methode, um die Zeichenfolge zu validieren, bevor Sie versuchen, in `String` eine Variable zu konvertieren `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="4d7da-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="4d7da-110">Wenn Sie das Datum oder die Uhrzeit zuerst überprüfen, können Sie verhindern, dass zur Laufzeit eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4d7da-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7da-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d7da-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="4d7da-112">Überprüfen von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d7da-112">Validating Strings in Visual Basic</span></span>](validating-strings.md)
