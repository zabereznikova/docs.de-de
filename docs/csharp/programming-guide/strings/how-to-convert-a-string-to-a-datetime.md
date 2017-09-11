---
title: 'Gewusst wie: Konvertieren einer Zeichenfolge in einen DateTime-Wert (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], converting to DateTIme
ms.assetid: 88abef11-3a06-4b49-8dd2-61ed0e876fc3
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 15ef1ec4debf242cdabc42f26add890bd4b61507
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-a-string-to-a-datetime-c-programming-guide"></a><span data-ttu-id="b1643-102">Gewusst wie: Konvertieren einer Zeichenfolge in einen DateTime-Wert (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b1643-102">How to: Convert a String to a DateTime (C# Programming Guide)</span></span>
<span data-ttu-id="b1643-103">Es ist in Programmen üblich, Benutzern die Eingabe von Datumsangaben als Zeichenfolgenwerte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b1643-103">It is common for programs to enable users to enter dates as string values.</span></span> <span data-ttu-id="b1643-104">Um ein zeichenfolgenbasiertes Datum in ein <xref:System.DateTime?displayProperty=fullName> -Objekt zu konvertieren, können Sie die <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName> -Methode oder die statische <xref:System.DateTime.Parse%28System.String%29?displayProperty=fullName> -Methode verwenden, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b1643-104">To convert a string-based date to a <xref:System.DateTime?displayProperty=fullName> object, you can use the <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName> method or the <xref:System.DateTime.Parse%28System.String%29?displayProperty=fullName> static method, as shown in the following example.</span></span>  
  
 <span data-ttu-id="b1643-105">**Kultur**.</span><span class="sxs-lookup"><span data-stu-id="b1643-105">**Culture**.</span></span>  <span data-ttu-id="b1643-106">Datumsangaben werden weltweit je nach Kultur unterschiedlich geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1643-106">Different cultures in the world write date strings in different ways.</span></span>  <span data-ttu-id="b1643-107">In den USA entspricht 01/20/2008 z. B. dem 20. Januar 2008.</span><span class="sxs-lookup"><span data-stu-id="b1643-107">For example, in the US 01/20/2008 is January 20th, 2008.</span></span>  <span data-ttu-id="b1643-108">In Frankreich wird dadurch eine InvalidFormatException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b1643-108">In France this will throw an InvalidFormatException.</span></span> <span data-ttu-id="b1643-109">Dies liegt daran, dass Datumsangaben in Frankreich als Tag/Monat/Jahr und in den USA als Monat/Tag/Jahr gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="b1643-109">This is because France reads date-times as Day/Month/Year, and in the US it is Month/Day/Year.</span></span>  
  
 <span data-ttu-id="b1643-110">Daher wird eine Zeichenfolge wie 20/01/2008 in Frankreich als 20. Januar 2008 interpretiert, während sie in den USA eine InvalidFormatException auslöst.</span><span class="sxs-lookup"><span data-stu-id="b1643-110">Consequently, a string like 20/01/2008 will parse to January 20th, 2008 in France, and then throw an InvalidFormatException in the US.</span></span>  
  
 <span data-ttu-id="b1643-111">Zum Ermitteln der aktuellen Kultureinstellungen können Sie System.Globalization.CultureInfo.CurrentCulture verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1643-111">To determine your current culture settings, you can use System.Globalization.CultureInfo.CurrentCulture.</span></span>  
  
 <span data-ttu-id="b1643-112">Im Folgenden finden Sie ein einfaches Beispiel für das Konvertieren einer Zeichenfolge in dateTime.</span><span class="sxs-lookup"><span data-stu-id="b1643-112">See the example below for a simple example of converting a string to dateTime.</span></span>  
  
 <span data-ttu-id="b1643-113">Weitere Beispiele für Datumszeichenfolgen finden Sie unter <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b1643-113">For more examples of date strings, see <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName>.</span></span>  
  
```csharp  
string dateTime = "01/08/2008 14:50:50.42";  
            DateTime dt = Convert.ToDateTime(dateTime);  
            Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}",  
                              dt.Year, dt.Month, dt.Day, dt.Hour, dt.Minute, dt.Second, dt.Millisecond);  
            // Specify exactly how to interpret the string.  
            IFormatProvider culture = new System.Globalization.CultureInfo("fr-FR", true);  
  
            // Alternate choice: If the string has been input by an end user, you might    
            // want to format it according to the current culture:   
            // IFormatProvider culture = System.Threading.Thread.CurrentThread.CurrentCulture;  
            DateTime dt2 = DateTime.Parse(dateTime, culture, System.Globalization.DateTimeStyles.AssumeLocal);  
            Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}",  
                              dt2.Year, dt2.Month, dt2.Day, dt2.Hour, dt2.Minute, dt2.Second, dt2.Millisecond  
/* Output (assuming first culture is en-US and second is fr-FR):  
    Year: 2008, Month: 1, Day: 8, Hour: 14, Minute: 50, Second: 50, Millisecond: 420  
Year: 2008, Month: 8, Day: 1, Hour: 14, Minute: 50, Second: 50, Millisecond: 420  
Press any key to continue . . .  
 */  
```  
  
## <a name="example"></a><span data-ttu-id="b1643-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1643-114">Example</span></span>  
 <span data-ttu-id="b1643-115">[!code-cs[csProgGuideStrings#13](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-a-string-to-a-datetime_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b1643-115">[!code-cs[csProgGuideStrings#13](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-a-string-to-a-datetime_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1643-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1643-116">See Also</span></span>  
 [<span data-ttu-id="b1643-117">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b1643-117">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

