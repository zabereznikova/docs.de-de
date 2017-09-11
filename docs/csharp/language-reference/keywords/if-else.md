---
title: if-else (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
dev_langs:
- CSharp
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
caps.latest.revision: 32
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
ms.openlocfilehash: 694761a9b03fadf2dff97e61e37c0af52658f9e4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="if-else-c-reference"></a><span data-ttu-id="a9438-102">if-else (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a9438-102">if-else (C# Reference)</span></span>
<span data-ttu-id="a9438-103">Eine `if` -Anweisung ermittelt, welche Anweisung basierend auf dem Wert eines `Boolean` Ausdrucks auszuführen ist.</span><span class="sxs-lookup"><span data-stu-id="a9438-103">An `if` statement identifies which statement to run based on the value of a `Boolean` expression.</span></span> <span data-ttu-id="a9438-104">Im folgenden Beispiel wird die `Boolean` Variable `result` auf `true` festgelegt und dann in der `if` Anweisung überprüft.</span><span class="sxs-lookup"><span data-stu-id="a9438-104">In the following example, the `Boolean` variable `result` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="a9438-105">Die Ausgabe lautet `The condition is true`.</span><span class="sxs-lookup"><span data-stu-id="a9438-105">The output is `The condition is true`.</span></span>  
  
 <span data-ttu-id="a9438-106">[!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9438-106">[!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]</span></span>  
  
 <span data-ttu-id="a9438-107">Die können die Beispiele in diesem Thema ausführen, indem Sie sie in die `Main` -Methode einer Konsolenanwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="a9438-107">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>  
  
 <span data-ttu-id="a9438-108">Eine `if` -Anweisung in C# kann zwei Formen annehmen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9438-108">An `if` statement in C# can take two forms, as the following example shows.</span></span>  
  
```csharp  
// if-else statement  
if (condition)  
{  
    then-statement;  
}  
else  
{  
    else-statement;  
}  
// Next statement in the program.  
  
// if statement without an else  
if (condition)  
{  
    then-statement;  
}  
// Next statement in the program.  
```  
  
 <span data-ttu-id="a9438-109">In einer `if-else` -Anweisung wird, wenn `condition` zu true ausgewertet wird, `then-statement` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9438-109">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="a9438-110">Wenn `condition` false ist, wird `else-statement` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9438-110">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="a9438-111">Da `condition` nicht gleichzeitig true und false sein kann, können `then-statement` und `else-statement` einer `if-else` -Anweisung niemals beide ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a9438-111">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="a9438-112">Nachdem `then-statement` oder `else-statement` ausgeführt wurde, wird die Steuerung an die `if` -Anweisung übergeben.</span><span class="sxs-lookup"><span data-stu-id="a9438-112">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="a9438-113">In einer `if` -Anweisung, die keine `else` -Anweisung enthält, wird, wenn `condition` true ist, `then-statement` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9438-113">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="a9438-114">Wenn `condition` false ist, wird die Steuerung an die nächste Anweisung nach der `if` Anweisung übergeben.</span><span class="sxs-lookup"><span data-stu-id="a9438-114">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="a9438-115">Sowohl `then-statement` als auch `else-statement` können aus einer einzelnen Anweisung oder mehreren in Klammern eingeschlossenen Anweisungen bestehen (`{}`).</span><span class="sxs-lookup"><span data-stu-id="a9438-115">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="a9438-116">Bei einer Anweisung sind die Klammern optional, sie werden aber empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a9438-116">For a single statement, the braces are optional but recommended.</span></span>  
  
 <span data-ttu-id="a9438-117">Die Anweisung bzw. die Anweisungen in `then-statement` und `else-statement` können von einer beliebigen Art sein und eine weitere `if` Anweisung enthalten, die in der ursprünglichen `if` -Anweisung geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="a9438-117">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="a9438-118">In geschachtelten `if` Anweisungen gehört jede `else` -Klausel zur letzten `if` -Anweisung, die nicht über eine zugehörige `else`-Anweisung verfügt.</span><span class="sxs-lookup"><span data-stu-id="a9438-118">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="a9438-119">Im folgenden Beispiel wird `Result1` angezeigt, wenn `m > 10` und `n > 20` zu true ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="a9438-119">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="a9438-120">Wenn `m > 10` true ist, `n > 20` hingegen false, wird `Result2` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9438-120">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>  
  
 <span data-ttu-id="a9438-121">[!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9438-121">[!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]</span></span>  
  
 <span data-ttu-id="a9438-122">Wenn stattdessen `Result2` angezeigt werden soll, wenn `(m > 10)` false ist, können Sie diese Zuordnung mithilfe von Klammern festlegen, um den Beginn und das Ende der geschachtelten `if` Anweisung anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9438-122">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>  
  
 <span data-ttu-id="a9438-123">[!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9438-123">[!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]</span></span>  
  
 <span data-ttu-id="a9438-124">`Result2` wird angezeigt, wenn die Bedingung `(m > 10)` als FALSE ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="a9438-124">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9438-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9438-125">Example</span></span>  
 <span data-ttu-id="a9438-126">Im folgenden Beispiel geben Sie ein Zeichen über die Tastatur ein. Das Programm verwendet eine geschachtelte `if` -Anweisung, um zu bestimmen, ob das eingegebene Zeichen ein alphabetisches Zeichen ist.</span><span class="sxs-lookup"><span data-stu-id="a9438-126">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="a9438-127">Wenn das eingegebene Zeichen ein alphabetisches Zeichen ist, überprüft das Programm, ob das eingegebene Zeichen in Groß- oder in Kleinschreibung ist.</span><span class="sxs-lookup"><span data-stu-id="a9438-127">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="a9438-128">In beiden Fällen wird eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9438-128">A message appears for each case.</span></span>  
  
 <span data-ttu-id="a9438-129">[!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9438-129">[!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9438-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9438-130">Example</span></span>  
 <span data-ttu-id="a9438-131">Sie können eine `if` Anweisung auch in einem else-Block schachteln, wie der folgende Codeausschnitt zeigt.</span><span class="sxs-lookup"><span data-stu-id="a9438-131">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="a9438-132">Im Beispiel werden `if` Anweisungen in zwei else-Blocks und einem then-Block geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="a9438-132">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="a9438-133">In den Kommentaren ist angegeben, welche Bedingungen in jedem Block true oder false sind.</span><span class="sxs-lookup"><span data-stu-id="a9438-133">The comments specify which conditions are true or false in each block.</span></span>  
  
 <span data-ttu-id="a9438-134">[!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9438-134">[!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9438-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9438-135">Example</span></span>  
 <span data-ttu-id="a9438-136">Im folgenden Beispiel wird bestimmt, ob ein eingegebenes Zeichen ein Kleinbuchstabe, ein Großbuchstabe oder eine Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="a9438-136">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="a9438-137">Wenn alle drei Bedingungen false sind, ist das Zeichen kein alphanumerisches Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a9438-137">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="a9438-138">Das Beispiel zeigt für jeden Fall eine Meldung an.</span><span class="sxs-lookup"><span data-stu-id="a9438-138">The example displays a message for each case.</span></span>  
  
 <span data-ttu-id="a9438-139">[!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="a9438-139">[!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]</span></span>  
  
 <span data-ttu-id="a9438-140">So, wie eine Anweisung im else-Block oder then-Block jede beliebige Anweisung sein kann, können Sie für die Bedingungen einen beliebigen gültigen booleschen Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9438-140">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="a9438-141">Sie können logische Operatoren wie z.B [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) und [!](../../../csharp/language-reference/operators/logical-negation-operator.md) verwenden</span><span class="sxs-lookup"><span data-stu-id="a9438-141">You can use logical operators such as [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="a9438-142">verwenden, um Verbundbedingungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9438-142">to make compound conditions.</span></span> <span data-ttu-id="a9438-143">Der folgende Code enthält Beispiele.</span><span class="sxs-lookup"><span data-stu-id="a9438-143">The following code shows examples.</span></span>  
  
```csharp  
// NOT  
bool result = true;  
if (!result)  
{  
    Console.WriteLine("The condition is true (result is false).");  
}  
else  
{  
    Console.WriteLine("The condition is false (result is true).");  
}  
  
// Short-circuit AND  
int m = 9;  
int n = 7;  
int p = 5;  
if (m >= n && m >= p)  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// AND and NOT  
if (m >= n && !(p > m))  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// Short-circuit OR  
if (m > n || m > p)  
{  
    Console.WriteLine("m isn't the smallest.");  
}  
  
// NOT and OR  
m = 4;  
if (!(m >= n || m >= p))  
{  
    Console.WriteLine("Now m is the smallest.");  
}  
// Output:  
// The condition is false (result is true).  
// Nothing is larger than m.  
// Nothing is larger than m.  
// m isn't the smallest.  
// Now m is the smallest.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="a9438-144">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="a9438-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a9438-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9438-145">See Also</span></span>  
 <span data-ttu-id="a9438-146">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9438-146">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a9438-147">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9438-147">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a9438-148">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9438-148">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a9438-149">[?:-Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a9438-149">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 <span data-ttu-id="a9438-150">[if-else-Anweisung (C++)](/cpp/cpp/if-else-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="a9438-150">[if-else Statement (C++)](/cpp/cpp/if-else-statement-cpp) </span></span>  
 [<span data-ttu-id="a9438-151">switch</span><span class="sxs-lookup"><span data-stu-id="a9438-151">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)

