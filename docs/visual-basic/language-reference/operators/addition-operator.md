---
title: + Operator
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: bc31e4c66c64d891e3fffd809b7ae99b9c9a0520
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873460"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="49f6a-102">+-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49f6a-102">+ Operator (Visual Basic)</span></span>

<span data-ttu-id="49f6a-103">Addiert zwei Zahlen oder gibt den positiven Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="49f6a-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="49f6a-104">Kann auch verwendet werden, um zwei Zeichen folgen Ausdrücke zu verketten.</span><span class="sxs-lookup"><span data-stu-id="49f6a-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f6a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="49f6a-105">Syntax</span></span>  
  
```vb
expression1 + expression2
```
  
<span data-ttu-id="49f6a-106">oder</span><span class="sxs-lookup"><span data-stu-id="49f6a-106">or</span></span>

```vb  
+expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="49f6a-107">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="49f6a-107">Parts</span></span>  
  
|<span data-ttu-id="49f6a-108">Begriff</span><span class="sxs-lookup"><span data-stu-id="49f6a-108">Term</span></span>|<span data-ttu-id="49f6a-109">Definition</span><span class="sxs-lookup"><span data-stu-id="49f6a-109">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="49f6a-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="49f6a-110">Required.</span></span> <span data-ttu-id="49f6a-111">Beliebiger numerischer Ausdruck oder Zeichen folgen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="49f6a-111">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="49f6a-112">Erforderlich, es sei denn, der `+` Operator berechnet einen negativen Wert.</span><span class="sxs-lookup"><span data-stu-id="49f6a-112">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="49f6a-113">Beliebiger numerischer Ausdruck oder Zeichen folgen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="49f6a-113">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="49f6a-114">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="49f6a-114">Result</span></span>  

 <span data-ttu-id="49f6a-115">Wenn `expression1` und `expression2` beide numerisch sind, entspricht das Ergebnis Ihrer arithmetischen Summe.</span><span class="sxs-lookup"><span data-stu-id="49f6a-115">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="49f6a-116">Wenn `expression2` nicht vorhanden ist, `+` ist der Operator der *unäre* Identitäts Operator für den unveränderten Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="49f6a-116">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="49f6a-117">In diesem Sinne besteht der Vorgang darin, das Vorzeichen von beizubehalten `expression1` , sodass das Ergebnis negativ ist, wenn `expression1` negativ ist.</span><span class="sxs-lookup"><span data-stu-id="49f6a-117">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="49f6a-118">Wenn `expression1` und `expression2` beide Zeichen folgen sind, ist das Ergebnis die Verkettung ihrer Werte.</span><span class="sxs-lookup"><span data-stu-id="49f6a-118">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="49f6a-119">Wenn `expression1` und `expression2` gemischte Typen sind, hängt die ausgeführte Aktion von ihren Typen, ihrem Inhalt und der Einstellung der [Option Strict-Anweisung](../statements/option-strict-statement.md)ab.</span><span class="sxs-lookup"><span data-stu-id="49f6a-119">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="49f6a-120">Weitere Informationen finden Sie in den Tabellen unter "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="49f6a-120">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="49f6a-121">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="49f6a-121">Supported Types</span></span>  

 <span data-ttu-id="49f6a-122">Alle numerischen Typen, einschließlich der unsignierten-und Gleit Komma Typen und `Decimal` , und `String` .</span><span class="sxs-lookup"><span data-stu-id="49f6a-122">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49f6a-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="49f6a-123">Remarks</span></span>  

 <span data-ttu-id="49f6a-124">Im allgemeinen `+` führt eine arithmetische Addition aus, wenn dies möglich ist, und verkettet nur, wenn beide Ausdrücke Zeichen folgen sind.</span><span class="sxs-lookup"><span data-stu-id="49f6a-124">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="49f6a-125">Wenn keiner der Ausdrücke eine ist `Object` , führt Visual Basic die folgenden Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="49f6a-125">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="49f6a-126">Datentypen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="49f6a-126">Data types of expressions</span></span>|<span data-ttu-id="49f6a-127">Aktion nach Compiler</span><span class="sxs-lookup"><span data-stu-id="49f6a-127">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="49f6a-128">Beide Ausdrücke sind numerische Datentypen ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` oder `Double` ).</span><span class="sxs-lookup"><span data-stu-id="49f6a-128">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="49f6a-129">Hinzufügen</span><span class="sxs-lookup"><span data-stu-id="49f6a-129">Add.</span></span> <span data-ttu-id="49f6a-130">Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von und geeignet ist `expression1` `expression2` .</span><span class="sxs-lookup"><span data-stu-id="49f6a-130">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="49f6a-131">Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](data-types-of-operator-results.md)</span><span class="sxs-lookup"><span data-stu-id="49f6a-131">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="49f6a-132">Beide Ausdrücke sind vom Typ. `String`</span><span class="sxs-lookup"><span data-stu-id="49f6a-132">Both expressions are of type `String`</span></span>|<span data-ttu-id="49f6a-133">Verketten.</span><span class="sxs-lookup"><span data-stu-id="49f6a-133">Concatenate.</span></span>|  
|<span data-ttu-id="49f6a-134">Ein Ausdruck ist ein numerischer Datentyp, der andere eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="49f6a-134">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="49f6a-135">Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="49f6a-135">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="49f6a-136">Wenn `Option Strict` `Off` den Wert hat, konvertieren Sie den implizit `String` in, `Double` und fügen Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="49f6a-136">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="49f6a-137">Wenn `String` nicht in konvertiert werden kann `Double` , wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="49f6a-137">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="49f6a-138">Ein Ausdruck ist ein numerischer Datentyp, der andere ist [Nothing](../nothing.md) .</span><span class="sxs-lookup"><span data-stu-id="49f6a-138">One expression is a numeric data type, and the other is [Nothing](../nothing.md)</span></span>|<span data-ttu-id="49f6a-139">Fügen Sie mit einem Wert von 0 (null) hinzu `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="49f6a-139">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="49f6a-140">Ein Ausdruck ist eine Zeichenfolge, und die andere ist. `Nothing`</span><span class="sxs-lookup"><span data-stu-id="49f6a-140">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="49f6a-141">Concatenate mit dem `Nothing` Wert "".</span><span class="sxs-lookup"><span data-stu-id="49f6a-141">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="49f6a-142">Wenn ein Ausdruck ein `Object` Ausdruck ist, führt Visual Basic die folgenden Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="49f6a-142">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="49f6a-143">Datentypen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="49f6a-143">Data types of expressions</span></span>|<span data-ttu-id="49f6a-144">Aktion nach Compiler</span><span class="sxs-lookup"><span data-stu-id="49f6a-144">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="49f6a-145">`Object` der Ausdruck enthält einen numerischen Wert und der andere einen numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="49f6a-145">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="49f6a-146">Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="49f6a-146">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="49f6a-147">Wenn `Option Strict` ist `Off` , dann hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="49f6a-147">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="49f6a-148">`Object` der Ausdruck enthält einen numerischen Wert, der andere vom Typ. `String`</span><span class="sxs-lookup"><span data-stu-id="49f6a-148">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="49f6a-149">Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="49f6a-149">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="49f6a-150">Wenn `Option Strict` `Off` den Wert hat, konvertieren Sie den implizit `String` in, `Double` und fügen Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="49f6a-150">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="49f6a-151">Wenn `String` nicht in konvertiert werden kann `Double` , wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="49f6a-151">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="49f6a-152">`Object` der Ausdruck enthält eine Zeichenfolge, die andere einen numerischen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="49f6a-152">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="49f6a-153">Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="49f6a-153">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="49f6a-154">Wenn `Option Strict` ist `Off` , konvertieren Sie die Zeichenfolge implizit `Object` in, `Double` und fügen Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="49f6a-154">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="49f6a-155">Wenn die Zeichenfolge `Object` nicht in konvertiert werden kann `Double` , wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="49f6a-155">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="49f6a-156">`Object` der Ausdruck enthält eine Zeichenfolge, und die andere weist den Typ auf. `String`</span><span class="sxs-lookup"><span data-stu-id="49f6a-156">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="49f6a-157">Wenn den Wert `Option Strict` `On` hat, generieren Sie einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="49f6a-157">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="49f6a-158">Wenn `Option Strict` `Off` den Wert hat, wird implizit `Object` in konvertiert `String` und verkettet.</span><span class="sxs-lookup"><span data-stu-id="49f6a-158">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="49f6a-159">Wenn beide Ausdrücke `Object` Ausdrücke sind, Visual Basic die folgenden Aktionen durchführt ( `Option Strict Off` nur).</span><span class="sxs-lookup"><span data-stu-id="49f6a-159">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="49f6a-160">Datentypen von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="49f6a-160">Data types of expressions</span></span>|<span data-ttu-id="49f6a-161">Aktion nach Compiler</span><span class="sxs-lookup"><span data-stu-id="49f6a-161">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="49f6a-162">Beide `Object` Ausdrücke enthalten numerische Werte.</span><span class="sxs-lookup"><span data-stu-id="49f6a-162">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="49f6a-163">Hinzufügen</span><span class="sxs-lookup"><span data-stu-id="49f6a-163">Add.</span></span>|  
|<span data-ttu-id="49f6a-164">Beide `Object` Ausdrücke sind vom Typ. `String`</span><span class="sxs-lookup"><span data-stu-id="49f6a-164">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="49f6a-165">Verketten.</span><span class="sxs-lookup"><span data-stu-id="49f6a-165">Concatenate.</span></span>|  
|<span data-ttu-id="49f6a-166">Ein `Object` Ausdruck enthält einen numerischen Wert, während der andere eine Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="49f6a-166">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="49f6a-167">Konvertieren Sie die Zeichenfolge implizit `Object` in `Double` und fügen Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="49f6a-167">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="49f6a-168">Wenn die Zeichenfolge `Object` nicht in einen numerischen Wert konvertiert werden kann, wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="49f6a-168">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="49f6a-169">Wenn `Object` einer der Ausdrücke als " [Nothing](../nothing.md) " oder ausgewertet <xref:System.DBNull> wird, `+` behandelt der Operator ihn als `String` mit dem Wert "".</span><span class="sxs-lookup"><span data-stu-id="49f6a-169">If either `Object` expression evaluates to [Nothing](../nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49f6a-170">Wenn Sie den- `+` Operator verwenden, sind Sie möglicherweise nicht in der Lage, zu bestimmen, ob Addition oder Zeichen folgen Verkettung auftreten.</span><span class="sxs-lookup"><span data-stu-id="49f6a-170">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="49f6a-171">Verwenden `&` Sie den Operator für die Verkettung, um Mehrdeutigkeit zu vermeiden und selbst dokumentierenden Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="49f6a-171">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="49f6a-172">Überladen</span><span class="sxs-lookup"><span data-stu-id="49f6a-172">Overloading</span></span>  

 <span data-ttu-id="49f6a-173">Der `+` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="49f6a-173">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="49f6a-174">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="49f6a-174">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="49f6a-175">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="49f6a-175">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49f6a-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="49f6a-176">Example</span></span>  

 <span data-ttu-id="49f6a-177">Im folgenden Beispiel wird der- `+` Operator verwendet, um Zahlen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="49f6a-177">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="49f6a-178">Wenn die Operanden beide numerisch sind, berechnet Visual Basic das arithmetische Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="49f6a-178">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="49f6a-179">Das arithmetische Ergebnis stellt die Summe der beiden Operanden dar.</span><span class="sxs-lookup"><span data-stu-id="49f6a-179">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="49f6a-180">Sie können auch den- `+` Operator verwenden, um Zeichen folgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="49f6a-180">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="49f6a-181">Wenn die Operanden beide Zeichen folgen sind, werden Sie von Visual Basic verkettet.</span><span class="sxs-lookup"><span data-stu-id="49f6a-181">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="49f6a-182">Das Verkettungs Ergebnis stellt eine einzelne Zeichenfolge dar, die aus dem Inhalt der beiden Operanden nacheinander besteht.</span><span class="sxs-lookup"><span data-stu-id="49f6a-182">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="49f6a-183">Wenn es sich bei den Operanden um gemischte Typen handelt, hängt das Ergebnis von der Einstellung der [Option Strict-Anweisung](../statements/option-strict-statement.md)ab.</span><span class="sxs-lookup"><span data-stu-id="49f6a-183">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="49f6a-184">Das folgende Beispiel veranschaulicht das Ergebnis, wenn `Option Strict` ist `On` .</span><span class="sxs-lookup"><span data-stu-id="49f6a-184">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="49f6a-185">Das folgende Beispiel veranschaulicht das Ergebnis, wenn `Option Strict` ist `Off` .</span><span class="sxs-lookup"><span data-stu-id="49f6a-185">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="49f6a-186">Um Mehrdeutigkeit auszuschließen, verwenden Sie den- `&` Operator anstelle von `+` für die Verkettung.</span><span class="sxs-lookup"><span data-stu-id="49f6a-186">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f6a-187">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49f6a-187">See also</span></span>

- [<span data-ttu-id="49f6a-188">&-Operator</span><span class="sxs-lookup"><span data-stu-id="49f6a-188">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="49f6a-189">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="49f6a-189">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="49f6a-190">Arithmetic Operators (Arithmetische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="49f6a-190">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="49f6a-191">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="49f6a-191">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="49f6a-192">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="49f6a-192">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="49f6a-193">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="49f6a-193">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="49f6a-194">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="49f6a-194">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
