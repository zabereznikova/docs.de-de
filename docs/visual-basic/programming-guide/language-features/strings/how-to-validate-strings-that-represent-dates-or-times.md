---
title: 'Vorgehensweise: Überprüfen von Zeichenfolgen, Datumsangaben oder Uhrzeiten darstellen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 1a838d9d156ad9c05a70a4d4d72db1a288731c9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685398"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="ec7b7-102">Vorgehensweise: Überprüfen von Zeichenfolgen, Datumsangaben oder Uhrzeiten darstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec7b7-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="ec7b7-103">Im folgenden Codebeispiel wird eine `Boolean` Wert, der angibt, ob eine Zeichenfolge ein gültiger Datums- oder Zeitwert darstellt.</span><span class="sxs-lookup"><span data-stu-id="ec7b7-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec7b7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec7b7-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ec7b7-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ec7b7-105">Compiling the Code</span></span>  
 <span data-ttu-id="ec7b7-106">Ersetzen Sie dies `("01/01/03")` und `"9:30 PM"` mit Datum und Uhrzeit, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="ec7b7-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="ec7b7-107">Können Sie die Zeichenfolge mit einer anderen Zeichenfolge, die hartcodiert und durch Ersetzen einer `String` Variablen, oder mit einer Methode, die eine Zeichenfolge zurückgibt, z. B. `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="ec7b7-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ec7b7-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="ec7b7-108">Robust Programming</span></span>  
 <span data-ttu-id="ec7b7-109">Mit dieser Methode können Sie um die Zeichenfolge zu überprüfen, bevor Sie versuchen, konvertieren die `String` zu einem `DateTime` Variable.</span><span class="sxs-lookup"><span data-stu-id="ec7b7-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="ec7b7-110">Überprüfen Sie zuerst das Datum oder Uhrzeit, können Sie vermeiden, zur Laufzeit eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="ec7b7-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7b7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec7b7-111">See also</span></span>
- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="ec7b7-112">Überprüfen von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec7b7-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
