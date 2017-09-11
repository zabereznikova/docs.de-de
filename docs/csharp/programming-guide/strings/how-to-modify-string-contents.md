---
title: "Gewusst wie: Ändern von Zeichenfolgeninhalten (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
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
ms.openlocfilehash: 114b6fdabd235d7e57947e77b672352e28aff11e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-modify-string-contents-c-programming-guide"></a><span data-ttu-id="04aa4-102">Gewusst wie: Ändern von Zeichenfolgeninhalten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="04aa4-102">How to: Modify String Contents (C# Programming Guide)</span></span>
<span data-ttu-id="04aa4-103">Da Zeichenfolgen *unveränderlich* sind, ist es nicht möglich (ohne unsicheren Code zu verwenden), den Wert eines Zeichenfolgenobjekts zu verändern, nachdem es erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="04aa4-103">Because strings are *immutable*, it is not possible (without using unsafe code) to modify the value of a string object after it has been created.</span></span> <span data-ttu-id="04aa4-104">Es gibt jedoch viele Möglichkeiten, den Wert einer Zeichenfolge zu ändern und das Ergebnis in einem neuen Zeichenfolgenobjekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="04aa4-104">However, there are many ways to modify the value of a string and store the result in a new string object.</span></span> <span data-ttu-id="04aa4-105">Die <xref:System.String?displayProperty=fullName>-Klasse enthält Methoden, die eine Eingabezeichenfolge verarbeiten und ein neues Zeichenfolgenobjekt zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="04aa4-105">The <xref:System.String?displayProperty=fullName> class provides methods that operate on an input string and return a new string object.</span></span> <span data-ttu-id="04aa4-106">In vielen Fällen können Sie das neue Objekt der Variablen zuweisen, die die ursprüngliche Zeichenfolge enthalten hat.</span><span class="sxs-lookup"><span data-stu-id="04aa4-106">In many cases, you can assign the new object to the variable that held the original string.</span></span> <span data-ttu-id="04aa4-107">Die <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>-Klasse stellt zusätzliche Methoden bereit, die auf ähnliche Weise funktionieren.</span><span class="sxs-lookup"><span data-stu-id="04aa4-107">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class provides additional methods that work in a similar manner.</span></span> <span data-ttu-id="04aa4-108">Die <xref:System.Text.StringBuilder?displayProperty=fullName>-Klasse stellt einen Puffer aus Zeichen bereit, die Sie „direkt“ ändern können.</span><span class="sxs-lookup"><span data-stu-id="04aa4-108">The <xref:System.Text.StringBuilder?displayProperty=fullName> class provides a character buffer that you can modify "in-place."</span></span> <span data-ttu-id="04aa4-109">Sie rufen die <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName>-Methode auf, um ein neues Zeichenfolgenobjekt zu erstellen, das die aktuellen Inhalte des Puffers enthält.</span><span class="sxs-lookup"><span data-stu-id="04aa4-109">You call the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> method to create a new string object that contains the current contents of the buffer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04aa4-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04aa4-110">Example</span></span>  
 <span data-ttu-id="04aa4-111">Das folgende Beispiel zeigt verschiedene Möglichkeiten, eine Teilzeichenfolgen in einer angegebenen Zeichenfolge zu ersetzen oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="04aa4-111">The following example shows various ways to replace or remove substrings in a specified string.</span></span>  
  
 <span data-ttu-id="04aa4-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="04aa4-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="04aa4-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04aa4-113">Example</span></span>  
 <span data-ttu-id="04aa4-114">Um auf die einzelnen Zeichen in einer Zeichenfolge mithilfe der Arraynotation zuzugreifen, können Sie das <xref:System.Text.StringBuilder>-Objekt verwenden, das den `[]`-Operator für den Zugriff auf den internen Zeichenpuffer überlädt.</span><span class="sxs-lookup"><span data-stu-id="04aa4-114">To access the individual characters in a string by using array notation, you can use the <xref:System.Text.StringBuilder> object, which overloads the `[]` operator to provide access to its internal character buffer.</span></span> <span data-ttu-id="04aa4-115">Sie können auch die Zeichenfolge mithilfe der <xref:System.String.ToCharArray%2A>-Methode in ein Array von Zeichen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="04aa4-115">You can also convert the string to an array of chars by using the <xref:System.String.ToCharArray%2A> method.</span></span> <span data-ttu-id="04aa4-116">Im folgenden Beispiel wird `ToCharArray` zum Erstellen des Arrays verwendet.</span><span class="sxs-lookup"><span data-stu-id="04aa4-116">The following example uses `ToCharArray` to create the array.</span></span> <span data-ttu-id="04aa4-117">Einige Elemente dieses Arrays werden dann geändert.</span><span class="sxs-lookup"><span data-stu-id="04aa4-117">Some elements of this array are then modified.</span></span> <span data-ttu-id="04aa4-118">Ein Zeichenfolgenkonstruktor, der ein char-Array als Eingabeparameter verwendet, wird dann zum Erstellen einer neuen Zeichenfolge aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="04aa4-118">A string constructor that takes a char array as an input parameter is then called to create a new string.</span></span>  
  
 <span data-ttu-id="04aa4-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="04aa4-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="04aa4-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04aa4-120">Example</span></span>  
 <span data-ttu-id="04aa4-121">Das folgende Beispiel wird für diese seltenen Fälle bereitgestellt, in denen Sie eine Zeichenfolge direkt verändern sollen, indem Sie einen unsicheren Code auf ähnliche Weise wie char-Array in C verwenden.</span><span class="sxs-lookup"><span data-stu-id="04aa4-121">The following example is provided for those very rare situations in which you may want to modify a string in-place by using unsafe code in a manner similar to C-style char arrays.</span></span> <span data-ttu-id="04aa4-122">Das Beispiel zeigt, wie Sie auf die einzelnen Zeichen „direkt“ mithilfe des festgelegten Schlüsselworts zugreifen.</span><span class="sxs-lookup"><span data-stu-id="04aa4-122">The example shows how to access the individual characters "in-place" by using the fixed keyword.</span></span> <span data-ttu-id="04aa4-123">Darüber hinaus wird ein möglicher Nebeneffekt unsicherer Vorgänge auf Zeichenfolgen gezeigt, die daraus entstehen, dass der C#-Compiler Zeichenfolgen intern speichert (hält).</span><span class="sxs-lookup"><span data-stu-id="04aa4-123">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="04aa4-124">Im Allgemeinen sollten Sie dieses Verfahren nicht verwenden, es sei denn, es ist unbedingt notwendig.</span><span class="sxs-lookup"><span data-stu-id="04aa4-124">In general, you should not use this technique unless it is absolutely necessary.</span></span>  
  
 <span data-ttu-id="04aa4-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="04aa4-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04aa4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04aa4-126">See Also</span></span>  
 <span data-ttu-id="04aa4-127">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="04aa4-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="04aa4-128">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="04aa4-128">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

