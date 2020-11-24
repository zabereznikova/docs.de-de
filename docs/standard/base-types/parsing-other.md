---
title: Analysieren anderer Zeichenfolgen in .NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
ms.openlocfilehash: 791ee37ff5f679d47492fc3cfdb61530bf570a36
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823991"
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="4774d-102">Analysieren anderer Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="4774d-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="4774d-103">Neben den numerischen und den <xref:System.DateTime>-Zeichenfolgen können Sie auch Zeichenfolgen in Datentypen analysieren, die die Typen <xref:System.Char>, <xref:System.Boolean> und <xref:System.Enum> darstellen.</span><span class="sxs-lookup"><span data-stu-id="4774d-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="4774d-104">Char</span><span class="sxs-lookup"><span data-stu-id="4774d-104">Char</span></span>  
 <span data-ttu-id="4774d-105">Die statische Parse-Methode, die dem **Char**-Datentyp zugeordnet ist, eignet sich zum Konvertieren einer Zeichenfolge mit einem einzigen Zeichen in den entsprechenden Unicode-Wert.</span><span class="sxs-lookup"><span data-stu-id="4774d-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="4774d-106">Im folgenden Codebeispiel wird eine Zeichenfolge in ein Unicode-Zeichen analysiert.</span><span class="sxs-lookup"><span data-stu-id="4774d-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="4774d-107">Boolesch</span><span class="sxs-lookup"><span data-stu-id="4774d-107">Boolean</span></span>  
 <span data-ttu-id="4774d-108">Der **Boolean**-Datentyp enthält eine **Parse**-Methode, mit der Sie eine Zeichenfolge, die einen **-Wert darstellt, in einen tatsächlichen** -Typ konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="4774d-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="4774d-109">Diese Methode ist von der Groß-/Kleinschreibung unabhängig und kann erfolgreich eine Zeichenfolge mit „True“ oder „False“ analysieren.</span><span class="sxs-lookup"><span data-stu-id="4774d-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="4774d-110">Die dem **Boolean**-Typ zugeordnete **Parse**-Methode kann auch Zeichenfolgen analysieren, die von Leerzeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="4774d-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="4774d-111">Wenn eine beliebige andere Zeichenfolge übergeben wird, wird eine <xref:System.FormatException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="4774d-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="4774d-112">Im folgenden Codebeispiel wird die **Parse**-Methode zum Konvertieren einer Zeichenfolge in einen Boolean-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="4774d-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="4774d-113">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4774d-113">Enumeration</span></span>  
 <span data-ttu-id="4774d-114">Mit der statischen **Parse**-Methode können Sie einen Enumerationstyp auf den Wert einer Zeichenfolge initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4774d-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="4774d-115">Diese Methode akzeptiert den zu analysierenden Enumerationstyp, die zu analysierende Zeichenfolge und ein optionales Boolean-Flag, das angibt, ob bei der Analyse die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="4774d-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="4774d-116">Die zu analysierende Zeichenfolge kann mehrere durch Kommas voneinander getrennte Werte enthalten, denen ein oder mehrere Leerzeichen (auch als Leerräume bezeichnet) voran- oder nachgestellt sein können.</span><span class="sxs-lookup"><span data-stu-id="4774d-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="4774d-117">Wenn die Zeichenfolge mehrere Werte enthält, entspricht der Wert des zurückgegebenen Objekts dem Wert aller angegebenen Werte, kombiniert mit einem bitweisen OR-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="4774d-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="4774d-118">Im folgenden Beispiel wird die **Parse**-Methode zum Konvertieren einer Zeichenfolgendarstellung in einen Enumerationswert verwendet.</span><span class="sxs-lookup"><span data-stu-id="4774d-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="4774d-119">Die <xref:System.DayOfWeek>-Enumeration wird über eine Zeichenfolge mit **Donnerstag** initialisiert.</span><span class="sxs-lookup"><span data-stu-id="4774d-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4774d-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4774d-120">See also</span></span>

- [<span data-ttu-id="4774d-121">Analysieren von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4774d-121">Parsing Strings</span></span>](parsing-strings.md)
- [<span data-ttu-id="4774d-122">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="4774d-122">Formatting Types</span></span>](formatting-types.md)
- [<span data-ttu-id="4774d-123">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="4774d-123">Type Conversion in the .NET</span></span>](type-conversion.md)
