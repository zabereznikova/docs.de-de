---
title: 'Gewusst wie: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 411c8517783421b2472c3e4aa77287f8252f179b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647861"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="468c1-102">Gewusst wie: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="468c1-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="468c1-103">Im folgenden Codebeispiel wird eine `Boolean` -Wert, der angibt, ob eine Zeichenfolge ein gültiges Datum oder Uhrzeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="468c1-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="468c1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="468c1-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="468c1-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="468c1-105">Compiling the Code</span></span>  
 <span data-ttu-id="468c1-106">Ersetzen Sie `("01/01/03")` und `"9:30 PM"` mit Datum und Uhrzeit, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="468c1-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="468c1-107">Können Sie die Zeichenfolge mit einer anderen hartcodierte Zeichenfolge durch Ersetzen einer `String` -Variable ist, oder mit einer Methode, die eine Zeichenfolge zurückgibt, z. B. `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="468c1-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="468c1-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="468c1-108">Robust Programming</span></span>  
 <span data-ttu-id="468c1-109">Mit dieser Methode können Sie um die Zeichenfolge zu überprüfen, bevor Sie versuchen, konvertieren die `String` zu einem `DateTime` Variable.</span><span class="sxs-lookup"><span data-stu-id="468c1-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="468c1-110">Überprüfen Sie zunächst die Datums- oder Zeitangabe, können Sie vermeiden, zur Laufzeit eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="468c1-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="468c1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="468c1-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [<span data-ttu-id="468c1-112">Überprüfen von Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="468c1-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
