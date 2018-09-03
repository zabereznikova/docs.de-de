---
title: for-Anweisung in C#
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: c6ef926d6fb2c79b7b7f71c3b24b86a7ab057c88
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391380"
---
# <a name="for-c-reference"></a><span data-ttu-id="62af5-102">for (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="62af5-102">for (C# reference)</span></span>

<span data-ttu-id="62af5-103">Die Anweisung `for` führt eine Anweisung oder einen Anweisungsblock aus, während ein angegebener boolescher Ausdruck `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="62af5-103">The `for` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="62af5-104">Sie können die Schleife an jedem Punkt im `for`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="62af5-104">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="62af5-105">Sie können eine `for`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="62af5-105">You also can exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="structure-of-the-for-statement"></a><span data-ttu-id="62af5-106">Struktur der `for`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="62af5-106">Structure of the `for` statement</span></span>

<span data-ttu-id="62af5-107">Jede `for`-Anweisung definiert die Abschnitte *initializer*, *condition* und *iterator*:</span><span class="sxs-lookup"><span data-stu-id="62af5-107">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>

```csharp
for (initializer; condition; iterator)
    body
```

<span data-ttu-id="62af5-108">Alle drei Abschnitte sind optional.</span><span class="sxs-lookup"><span data-stu-id="62af5-108">All three sections are optional.</span></span> <span data-ttu-id="62af5-109">Der Schleifenkörper ist entweder eine Anweisung oder ein Anweisungsblock</span><span class="sxs-lookup"><span data-stu-id="62af5-109">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="62af5-110">Im folgenden Beispiel wird die `for`-Anweisung mit allen Abschnitten definiert dargestellt:</span><span class="sxs-lookup"><span data-stu-id="62af5-110">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="62af5-111">Der Abschnitt *initializer*</span><span class="sxs-lookup"><span data-stu-id="62af5-111">The *initializer* section</span></span>

<span data-ttu-id="62af5-112">Die Anweisungen im Abschnitt *initializer* werden nur einmal ausgeführt, bevor die Schleife beginnt.</span><span class="sxs-lookup"><span data-stu-id="62af5-112">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="62af5-113">Der Abschnitt *initializer* ist eines der Folgenden:</span><span class="sxs-lookup"><span data-stu-id="62af5-113">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="62af5-114">Die Deklaration und Initialisierung einer lokalen Schleifenvariable, auf die nicht von außerhalb der Schleife zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="62af5-114">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="62af5-115">Null (0) oder mehr durch Kommas getrennte Anweisungsausdrücke aus der folgenden Liste:</span><span class="sxs-lookup"><span data-stu-id="62af5-115">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="62af5-116">[Zuweisungsanweisung](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="62af5-116">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="62af5-117">Aufruf einer Methode</span><span class="sxs-lookup"><span data-stu-id="62af5-117">invocation of a method</span></span>

  - <span data-ttu-id="62af5-118">Präfix- oder Postfix-[Inkrementausdruck](../operators/increment-operator.md), z.B. `++i` oder `i++`</span><span class="sxs-lookup"><span data-stu-id="62af5-118">prefix or postfix [increment](../operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>

  - <span data-ttu-id="62af5-119">Präfix- oder Postfix-[Dekrementausdruck](../operators/decrement-operator.md), z.B. `--i` oder `i--`</span><span class="sxs-lookup"><span data-stu-id="62af5-119">prefix or postfix [decrement](../operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>

  - <span data-ttu-id="62af5-120">Erstellung eines Objekts mithilfe des Schlüsselworts [new](new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="62af5-120">creation of an object by using [new](new-operator.md) keyword</span></span>

  - <span data-ttu-id="62af5-121">[await](await.md)-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="62af5-121">[await](await.md) expression</span></span>

<span data-ttu-id="62af5-122">Der Abschnitt *initializer* im obigen Beispiel deklariert und initialisiert die lokale Schleifenvariable `i`:</span><span class="sxs-lookup"><span data-stu-id="62af5-122">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="62af5-123">Der Abschnitt *condition*</span><span class="sxs-lookup"><span data-stu-id="62af5-123">The *condition* section</span></span>

<span data-ttu-id="62af5-124">Der Abschnitt *condition* muss ein boolescher Ausdruck sein, wenn er vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="62af5-124">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="62af5-125">Dieser Ausdruck wird vor jeder Schleifeniteration ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="62af5-125">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="62af5-126">Wenn der Abschnitt *condition* nicht vorhanden ist oder der boolesche Ausdruck `true` ergibt, wird die nächste Schleifeniteration ausgeführt. Andernfalls wird die Schleife beendet.</span><span class="sxs-lookup"><span data-stu-id="62af5-126">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="62af5-127">Im obigen Beispiel wird durch den Abschnitt *condition* bestimmt, ob die Schleife basierend auf dem Wert der lokalen Schleifenvariable beendet wird:</span><span class="sxs-lookup"><span data-stu-id="62af5-127">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="62af5-128">Der Abschnitt *iterator*</span><span class="sxs-lookup"><span data-stu-id="62af5-128">The *iterator* section</span></span>

<span data-ttu-id="62af5-129">Der Abschnitt *iterator* definiert, was nach jeder Iteration des Schleifenkörpers geschieht.</span><span class="sxs-lookup"><span data-stu-id="62af5-129">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="62af5-130">Der Abschnitt *iterator* enthält keine oder mehrere der folgenden durch Kommas getrennten Anweisungsausdrücke:</span><span class="sxs-lookup"><span data-stu-id="62af5-130">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>

- <span data-ttu-id="62af5-131">[Zuweisungsanweisung](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="62af5-131">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="62af5-132">Aufruf einer Methode</span><span class="sxs-lookup"><span data-stu-id="62af5-132">invocation of a method</span></span>

- <span data-ttu-id="62af5-133">Präfix- oder Postfix-[Inkrementausdruck](../operators/increment-operator.md), z.B. `++i` oder `i++`</span><span class="sxs-lookup"><span data-stu-id="62af5-133">prefix or postfix [increment](../operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>

- <span data-ttu-id="62af5-134">Präfix- oder Postfix-[Dekrementausdruck](../operators/decrement-operator.md), z.B. `--i` oder `i--`</span><span class="sxs-lookup"><span data-stu-id="62af5-134">prefix or postfix [decrement](../operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>

- <span data-ttu-id="62af5-135">Erstellung eines Objekts mithilfe des Schlüsselworts [new](new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="62af5-135">creation of an object by using [new](new-operator.md) keyword</span></span>

- <span data-ttu-id="62af5-136">[await](await.md)-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="62af5-136">[await](await.md) expression</span></span>

<span data-ttu-id="62af5-137">Im Beispiel wird die lokale Schleifenvariable durch den Abschnitt *iterator* inkrementiert:</span><span class="sxs-lookup"><span data-stu-id="62af5-137">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="62af5-138">Beispiele</span><span class="sxs-lookup"><span data-stu-id="62af5-138">Examples</span></span>

<span data-ttu-id="62af5-139">Das folgende Beispiel veranschaulicht mehrere weniger übliche Verwendungen der Abschnitte der `for`-Anweisung: das Zuweisen eines Werts für eine externe Schleifenvariable im Abschnitt *initializer*, das Aufrufen einer Methode in den Abschnitten *initializer* und *iterator* und das Ändern der Werte von zwei Variablen im Abschnitt *iterator*.</span><span class="sxs-lookup"><span data-stu-id="62af5-139">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="62af5-140">Klicken Sie auf **Run** (Ausführen), um den Beispielcode auszuführen.</span><span class="sxs-lookup"><span data-stu-id="62af5-140">Select **Run** to run the example code.</span></span> <span data-ttu-id="62af5-141">Danach können Sie Änderungen am Code vornehmen und ihn erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="62af5-141">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]

<span data-ttu-id="62af5-142">Im folgenden Beispiel wird die Endlosschleife `for` definiert:</span><span class="sxs-lookup"><span data-stu-id="62af5-142">The following example defines the infinite `for` loop:</span></span>

[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="62af5-143">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="62af5-143">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="62af5-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62af5-144">See also</span></span>

- [<span data-ttu-id="62af5-145">Die for-Anweisung (C#-Spezifikation)</span><span class="sxs-lookup"><span data-stu-id="62af5-145">The for statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement)
- [<span data-ttu-id="62af5-146">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="62af5-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="62af5-147">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="62af5-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="62af5-148">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="62af5-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="62af5-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="62af5-149">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="62af5-150">for-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="62af5-150">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)
- [<span data-ttu-id="62af5-151">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="62af5-151">Iteration Statements</span></span>](iteration-statements.md)
