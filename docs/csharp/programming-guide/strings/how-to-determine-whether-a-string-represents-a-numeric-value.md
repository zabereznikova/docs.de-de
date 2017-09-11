---
title: 'Gewusst wie: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: 9
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
ms.openlocfilehash: d2f89f4a4771625389a04f5c92829c91d66eb207
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="b06cb-102">Gewusst wie: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b06cb-102">How to: Determine Whether a String Represents a Numeric Value (C# Programming Guide)</span></span>
<span data-ttu-id="b06cb-103">Verwenden Sie die statische `TryParse`-Methode, die von allen primitiven numerischen Typen sowie von Typen wie z.B. <xref:System.DateTime> und <xref:System.Net.IPAddress> implementiert wird, um zu bestimmen, ob eine Zeichenfolge eine gültige Darstellung eines angegebenen numerischen Typs ist.</span><span class="sxs-lookup"><span data-stu-id="b06cb-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="b06cb-104">In folgendem Beispiel wird gezeigt, wie Sie bestimmen können, ob „108“ eine zulässige [ganze Zahl](../../../csharp/language-reference/keywords/int.md) ist.</span><span class="sxs-lookup"><span data-stu-id="b06cb-104">The following example shows how to determine whether "108" is a valid [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="b06cb-105">Wenn die Zeichenfolge nicht numerische Zeichen enthält oder der numerische Wert für den Typ, den Sie angegeben haben, zu groß oder zu klein ist, gibt `TryParse` „FALSE“ zurück und legt den Parameter auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="b06cb-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="b06cb-106">Andernfalls wird „TRUE“ zurückgegeben und der Parameter auf den numerischen Wert der Zeichenfolge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b06cb-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b06cb-107">Eine Zeichenfolge kann auch nur numerische Zeichen enthalten und trotzdem für den Typ unzulässig sein, dessen `TryParse`-Methode Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="b06cb-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="b06cb-108">Beispielsweise ist „256“ kein zulässiger Wert für `byte`, aber zulässig für `int`.</span><span class="sxs-lookup"><span data-stu-id="b06cb-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="b06cb-109">„98,6“ ist kein zulässiger Wert für `int`, aber zulässig für `decimal`.</span><span class="sxs-lookup"><span data-stu-id="b06cb-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b06cb-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b06cb-110">Example</span></span>  
 <span data-ttu-id="b06cb-111">In folgendem Beispiel wird gezeigt, wie Sie `TryParse` mit einer Zeichenfolgenrepräsentation von den Werten `long`, `byte` und `decimal` verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b06cb-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 <span data-ttu-id="b06cb-112">[!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b06cb-112">[!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b06cb-113">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b06cb-113">Robust Programming</span></span>  
 <span data-ttu-id="b06cb-114">Primitive numerische Typen implementieren auch die statische `Parse`-Methode, die eine Ausnahme auslöst, wenn die Zeichenfolge keine zulässige Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="b06cb-114">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="b06cb-115">`TryParse` ist für gewöhnlich effizienter, da es einfach „FALSE“ zurückgibt, wenn die Zahl unzulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b06cb-115">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b06cb-116">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b06cb-116">.NET Framework Security</span></span>  
 <span data-ttu-id="b06cb-117">Verwenden Sie immer die Methoden `TryParse` oder `Parse`, um Benutzereingaben von Steuerelementen wie Text- oder Kombinationsfeldern zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b06cb-117">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b06cb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b06cb-118">See Also</span></span>  
 <span data-ttu-id="b06cb-119">[Vorgehensweise Konvertieren eines Bytearrays in einen ganzzahligen Typ](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md) </span><span class="sxs-lookup"><span data-stu-id="b06cb-119">[How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md) </span></span>  
 <span data-ttu-id="b06cb-120">[Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) </span><span class="sxs-lookup"><span data-stu-id="b06cb-120">[How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) </span></span>  
 <span data-ttu-id="b06cb-121">[Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) </span><span class="sxs-lookup"><span data-stu-id="b06cb-121">[How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) </span></span>  
 <span data-ttu-id="b06cb-122">[Analysieren numerischer Zeichenfolgen](../../../standard/base-types/parsing-numeric.md) </span><span class="sxs-lookup"><span data-stu-id="b06cb-122">[Parsing Numeric Strings](../../../standard/base-types/parsing-numeric.md) </span></span>  
 [<span data-ttu-id="b06cb-123">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="b06cb-123">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

