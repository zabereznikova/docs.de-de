---
title: Formatieren von Nur-Text
description: 'Erfahren Sie, wie Sie printf und andere Klartext-Formatierungen in F #-Anwendungen und-Skripts verwenden.'
ms.date: 07/22/2020
ms.openlocfilehash: 90a861736dae69dfbc199a19e24f587c42404737
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063782"
---
# <a name="plain-text-formatting"></a><span data-ttu-id="a2c56-103">Formatieren von nur Text</span><span class="sxs-lookup"><span data-stu-id="a2c56-103">Plain text formatting</span></span>

<span data-ttu-id="a2c56-104">F # unterstützt die typüberprüfte Formatierung von Klartext mithilfe von `printf` , `printfn` , `sprintf` und verwandten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a2c56-104">F# supports type-checked formatting of plain text using `printf`, `printfn`, `sprintf`, and related functions.</span></span>
<span data-ttu-id="a2c56-105">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-105">For example,</span></span>

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

<span data-ttu-id="a2c56-106">Gibt die Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="a2c56-106">gives the output</span></span>

```fsharp
Hello world, 2 + 2 is 4
```

<span data-ttu-id="a2c56-107">Mit F # können auch strukturierte Werte als nur-Text formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="a2c56-107">F# also allows structured values to be formatted as plain text.</span></span>
<span data-ttu-id="a2c56-108">Sehen Sie sich z. b. das folgende Beispiel an, in dem die Ausgabe als Matrix ähnliche Anzeige von Tupeln formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2c56-108">For example, consider the following example that formats the output as a matrix-like display of tuples.</span></span>

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

<span data-ttu-id="a2c56-109">Die strukturierte Formatierung im Klartext wird aktiviert, wenn Sie das `%A` Format in Formatierungs Zeichenfolgen verwenden `printf` .</span><span class="sxs-lookup"><span data-stu-id="a2c56-109">Structured plain text formatting is activated when you use the `%A` format in `printf` formatting strings.</span></span>
<span data-ttu-id="a2c56-110">Sie wird auch aktiviert, wenn die Ausgabe von Werten in F # Interactive formatiert wird, wobei die Ausgabe zusätzliche Informationen enthält und außerdem anpassbar ist.</span><span class="sxs-lookup"><span data-stu-id="a2c56-110">It's also activated when formatting the output of values in F# interactive, where the output includes extra information and is additionally customizable.</span></span>
<span data-ttu-id="a2c56-111">Die nur-Text-Formatierung kann auch durch Aufrufe von in `x.ToString()` F #-Union-und-Datensatz-Werten beobachtet werden, einschließlich derjenigen, die implizit beim Debuggen, protokollieren und anderen Tools auftreten.</span><span class="sxs-lookup"><span data-stu-id="a2c56-111">Plain text formatting is also observable through any calls to `x.ToString()` on F# union and record values, including those that occur implicitly in debugging, logging, and other tooling.</span></span>

## <a name="checking-of-printf-format-strings"></a><span data-ttu-id="a2c56-112">Überprüfen von Format Zeichenfolgen `printf`</span><span class="sxs-lookup"><span data-stu-id="a2c56-112">Checking of `printf`-format strings</span></span>

<span data-ttu-id="a2c56-113">Ein Kompilierzeitfehler wird gemeldet, wenn eine `printf` Formatierungsfunktion mit einem Argument verwendet wird, das nicht mit den printf-Format bezeichmern in der Format Zeichenfolge identisch ist.</span><span class="sxs-lookup"><span data-stu-id="a2c56-113">A compile-time error will be reported if a `printf` formatting function is used with an argument that doesn't match the printf format specifiers in the format string.</span></span>  <span data-ttu-id="a2c56-114">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-114">For example,</span></span>

```fsharp
sprintf "Hello %s" (2+2)
```

<span data-ttu-id="a2c56-115">Gibt die Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="a2c56-115">gives the output</span></span>

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

<span data-ttu-id="a2c56-116">Wenn Sie `printf` und andere verwandte Funktionen verwenden, prüft eine spezielle Regel im F #-Compiler das als Format Zeichenfolge übergebenen Zeichenfolgenliteral. Dadurch wird sichergestellt, dass die nachfolgenden Argumente den richtigen Typ aufweisen, um mit den verwendeten Format bezeichnerwerten zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a2c56-116">Technically speaking, when using `printf` and other related functions, a special rule in the F# compiler checks the string literal passed as the format string, ensuring the subsequent arguments applied are of the correct type to match the format specifiers used.</span></span>

## <a name="format-specifiers-for-printf"></a><span data-ttu-id="a2c56-117">Formatspezifizierer für`printf`</span><span class="sxs-lookup"><span data-stu-id="a2c56-117">Format specifiers for `printf`</span></span>

<span data-ttu-id="a2c56-118">Formatspezifikationen für `printf` Formate sind Zeichen folgen mit `%` Markierungen, die das Format angeben.</span><span class="sxs-lookup"><span data-stu-id="a2c56-118">Format specifications for `printf` formats are strings with `%` markers that indicate format.</span></span> <span data-ttu-id="a2c56-119">Format Platzhalter bestehen aus der `%[flags][width][.precision][type]` Art, in der der Typ wie folgt interpretiert wird:</span><span class="sxs-lookup"><span data-stu-id="a2c56-119">Format placeholders consist of `%[flags][width][.precision][type]` where the type is interpreted as follows:</span></span>

| <span data-ttu-id="a2c56-120">Formatbezeichner</span><span class="sxs-lookup"><span data-stu-id="a2c56-120">Format specifier</span></span>   | <span data-ttu-id="a2c56-121">Typ (e)</span><span class="sxs-lookup"><span data-stu-id="a2c56-121">Type(s)</span></span>        | <span data-ttu-id="a2c56-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a2c56-122">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | <span data-ttu-id="a2c56-123">bool</span><span class="sxs-lookup"><span data-stu-id="a2c56-123">bool</span></span>      | <span data-ttu-id="a2c56-124">Formatiert als `true` oder`false`</span><span class="sxs-lookup"><span data-stu-id="a2c56-124">Formatted as `true` or `false`</span></span>                |
| `%s`               | <span data-ttu-id="a2c56-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2c56-125">string</span></span>    | <span data-ttu-id="a2c56-126">Formatiert als Inhalt ohne Escapezeichen</span><span class="sxs-lookup"><span data-stu-id="a2c56-126">Formatted as its unescaped contents</span></span>         |
| `%c`               | <span data-ttu-id="a2c56-127">char</span><span class="sxs-lookup"><span data-stu-id="a2c56-127">char</span></span>      | <span data-ttu-id="a2c56-128">Formatiert als Zeichenliteral</span><span class="sxs-lookup"><span data-stu-id="a2c56-128">Formatted as the character literal</span></span>  |
| <span data-ttu-id="a2c56-129">`%d`, `%i`</span><span class="sxs-lookup"><span data-stu-id="a2c56-129">`%d`, `%i`</span></span>         | <span data-ttu-id="a2c56-130">ein einfacher ganzzahliger Typ</span><span class="sxs-lookup"><span data-stu-id="a2c56-130">a basic integer type</span></span> | <span data-ttu-id="a2c56-131">Formatiert als ganze Dezimalzahl, signiert, wenn der grundlegende ganzzahlige Typ signiert ist.</span><span class="sxs-lookup"><span data-stu-id="a2c56-131">Formatted as a decimal integer, signed if the basic integer type is signed</span></span> |
| `%u`               | <span data-ttu-id="a2c56-132">ein einfacher ganzzahliger Typ</span><span class="sxs-lookup"><span data-stu-id="a2c56-132">a basic integer type</span></span> | <span data-ttu-id="a2c56-133">Formatiert als ganze Dezimalzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="a2c56-133">Formatted as an unsigned decimal integer</span></span>   |
| <span data-ttu-id="a2c56-134">`%x`, `%X`</span><span class="sxs-lookup"><span data-stu-id="a2c56-134">`%x`, `%X`</span></span>         | <span data-ttu-id="a2c56-135">ein einfacher ganzzahliger Typ</span><span class="sxs-lookup"><span data-stu-id="a2c56-135">a basic integer type</span></span> | <span data-ttu-id="a2c56-136">Formatiert als hexadezimal Zahl ohne Vorzeichen (a-f oder a-f für Hex-Ziffern)</span><span class="sxs-lookup"><span data-stu-id="a2c56-136">Formatted as an unsigned hexadecimal number (a-f or A-F for hex digits respectively)</span></span>  |
|  `%o`              | <span data-ttu-id="a2c56-137">ein einfacher ganzzahliger Typ</span><span class="sxs-lookup"><span data-stu-id="a2c56-137">a basic integer type</span></span> | <span data-ttu-id="a2c56-138">Formatiert als oktale Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="a2c56-138">Formatted as an unsigned octal number</span></span> |
| <span data-ttu-id="a2c56-139">`%e`, `%E`</span><span class="sxs-lookup"><span data-stu-id="a2c56-139">`%e`, `%E`</span></span>         | <span data-ttu-id="a2c56-140">ein Basistyp für Gleit Komma Zahlen</span><span class="sxs-lookup"><span data-stu-id="a2c56-140">a basic floating point type</span></span> | <span data-ttu-id="a2c56-141">Wird als Wert mit Vorzeichen formatiert, wobei das Format `[-]d.dddde[sign]ddd` d eine einfache Dezimalzahl ist, dddd eine oder mehrere Dezimalstellen, DDD genau drei Dezimalstellen und Vorzeichen `+` oder`-`</span><span class="sxs-lookup"><span data-stu-id="a2c56-141">Formatted as a signed value having the form `[-]d.dddde[sign]ddd` where d is a single decimal digit, dddd is one or more decimal digits, ddd is exactly three decimal digits, and sign is `+` or `-`</span></span> |
| `%f`               | <span data-ttu-id="a2c56-142">ein Basistyp für Gleit Komma Zahlen</span><span class="sxs-lookup"><span data-stu-id="a2c56-142">a basic floating point type</span></span> | <span data-ttu-id="a2c56-143">Wird als signierter Wert mit dem Format formatiert `[-]dddd.dddd` , wobei `dddd` eine oder mehrere Dezimalstellen sind.</span><span class="sxs-lookup"><span data-stu-id="a2c56-143">Formatted as a signed value having the form `[-]dddd.dddd`, where `dddd` is one or more decimal digits.</span></span> <span data-ttu-id="a2c56-144">Die Anzahl der Ziffern vor dem Dezimaltrennzeichen ist abhängig von der Größe der Zahl, und die Anzahl der Ziffern nach dem Dezimaltrennzeichen ist abhängig von der angeforderten Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="a2c56-144">The number of digits before the decimal point depends on the magnitude of the number, and the number of digits after the decimal point depends on the requested precision.</span></span> |
| <span data-ttu-id="a2c56-145">`%g`, `%G`</span><span class="sxs-lookup"><span data-stu-id="a2c56-145">`%g`, `%G`</span></span> | <span data-ttu-id="a2c56-146">ein Basistyp für Gleit Komma Zahlen</span><span class="sxs-lookup"><span data-stu-id="a2c56-146">a basic floating point type</span></span> |  <span data-ttu-id="a2c56-147">Formatiert mithilfe von als Wert mit Vorzeichen `%f` im `%e` Format oder, je nachdem, welcher Wert für den angegebenen Wert und die Genauigkeit kompakter ist.</span><span class="sxs-lookup"><span data-stu-id="a2c56-147">Formatted using as a signed value printed in `%f` or `%e` format, whichever is more compact for the given value and precision.</span></span> |
| `%M` | <span data-ttu-id="a2c56-148">ein- `System.Decimal` Wert</span><span class="sxs-lookup"><span data-stu-id="a2c56-148">a `System.Decimal` value</span></span>  |    <span data-ttu-id="a2c56-149">Formatiert mit dem Format Bezeichner `"G"` für`System.Decimal.ToString(format)`</span><span class="sxs-lookup"><span data-stu-id="a2c56-149">Formatted using the `"G"` format specifier for `System.Decimal.ToString(format)`</span></span> |
| `%O` | <span data-ttu-id="a2c56-150">beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="a2c56-150">any value</span></span>  |   <span data-ttu-id="a2c56-151">Formatiert durch Boxing des-Objekts und Aufrufen seiner- `System.Object.ToString()` Methode.</span><span class="sxs-lookup"><span data-stu-id="a2c56-151">Formatted by boxing the object and calling its `System.Object.ToString()` method</span></span> |
| `%A` | <span data-ttu-id="a2c56-152">beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="a2c56-152">any value</span></span>  |   <span data-ttu-id="a2c56-153">Formatiert mit [strukturierter Klartext-Formatierung](plaintext-formatting.md) mit den Standardlayouteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a2c56-153">Formatted using [structured plain text formatting](plaintext-formatting.md) with the default layout settings</span></span> |
| `%a` | <span data-ttu-id="a2c56-154">beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="a2c56-154">any value</span></span>  |   <span data-ttu-id="a2c56-155">Erfordert zwei Argumente: eine Formatierungsfunktion, die einen Kontext Parameter und den Wert akzeptiert, und den zu Druck Ende Wert.</span><span class="sxs-lookup"><span data-stu-id="a2c56-155">Requires two arguments: a formatting function accepting a context parameter and the value, and the particular value to print</span></span> |
| `%t` | <span data-ttu-id="a2c56-156">beliebiger Wert</span><span class="sxs-lookup"><span data-stu-id="a2c56-156">any value</span></span>  |   <span data-ttu-id="a2c56-157">Erfordert ein Argument: eine Formatierungsfunktion, die einen Kontext Parameter annimmt, der den entsprechenden Text entweder ausgibt oder zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a2c56-157">Requires one argument: a formatting function accepting a context parameter that either outputs or returns the appropriate text</span></span> |
| `%%` | <span data-ttu-id="a2c56-158">(none)</span><span class="sxs-lookup"><span data-stu-id="a2c56-158">(none)</span></span>  |   <span data-ttu-id="a2c56-159">Erfordert keine Argumente und druckt ein einfaches Prozentzeichen:`%`</span><span class="sxs-lookup"><span data-stu-id="a2c56-159">Requires no arguments and prints a plain percent sign: `%`</span></span> |

<span data-ttu-id="a2c56-160">Einfache ganzzahlige Typen sind `byte` ( `System.Byte` ), `sbyte` ( `System.SByte` ), `int16` ( `System.Int16` ), `uint16` ( `System.UInt16` ), `int32` ( `System.Int32` ), (), `uint32` `System.UInt32` `int64` ( `System.Int64` ), `uint64` ( `System.UInt64` ), `nativeint` ( `System.IntPtr` ) und `unativeint` ( `System.UIntPtr` ).</span><span class="sxs-lookup"><span data-stu-id="a2c56-160">Basic integer types are `byte` (`System.Byte`), `sbyte` (`System.SByte`), `int16` (`System.Int16`), `uint16` (`System.UInt16`), `int32` (`System.Int32`), `uint32` (`System.UInt32`), `int64` (`System.Int64`), `uint64` (`System.UInt64`), `nativeint`  (`System.IntPtr`), and `unativeint`  (`System.UIntPtr`).</span></span>
<span data-ttu-id="a2c56-161">Grundlegende Gleit Komma Typen sind `float` ( `System.Double` ) und `float32` ( `System.Single` ).</span><span class="sxs-lookup"><span data-stu-id="a2c56-161">Basic floating point types are `float` (`System.Double`) and `float32` (`System.Single`).</span></span>

<span data-ttu-id="a2c56-162">Die optionale Breite ist eine ganze Zahl, die die minimale Breite des Ergebnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="a2c56-162">The optional width is an integer indicating the minimal width of the result.</span></span> <span data-ttu-id="a2c56-163">Gibt beispielsweise `%6d` eine ganze Zahl aus, die Leerzeichen vorangestellt ist, um mindestens sechs Zeichen auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="a2c56-163">For instance, `%6d` prints an integer, prefixing it with spaces to fill at least six characters.</span></span> <span data-ttu-id="a2c56-164">Wenn Width `*` gleich ist, wird ein zusätzliches ganzzahliges Argument zum Angeben der entsprechenden Breite verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2c56-164">If width is `*`, then an extra integer  argument is taken to specify the corresponding width.</span></span>

<span data-ttu-id="a2c56-165">Gültige Flags sind:</span><span class="sxs-lookup"><span data-stu-id="a2c56-165">Valid flags are:</span></span>

| <span data-ttu-id="a2c56-166">Flag</span><span class="sxs-lookup"><span data-stu-id="a2c56-166">Flag</span></span>   | <span data-ttu-id="a2c56-167">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="a2c56-167">Effect</span></span>        | <span data-ttu-id="a2c56-168">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a2c56-168">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | <span data-ttu-id="a2c56-169">Fügen Sie Nullen anstelle von Leerzeichen hinzu, um die erforderliche Breite zu bilden.</span><span class="sxs-lookup"><span data-stu-id="a2c56-169">Add zeros instead of spaces to make up the required width</span></span> |    |
| `-` |  <span data-ttu-id="a2c56-170">Linksbündig das Ergebnis innerhalb der angegebenen Breite begründen</span><span class="sxs-lookup"><span data-stu-id="a2c56-170">Left justify the result within the specified width</span></span> |   |
| `+`  | <span data-ttu-id="a2c56-171">Fügen Sie ein `+` Zeichen hinzu, wenn die Zahl positiv ist (um einem `-` Vorzeichen für negatives zu entsprechen).</span><span class="sxs-lookup"><span data-stu-id="a2c56-171">Add a `+` character if the number is positive (to match a `-` sign for negatives)</span></span> |   |
| <span data-ttu-id="a2c56-172">Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="a2c56-172">space character</span></span> | <span data-ttu-id="a2c56-173">Zusätzlichen Speicherplatz hinzufügen, wenn die Zahl positiv ist (um ein "-"-Zeichen für negative Entsprechung zu finden)</span><span class="sxs-lookup"><span data-stu-id="a2c56-173">Add an extra space if the number is positive (to match a '-' sign for negatives)</span></span> |

<span data-ttu-id="a2c56-174">Das printf `#` -Flag ist ungültig, und es wird ein Kompilierzeitfehler gemeldet, wenn es verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2c56-174">The printf `#` flag is invalid and a compile-time error will be reported if it is used.</span></span>

<span data-ttu-id="a2c56-175">Werte werden mithilfe der invarianten Kultur formatiert.</span><span class="sxs-lookup"><span data-stu-id="a2c56-175">Values are formatted using invariant culture.</span></span> <span data-ttu-id="a2c56-176">Kultur Einstellungen sind für `printf` die Formatierung unerheblich, es sei denn, Sie wirken sich auf die Ergebnisse der Formatierung `%O` und aus `%A` .</span><span class="sxs-lookup"><span data-stu-id="a2c56-176">Culture settings are irrelevant to `printf` formatting except when they affect the results of `%O` and `%A` formatting.</span></span> <span data-ttu-id="a2c56-177">Weitere Informationen finden Sie unter [strukturierte Klartext-Formatierung](plaintext-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="a2c56-177">For more information, see [structured plain text formatting](plaintext-formatting.md).</span></span>

## <a name="a-formatting"></a><span data-ttu-id="a2c56-178">`%A`ert</span><span class="sxs-lookup"><span data-stu-id="a2c56-178">`%A` formatting</span></span>

<span data-ttu-id="a2c56-179">Der `%A` Format Bezeichner wird verwendet, um Werte auf lesbare Weise zu formatieren, und kann auch hilfreich sein, um Diagnoseinformationen zu melden.</span><span class="sxs-lookup"><span data-stu-id="a2c56-179">The `%A` format specifier is used to format values in a human-readable way, and can also be useful for reporting diagnostic information.</span></span>

### <a name="primitive-values"></a><span data-ttu-id="a2c56-180">Primitive Werte</span><span class="sxs-lookup"><span data-stu-id="a2c56-180">Primitive values</span></span>

<span data-ttu-id="a2c56-181">Beim Formatieren von Klartext mit dem `%A` Spezifizierer werden numerische F #-Werte mit Ihrem Suffix und der invarianten Kultur formatiert.</span><span class="sxs-lookup"><span data-stu-id="a2c56-181">When formatting plain text using the `%A` specifier, F# numeric values are formatted with their suffix and invariant culture.</span></span> <span data-ttu-id="a2c56-182">Gleit Komma Werte werden mithilfe von 10 Stellen der Gleit Komma Genauigkeit formatiert.</span><span class="sxs-lookup"><span data-stu-id="a2c56-182">Floating point values are formatted using 10 places of floating point precision.</span></span> <span data-ttu-id="a2c56-183">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-183">For example,</span></span>

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

<span data-ttu-id="a2c56-184">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-184">produces</span></span>

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

<span data-ttu-id="a2c56-185">Wenn Sie den- `%A` Spezifizierer verwenden, werden Zeichen folgen mit Anführungszeichen formatiert.</span><span class="sxs-lookup"><span data-stu-id="a2c56-185">When using the `%A` specifier, strings are formatted using quotes.</span></span> <span data-ttu-id="a2c56-186">Escapecodes werden nicht hinzugefügt, und stattdessen werden die Rohzeichen gedruckt.</span><span class="sxs-lookup"><span data-stu-id="a2c56-186">Escape codes are not added and instead the raw characters are printed.</span></span> <span data-ttu-id="a2c56-187">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-187">For example,</span></span>

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

<span data-ttu-id="a2c56-188">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-188">produces</span></span>

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a><span data-ttu-id="a2c56-189">.Net-Werte</span><span class="sxs-lookup"><span data-stu-id="a2c56-189">.NET values</span></span>

<span data-ttu-id="a2c56-190">Beim Formatieren von nur-Text mit dem `%A` -Spezifizierer werden nicht-F #-.NET-Objekte mithilfe `x.ToString()` der Standardeinstellungen von .net formatiert, die von und angegeben werden `System.Globalization.CultureInfo.CurrentCulture` `System.Globalization.CultureInfo.CurrentUICulture` .</span><span class="sxs-lookup"><span data-stu-id="a2c56-190">When formatting plain text using the `%A` specifier, non-F# .NET objects are formatted by using `x.ToString()` using the default settings of .NET given by `System.Globalization.CultureInfo.CurrentCulture` and `System.Globalization.CultureInfo.CurrentUICulture`.</span></span>  <span data-ttu-id="a2c56-191">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-191">For example,</span></span>

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

<span data-ttu-id="a2c56-192">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-192">produces</span></span>

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a><span data-ttu-id="a2c56-193">Strukturierte Werte</span><span class="sxs-lookup"><span data-stu-id="a2c56-193">Structured values</span></span>

<span data-ttu-id="a2c56-194">Beim Formatieren von nur-Text mit dem- `%A` Spezifizierer wird der Block Einzug für F #-Listen und-Tupel verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2c56-194">When formatting plain text using the `%A` specifier, block indentation is used for F# lists and tuples.</span></span> <span data-ttu-id="a2c56-195">Dies wird im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2c56-195">This shown in the previous example.</span></span>
<span data-ttu-id="a2c56-196">Die Struktur von Arrays wird ebenfalls verwendet, einschließlich mehrdimensionaler Arrays.</span><span class="sxs-lookup"><span data-stu-id="a2c56-196">The structure of arrays is also used, including multi-dimensional arrays.</span></span>  <span data-ttu-id="a2c56-197">Eindimensionale Arrays werden mit Syntax angezeigt `[| ... |]` .</span><span class="sxs-lookup"><span data-stu-id="a2c56-197">Single-dimensional arrays are shown with `[| ... |]` syntax.</span></span> <span data-ttu-id="a2c56-198">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-198">For example,</span></span>

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

<span data-ttu-id="a2c56-199">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-199">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

<span data-ttu-id="a2c56-200">Die Standarddruck Breite ist 80.</span><span class="sxs-lookup"><span data-stu-id="a2c56-200">The default print width is 80.</span></span>  <span data-ttu-id="a2c56-201">Diese Breite kann mit einer Druckbreite im Format Bezeichner angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="a2c56-201">This width can be customized by using a print width in the format specifier.</span></span> <span data-ttu-id="a2c56-202">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-202">For example,</span></span>

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

<span data-ttu-id="a2c56-203">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-203">produces</span></span>

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

<span data-ttu-id="a2c56-204">Wenn eine Druckbreite von 0 angegeben wird, wird keine Druckbreite verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2c56-204">Specifying a print width of 0 results in no print width being used.</span></span> <span data-ttu-id="a2c56-205">Eine einzelne Textzeile wird angezeigt, außer wenn eingebettete Zeichen folgen in der Ausgabezeilen Umbrüche enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2c56-205">A single line of text will result, except where embedded strings in the output contain line breaks.</span></span>  <span data-ttu-id="a2c56-206">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a2c56-206">For example</span></span>

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

<span data-ttu-id="a2c56-207">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-207">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

<span data-ttu-id="a2c56-208">Ein tiefen Limit von 4 wird für Sequenzwerte ( `IEnumerable` ) verwendet, die als angezeigt werden `seq { ...}` .</span><span class="sxs-lookup"><span data-stu-id="a2c56-208">A depth limit of 4 is used for sequence (`IEnumerable`) values, which are shown as `seq { ...}`.</span></span> <span data-ttu-id="a2c56-209">Für Listen-und Array Werte wird eine Tiefe Grenze von 100 verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2c56-209">A depth limit of 100 is used for list and array values.</span></span>
<span data-ttu-id="a2c56-210">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-210">For example,</span></span>

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

<span data-ttu-id="a2c56-211">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-211">produces</span></span>

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

<span data-ttu-id="a2c56-212">Der Block Einzug wird auch für die Struktur öffentlicher Daten Satz-und Union-Werte verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2c56-212">Block indentation is also used for the structure of public record and union values.</span></span> <span data-ttu-id="a2c56-213">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-213">For example,</span></span>

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="a2c56-214">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-214">produces</span></span>

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="a2c56-215">Wenn `%+A` verwendet wird, wird die private Struktur von Datensätzen und Unions auch mithilfe von Reflektion offengelegt.</span><span class="sxs-lookup"><span data-stu-id="a2c56-215">If `%+A` is used, then the private structure of records and unions is also revealed by using reflection.</span></span> <span data-ttu-id="a2c56-216">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a2c56-216">For example</span></span>

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

<span data-ttu-id="a2c56-217">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-217">produces</span></span>

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a><span data-ttu-id="a2c56-218">Große, zyklische oder tief geschachtelte Werte</span><span class="sxs-lookup"><span data-stu-id="a2c56-218">Large, cyclic, or deeply nested values</span></span>

<span data-ttu-id="a2c56-219">Große strukturierte Werte werden mit einer maximalen Gesamtzahl von Objekt Knoten von 10000 formatiert.</span><span class="sxs-lookup"><span data-stu-id="a2c56-219">Large structured values are formatted to a maximum overall object node count of 10000.</span></span>
<span data-ttu-id="a2c56-220">Tief geschachtelte Werte werden mit einer Tiefe von 100 formatiert.</span><span class="sxs-lookup"><span data-stu-id="a2c56-220">Deeply nested values are formatted to a depth of 100.</span></span>  <span data-ttu-id="a2c56-221">In beiden Fällen `...` wird verwendet, um einen Teil der Ausgabe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a2c56-221">In both cases `...` is used to elide some of the output.</span></span>  <span data-ttu-id="a2c56-222">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-222">For example,</span></span>

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

<span data-ttu-id="a2c56-223">erzeugt eine große Ausgabe mit einigen Teilen:</span><span class="sxs-lookup"><span data-stu-id="a2c56-223">produces a large output with some parts elided:</span></span>

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

<span data-ttu-id="a2c56-224">Zyklen werden in den Objekt Diagrammen erkannt und `...` an Stellen verwendet, an denen Zyklen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="a2c56-224">Cycles are detected in the object graphs and `...` is used at places where cycles are detected.</span></span> <span data-ttu-id="a2c56-225">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a2c56-225">For example</span></span>

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

<span data-ttu-id="a2c56-226">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-226">produces</span></span>

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a><span data-ttu-id="a2c56-227">Werte für Lazy, NULL und Function</span><span class="sxs-lookup"><span data-stu-id="a2c56-227">Lazy, null, and function values</span></span>

<span data-ttu-id="a2c56-228">Verzögerte Werte werden als `Value is not created` oder entsprechender Text gedruckt, wenn der Wert noch nicht ausgewertet wurde.</span><span class="sxs-lookup"><span data-stu-id="a2c56-228">Lazy values are printed as `Value is not created` or equivalent text when the value has not yet been evaluated.</span></span>

<span data-ttu-id="a2c56-229">NULL-Werte werden als gedruckt `null` , es sei denn, der statische Typ des Werts wird als Union-Typ festgelegt, wobei `null` eine zugelassene Darstellung ist.</span><span class="sxs-lookup"><span data-stu-id="a2c56-229">Null values are printed as `null` unless the static type of the value is determined to be a union type where `null` is a permitted representation.</span></span>

<span data-ttu-id="a2c56-230">F #-Funktions Werte werden als Ihr intern generierter Schließungs Name gedruckt, z `<fun:it@43-7>` . b..</span><span class="sxs-lookup"><span data-stu-id="a2c56-230">F# function values are printed as their internally generated closure name, for example, `<fun:it@43-7>`.</span></span>

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a><span data-ttu-id="a2c56-231">Anpassen der nur-Text-Formatierung mit`StructuredFormatDisplay`</span><span class="sxs-lookup"><span data-stu-id="a2c56-231">Customize plain text formatting with `StructuredFormatDisplay`</span></span>

<span data-ttu-id="a2c56-232">Wenn Sie den- `%A` Spezifizierer verwenden, wird das vorhanden sein des- `StructuredFormatDisplay` Attributs für Typdeklarationen beachtet.</span><span class="sxs-lookup"><span data-stu-id="a2c56-232">When using the `%A` specifier, the presence of the `StructuredFormatDisplay` attribute on type declarations is respected.</span></span>  <span data-ttu-id="a2c56-233">Dies kann verwendet werden, um den Ersatztext und die Eigenschaft anzugeben, um einen Wert anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2c56-233">This can be used to specify surrogate text and property to display a value.</span></span> <span data-ttu-id="a2c56-234">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a2c56-234">For example:</span></span>

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

<span data-ttu-id="a2c56-235">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-235">produces</span></span>

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a><span data-ttu-id="a2c56-236">Einfache Textformatierung durch Überschreiben anpassen`ToString`</span><span class="sxs-lookup"><span data-stu-id="a2c56-236">Customize plain text formatting by overriding `ToString`</span></span>

<span data-ttu-id="a2c56-237">Die Standard Implementierung von `ToString` ist in der F #-Programmierung Observable.</span><span class="sxs-lookup"><span data-stu-id="a2c56-237">The default implementation of `ToString` is observable in F# programming.</span></span> <span data-ttu-id="a2c56-238">Häufig sind die Standard Ergebnisse nicht für die Verwendung in der programmierseitigen Informationsanzeige oder bei der Benutzer Ausgabe geeignet. Folglich ist es üblich, die Standard Implementierung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a2c56-238">Often, the default results aren't suitable for use in either programmer-facing information display or user output, and as a result it is common to override the default implementation.</span></span>  

<span data-ttu-id="a2c56-239">Standardmäßig überschreiben F #-Datensatz-und Union-Typen die Implementierung von `ToString` mit einer-Implementierung, die verwendet `sprintf "%+A"` .</span><span class="sxs-lookup"><span data-stu-id="a2c56-239">By default, F# record and union types override the implementation of `ToString` with an implementation that uses `sprintf "%+A"`.</span></span>  <span data-ttu-id="a2c56-240">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-240">For example,</span></span>

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

<span data-ttu-id="a2c56-241">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-241">produces</span></span>

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

<span data-ttu-id="a2c56-242">Bei Klassentypen wird keine Standard Implementierung von `ToString` bereitgestellt, und der .NET-Standard wird verwendet, der den Namen des Typs meldet.</span><span class="sxs-lookup"><span data-stu-id="a2c56-242">For class types, no default implementation of `ToString` is provided and the .NET default is used, which reports the name of the type.</span></span> <span data-ttu-id="a2c56-243">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="a2c56-243">For example,</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="a2c56-244">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-244">produces</span></span>

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

<span data-ttu-id="a2c56-245">Das Hinzufügen einer außer Kraft setzung für `ToString` kann eine bessere Formatierung bieten.</span><span class="sxs-lookup"><span data-stu-id="a2c56-245">Adding an override for `ToString` can give better formatting.</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="a2c56-246">Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="a2c56-246">produces</span></span>

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="a2c56-247">F# Interactive strukturierter Druck</span><span class="sxs-lookup"><span data-stu-id="a2c56-247">F# Interactive structured printing</span></span>

<span data-ttu-id="a2c56-248">F# Interactive ( `dotnet fsi` ) verwendet eine erweiterte Version der strukturierten Klartext-Formatierung, um Werte zu melden, und ermöglicht zusätzliche Anpassungsmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="a2c56-248">F# Interactive (`dotnet fsi`) uses an extended version of structured plain text formatting to report values and allows additional customizability.</span></span> <span data-ttu-id="a2c56-249">Weitere Informationen finden Sie unter [F# Interactive](fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="a2c56-249">For more information, see [F# Interactive](fsharp-interactive-options.md).</span></span>

## <a name="customize-debug-displays"></a><span data-ttu-id="a2c56-250">Anpassen der debuganzeige</span><span class="sxs-lookup"><span data-stu-id="a2c56-250">Customize debug displays</span></span>

<span data-ttu-id="a2c56-251">Debugger für .net berücksichtigen die Verwendung von Attributen, wie z `DebuggerDisplay` `DebuggerTypeProxy` . b. und, und diese beeinflussen die strukturierte Anzeige von Objekten in debuggerinspektions-Fenstern.</span><span class="sxs-lookup"><span data-stu-id="a2c56-251">Debuggers for .NET respect the use of attributes such as `DebuggerDisplay` and `DebuggerTypeProxy`, and these affect the structured display of objects in debugger inspection windows.</span></span>
<span data-ttu-id="a2c56-252">Der F #-Compiler hat diese Attribute automatisch für Unterscheidungs-Union-und Daten Satz Typen generiert, aber nicht für Klassen-, Schnittstellen-oder Strukturtypen.</span><span class="sxs-lookup"><span data-stu-id="a2c56-252">The F# compiler automatically generated these attributes for discriminated union and record types, but not class, interface, or struct types.</span></span>

<span data-ttu-id="a2c56-253">Diese Attribute werden bei der Klartext-Formatierung in F # ignoriert, aber es kann nützlich sein, diese Methoden zu implementieren, um die Anzeige beim Debuggen von F #-Typen zu verbessern</span><span class="sxs-lookup"><span data-stu-id="a2c56-253">These attributes are ignored in F# plain text formatting, but it can be useful to implement these methods to improve displays when debugging F# types.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2c56-254">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2c56-254">See also</span></span>

- [<span data-ttu-id="a2c56-255">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a2c56-255">Strings</span></span>](strings.md)
- [<span data-ttu-id="a2c56-256">Datensätze</span><span class="sxs-lookup"><span data-stu-id="a2c56-256">Records</span></span>](records.md)
- [<span data-ttu-id="a2c56-257">Unterscheidungs-Unions</span><span class="sxs-lookup"><span data-stu-id="a2c56-257">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="a2c56-258">F# Interactive</span><span class="sxs-lookup"><span data-stu-id="a2c56-258">F# Interactive</span></span>](fsharp-interactive-options.md)
