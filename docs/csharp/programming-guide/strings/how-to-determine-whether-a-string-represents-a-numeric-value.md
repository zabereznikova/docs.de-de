---
title: 'Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie bestimmen, ob eine Zeichenfolge eine gültige Darstellung eines angegebenen numerischen Typs ist. Hier finden Sie Codebeispiele und weitere Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: c248c6c54de493ab06a833fc525252fa812d60da
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381748"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="40034-104">Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="40034-104">How to determine whether a string represents a numeric value (C# Programming Guide)</span></span>
<span data-ttu-id="40034-105">Verwenden Sie die statische `TryParse`-Methode, die von allen primitiven numerischen Typen sowie von Typen wie z.B. <xref:System.DateTime> und <xref:System.Net.IPAddress> implementiert wird, um zu bestimmen, ob eine Zeichenfolge eine gültige Darstellung eines angegebenen numerischen Typs ist.</span><span class="sxs-lookup"><span data-stu-id="40034-105">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="40034-106">In folgendem Beispiel wird gezeigt, wie Sie bestimmen können, ob „108“ eine zulässige [ganze Zahl](../../language-reference/builtin-types/integral-numeric-types.md) ist.</span><span class="sxs-lookup"><span data-stu-id="40034-106">The following example shows how to determine whether "108" is a valid [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
```csharp  
int i = 0;
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="40034-107">Wenn die Zeichenfolge nicht numerische Zeichen enthält oder der numerische Wert für den Typ, den Sie angegeben haben, zu groß oder zu klein ist, gibt `TryParse` „FALSE“ zurück und legt den Parameter auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="40034-107">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="40034-108">Andernfalls wird „TRUE“ zurückgegeben und der Parameter auf den numerischen Wert der Zeichenfolge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="40034-108">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40034-109">Eine Zeichenfolge kann auch nur numerische Zeichen enthalten und trotzdem für den Typ unzulässig sein, dessen `TryParse`-Methode Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="40034-109">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="40034-110">Beispielsweise ist „256“ kein zulässiger Wert für `byte`, aber zulässig für `int`.</span><span class="sxs-lookup"><span data-stu-id="40034-110">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="40034-111">„98,6“ ist kein zulässiger Wert für `int`, aber zulässig für `decimal`.</span><span class="sxs-lookup"><span data-stu-id="40034-111">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40034-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40034-112">Example</span></span>  
 <span data-ttu-id="40034-113">In folgendem Beispiel wird gezeigt, wie Sie `TryParse` mit einer Zeichenfolgenrepräsentation von den Werten `long`, `byte` und `decimal` verwenden können.</span><span class="sxs-lookup"><span data-stu-id="40034-113">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a><span data-ttu-id="40034-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="40034-114">Robust Programming</span></span>  
 <span data-ttu-id="40034-115">Primitive numerische Typen implementieren auch die statische `Parse`-Methode, die eine Ausnahme auslöst, wenn die Zeichenfolge keine zulässige Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="40034-115">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="40034-116">`TryParse` ist für gewöhnlich effizienter, da es einfach „FALSE“ zurückgibt, wenn die Zahl unzulässig ist.</span><span class="sxs-lookup"><span data-stu-id="40034-116">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="40034-117">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="40034-117">.NET Security</span></span>  
 <span data-ttu-id="40034-118">Verwenden Sie immer die Methoden `TryParse` oder `Parse`, um Benutzereingaben von Steuerelementen wie Text- oder Kombinationsfeldern zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="40034-118">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40034-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40034-119">See also</span></span>

- [<span data-ttu-id="40034-120">Konvertieren eines Bytearrays in einen Typ „int“</span><span class="sxs-lookup"><span data-stu-id="40034-120">How to convert a byte array to an int</span></span>](../types/how-to-convert-a-byte-array-to-an-int.md)
- [<span data-ttu-id="40034-121">Konvertieren einer Zeichenfolge in eine Zahl</span><span class="sxs-lookup"><span data-stu-id="40034-121">How to convert a string to a number</span></span>](../types/how-to-convert-a-string-to-a-number.md)
- [<span data-ttu-id="40034-122">Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="40034-122">How to convert between hexadecimal strings and numeric types</span></span>](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [<span data-ttu-id="40034-123">Verarbeiten numerischer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="40034-123">Parsing Numeric Strings</span></span>](../../../standard/base-types/parsing-numeric.md)
- [<span data-ttu-id="40034-124">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="40034-124">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
