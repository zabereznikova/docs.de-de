---
title: Analysieren anderer Zeichenfolgen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="f36ca-102">Analysieren anderer Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="f36ca-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="f36ca-103">Zusätzlich zu den numerischen und <xref:System.DateTime> Zeichenfolgen, Sie können auch Analysieren von Zeichenfolgen, die die Typen darstellen <xref:System.Char>, <xref:System.Boolean>, und <xref:System.Enum> in Datentypen.</span><span class="sxs-lookup"><span data-stu-id="f36ca-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="f36ca-104">Char</span><span class="sxs-lookup"><span data-stu-id="f36ca-104">Char</span></span>  
 <span data-ttu-id="f36ca-105">Die statische Parse-Methode, die dem **Char**-Datentyp zugeordnet ist, eignet sich zum Konvertieren einer Zeichenfolge mit einem einzigen Zeichen in den entsprechenden Unicode-Wert.</span><span class="sxs-lookup"><span data-stu-id="f36ca-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="f36ca-106">Im folgenden Codebeispiel wird eine Zeichenfolge in ein Unicode-Zeichen analysiert.</span><span class="sxs-lookup"><span data-stu-id="f36ca-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="f36ca-107">Boolesch</span><span class="sxs-lookup"><span data-stu-id="f36ca-107">Boolean</span></span>  
 <span data-ttu-id="f36ca-108">Die **booleschen** -Datentyp enthält eine **analysieren** -Methode, die Sie verwenden können, um eine Zeichenfolge zu konvertieren, die einen booleschen Wert in einen tatsächlichen darstellt **booleschen** Typ.</span><span class="sxs-lookup"><span data-stu-id="f36ca-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="f36ca-109">Diese Methode ist von der Groß-/Kleinschreibung unabhängig und kann erfolgreich eine Zeichenfolge mit „True“ oder „False“ analysieren.</span><span class="sxs-lookup"><span data-stu-id="f36ca-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="f36ca-110">Die **analysieren** zugeordnete Methode der **booleschen** Typ kann auch Analysieren von Zeichenfolgen, die durch Leerzeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="f36ca-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="f36ca-111">Wenn eine andere Zeichenfolge übergeben wird, eine <xref:System.FormatException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f36ca-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="f36ca-112">Im folgenden Codebeispiel wird mit der **analysieren** Methode zum Konvertieren einer Zeichenfolge in einen booleschen Wert.</span><span class="sxs-lookup"><span data-stu-id="f36ca-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="f36ca-113">Enumeration</span><span class="sxs-lookup"><span data-stu-id="f36ca-113">Enumeration</span></span>  
 <span data-ttu-id="f36ca-114">Mit der statischen **Parse**-Methode können Sie einen Enumerationstyp auf den Wert einer Zeichenfolge initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f36ca-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="f36ca-115">Diese Methode akzeptiert der Enumerationstyp, den Sie analysieren, die zu analysierende Zeichenfolge und ein optionales boolesches Flag, der angibt, ob die Analyse Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="f36ca-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="f36ca-116">Die zu analysierende Zeichenfolge kann mehrere durch Kommas voneinander getrennte Werte enthalten, denen ein oder mehrere Leerzeichen (auch als Leerräume bezeichnet) voran- oder nachgestellt sein können.</span><span class="sxs-lookup"><span data-stu-id="f36ca-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="f36ca-117">Wenn die Zeichenfolge mehrere Werte enthält, entspricht der Wert des zurückgegebenen Objekts dem Wert aller angegebenen Werte, kombiniert mit einem bitweisen OR-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="f36ca-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="f36ca-118">Im folgenden Beispiel wird die **analysieren** Methode, um eine Zeichenfolgendarstellung in einen Enumerationswert zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f36ca-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="f36ca-119">Die <xref:System.DayOfWeek> Enumeration wird mit initialisiert **Donnerstag** aus einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f36ca-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f36ca-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f36ca-120">See Also</span></span>  
 [<span data-ttu-id="f36ca-121">Analysieren von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f36ca-121">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 [<span data-ttu-id="f36ca-122">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="f36ca-122">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 [<span data-ttu-id="f36ca-123">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="f36ca-123">Type Conversion in the .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
