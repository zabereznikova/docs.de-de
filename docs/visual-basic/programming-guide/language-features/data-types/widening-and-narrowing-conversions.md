---
title: Erweiternde und eingrenzende Konvertierungen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- widening conversions
- narrowing conversions
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions, exceptions during conversion
- type conversion, exceptions during conversion
- conversions, data type
- conversions, narrowing
- type conversion, narrowing
- data type conversion, widening
- data type conversion, narrowing
- changing data types
- type conversion, widening
- data type conversion, exceptions during conversion
- conversions, widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c00db1c631e1cc71df856407e8646532a73c6d44
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="widening-and-narrowing-conversions-visual-basic"></a><span data-ttu-id="f89bb-102">Erweiternde und eingrenzende Konvertierungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f89bb-102">Widening and Narrowing Conversions (Visual Basic)</span></span>
<span data-ttu-id="f89bb-103">Ein wichtiger Aspekt mit einer Typumwandlung ist, ob das Ergebnis der Konvertierung innerhalb des Bereichs von den Zieldatentyp ist.</span><span class="sxs-lookup"><span data-stu-id="f89bb-103">An important consideration with a type conversion is whether the result of the conversion is within the range of the destination data type.</span></span>  
  
 <span data-ttu-id="f89bb-104">Ein *erweiternden Konvertierung* ändert einen Wert in einen Datentyp, der alle möglichen Werte der ursprünglichen Daten ermöglichen kann.</span><span class="sxs-lookup"><span data-stu-id="f89bb-104">A *widening conversion* changes a value to a data type that can allow for any possible value of the original data.</span></span>  <span data-ttu-id="f89bb-105">Erweiternde Konvertierungen Quellwert beibehalten, aber es können seine Darstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="f89bb-105">Widening conversions preserve the source value but can change its representation.</span></span> <span data-ttu-id="f89bb-106">Dies geschieht, wenn die Konvertierung von ganzzahligen Typen in `Decimal`, oder von `Char` auf `String`.</span><span class="sxs-lookup"><span data-stu-id="f89bb-106">This occurs if you convert from an integral type to `Decimal`, or from `Char` to `String`.</span></span>  
  
 <span data-ttu-id="f89bb-107">Eine *einschränkende* Konvertierung ändert einen Wert in einen Datentyp, der möglicherweise nicht in der Lage ist, alle möglichen Werte zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f89bb-107">A *narrowing conversion* changes a value to a data type that might not be able to hold some of the possible values.</span></span> <span data-ttu-id="f89bb-108">Beispielsweise wird ein Dezimalstellenwert gerundet, bei der Konvertierung in einen ganzzahligen Typ und einen numerischen Typ konvertiert wird, um `Boolean` wird entweder reduziert `True` oder `False`.</span><span class="sxs-lookup"><span data-stu-id="f89bb-108">For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to `Boolean` is reduced to either `True` or `False`.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="f89bb-109">Erweiternde Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="f89bb-109">Widening Conversions</span></span>  
 <span data-ttu-id="f89bb-110">Die folgende Tabelle zeigt die Standard-erweiternde Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="f89bb-110">The following table shows the standard widening conversions.</span></span>  
  
|<span data-ttu-id="f89bb-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f89bb-111">Data type</span></span>|<span data-ttu-id="f89bb-112">Erweiterung in Datentypen <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f89bb-112">Widens to data types <sup>1</sup></span></span>|  
|---|---|  
|[<span data-ttu-id="f89bb-113">SByte</span><span class="sxs-lookup"><span data-stu-id="f89bb-113">SByte</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="f89bb-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="f89bb-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="f89bb-115">Byte</span><span class="sxs-lookup"><span data-stu-id="f89bb-115">Byte</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="f89bb-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="f89bb-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="f89bb-117">Kurze</span><span class="sxs-lookup"><span data-stu-id="f89bb-117">Short</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="f89bb-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="f89bb-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="f89bb-119">UShort</span><span class="sxs-lookup"><span data-stu-id="f89bb-119">UShort</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="f89bb-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="f89bb-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="f89bb-121">Ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="f89bb-121">Integer</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="f89bb-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f89bb-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="f89bb-123">UInteger</span><span class="sxs-lookup"><span data-stu-id="f89bb-123">UInteger</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="f89bb-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f89bb-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="f89bb-125">Lange</span><span class="sxs-lookup"><span data-stu-id="f89bb-125">Long</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="f89bb-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f89bb-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="f89bb-127">Ulong-Typ</span><span class="sxs-lookup"><span data-stu-id="f89bb-127">ULong</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="f89bb-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f89bb-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="f89bb-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="f89bb-129">Decimal</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="f89bb-130">`Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f89bb-130">`Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="f89bb-131">Single</span><span class="sxs-lookup"><span data-stu-id="f89bb-131">Single</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="f89bb-132">`Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="f89bb-132">`Single`, `Double`</span></span>|  
|[<span data-ttu-id="f89bb-133">Double</span><span class="sxs-lookup"><span data-stu-id="f89bb-133">Double</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|<span data-ttu-id="f89bb-134">Beliebiger aufgelisteter Typ ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="f89bb-134">Any enumerated type ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span></span>|<span data-ttu-id="f89bb-135">Der zugrunde liegende ganzzahlige Typ und jeden Typ, der der zugrunde liegende Typ erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="f89bb-135">Its underlying integral type and any type to which the underlying type widens.</span></span>|  
|[<span data-ttu-id="f89bb-136">Char</span><span class="sxs-lookup"><span data-stu-id="f89bb-136">Char</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="f89bb-137">`Char`, `String`</span><span class="sxs-lookup"><span data-stu-id="f89bb-137">`Char`, `String`</span></span>|  
|<span data-ttu-id="f89bb-138">`Char`-Array</span><span class="sxs-lookup"><span data-stu-id="f89bb-138">`Char` array</span></span>|<span data-ttu-id="f89bb-139">`Char`Array`String`</span><span class="sxs-lookup"><span data-stu-id="f89bb-139">`Char` array, `String`</span></span>|  
|<span data-ttu-id="f89bb-140">Beliebiger Typ</span><span class="sxs-lookup"><span data-stu-id="f89bb-140">Any type</span></span>|[<span data-ttu-id="f89bb-141">Objekt</span><span class="sxs-lookup"><span data-stu-id="f89bb-141">Object</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|<span data-ttu-id="f89bb-142">Alle abgeleiteten Typ</span><span class="sxs-lookup"><span data-stu-id="f89bb-142">Any derived type</span></span>|<span data-ttu-id="f89bb-143">Alle Basistypen, die von der sie abgeleitet ist <sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="f89bb-143">Any base type from which it is derived <sup>3</sup>.</span></span>|  
|<span data-ttu-id="f89bb-144">Beliebiger Typ</span><span class="sxs-lookup"><span data-stu-id="f89bb-144">Any type</span></span>|<span data-ttu-id="f89bb-145">Eine Schnittstelle, die er implementiert.</span><span class="sxs-lookup"><span data-stu-id="f89bb-145">Any interface it implements.</span></span>|  
|[<span data-ttu-id="f89bb-146">Nothing</span><span class="sxs-lookup"><span data-stu-id="f89bb-146">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)|<span data-ttu-id="f89bb-147">Jeder Datentyp oder Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="f89bb-147">Any data type or object type.</span></span>|  
  
 <span data-ttu-id="f89bb-148"><sup>1</sup> per Definition jeder-Datentyp wird auf sich selbst.</span><span class="sxs-lookup"><span data-stu-id="f89bb-148"><sup>1</sup> By definition, every data type widens to itself.</span></span>  
  
 <span data-ttu-id="f89bb-149"><sup>2</sup> Konvertierungen von `Integer`, `UInteger`, `Long`, `ULong`, oder `Decimal` auf `Single` oder `Double` Verlust an Genauigkeit, aber nie in Verlust Größenordnung kommen.</span><span class="sxs-lookup"><span data-stu-id="f89bb-149"><sup>2</sup> Conversions from `Integer`, `UInteger`, `Long`, `ULong`, or `Decimal` to `Single` or `Double` might result in loss of precision, but never in loss of magnitude.</span></span> <span data-ttu-id="f89bb-150">In diesem Fall führen Sie kein Verlust von Informationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f89bb-150">In this sense they do not incur information loss.</span></span>  
  
 <span data-ttu-id="f89bb-151"><sup>3</sup> es vielleicht überraschend, dass eine Konvertierung von einem abgeleiteten Typ in einem seiner Basistypen erweitern ist.</span><span class="sxs-lookup"><span data-stu-id="f89bb-151"><sup>3</sup> It might seem surprising that a conversion from a derived type to one of its base types is widening.</span></span> <span data-ttu-id="f89bb-152">Die Ausrichtung ist, dass der abgeleitete Typ alle Member des Basistyps, enthält damit es als eine Instanz des Basistyps qualifiziert.</span><span class="sxs-lookup"><span data-stu-id="f89bb-152">The justification is that the derived type contains all the members of the base type, so it qualifies as an instance of the base type.</span></span> <span data-ttu-id="f89bb-153">In der entgegengesetzten Richtung enthält der Basistyp nicht vom abgeleiteten Typ definierten neuen Member.</span><span class="sxs-lookup"><span data-stu-id="f89bb-153">In the opposite direction, the base type does not contain any new members defined by the derived type.</span></span>  
  
 <span data-ttu-id="f89bb-154">Erweiternde Konvertierungen zur Laufzeit immer erfolgreich und nie Datenverlust verursachen.</span><span class="sxs-lookup"><span data-stu-id="f89bb-154">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="f89bb-155">Immer durchführen können sie implizit, ob die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) wird der Typ, wechseln Sie zur Prüfung `On` oder `Off`.</span><span class="sxs-lookup"><span data-stu-id="f89bb-155">You can always perform them implicitly, whether the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `On` or to `Off`.</span></span>  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="f89bb-156">Einschränkende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="f89bb-156">Narrowing Conversions</span></span>  
 <span data-ttu-id="f89bb-157">Die standardmäßigen einschränkenden Konvertierungen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f89bb-157">The standard narrowing conversions include the following:</span></span>  
  
-   <span data-ttu-id="f89bb-158">Die umgekehrte Richtung der erweiternden Konvertierungen in der vorherigen Tabelle (außer, dass jeder Typ selbst erweitert)</span><span class="sxs-lookup"><span data-stu-id="f89bb-158">The reverse directions of the widening conversions in the preceding table (except that every type widens to itself)</span></span>  
  
-   <span data-ttu-id="f89bb-159">Konvertierungen zwischen [boolesche](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) und alle numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="f89bb-159">Conversions in either direction between [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) and any numeric type</span></span>  
  
-   <span data-ttu-id="f89bb-160">Beim Konvertieren von numerischen Typ in einen Enumerationstyp (`Enum`)</span><span class="sxs-lookup"><span data-stu-id="f89bb-160">Conversions from any numeric type to any enumerated type (`Enum`)</span></span>  
  
-   <span data-ttu-id="f89bb-161">Konvertierungen zwischen [Zeichenfolge](../../../../visual-basic/language-reference/data-types/string-data-type.md) und alle numerischen Typen, `Boolean`, oder [Datum](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="f89bb-161">Conversions in either direction between [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) and any numeric type, `Boolean`, or [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span></span>  
  
-   <span data-ttu-id="f89bb-162">Geben Sie zur Konvertierung von einem Datentyp oder das Objekt um einen abgeleiteten Typ</span><span class="sxs-lookup"><span data-stu-id="f89bb-162">Conversions from a data type or object type to a type derived from it</span></span>  
  
 <span data-ttu-id="f89bb-163">Einschränkende Konvertierungen nicht immer erfolgreich zur Laufzeit und können fehlschlagen oder Datenverlust verursachen.</span><span class="sxs-lookup"><span data-stu-id="f89bb-163">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="f89bb-164">Ein Fehler tritt auf, wenn der Zieldatentyp nicht den konvertierten Wert empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="f89bb-164">An error occurs if the destination data type cannot receive the value being converted.</span></span> <span data-ttu-id="f89bb-165">Beispielsweise kann eine numerische Konvertierung zu einem Überlauf führen.</span><span class="sxs-lookup"><span data-stu-id="f89bb-165">For example, a numeric conversion can result in an overflow.</span></span> <span data-ttu-id="f89bb-166">Der Compiler lässt keine auszuführenden einschränkende Konvertierungen implizit, wenn Sie die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) legt die Schalter für die Typprüfung `Off`.</span><span class="sxs-lookup"><span data-stu-id="f89bb-166">The compiler does not allow you to perform narrowing conversions implicitly unless the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `Off`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f89bb-167">Der Fehler für einschränkende Konvertierung wird unterdrückt für Konvertierungen von den Elementen in einer `For Each…Next` -Auflistung, um die Schleifensteuerungsvariable.</span><span class="sxs-lookup"><span data-stu-id="f89bb-167">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="f89bb-168">Weitere Informationen und Beispiele finden Sie im Abschnitt "Einschränkende Konvertierungen" im [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f89bb-168">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="when-to-use-narrowing-conversions"></a><span data-ttu-id="f89bb-169">Einschränkende Konvertierungen verwenden</span><span class="sxs-lookup"><span data-stu-id="f89bb-169">When to Use Narrowing Conversions</span></span>  
 <span data-ttu-id="f89bb-170">Verwenden Sie eine einschränkende Konvertierung, wenn Sie wissen, dass der Quellwert in den Zieldatentyp ohne Fehler oder Datenverlust konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f89bb-170">You use a narrowing conversion when you know the source value can be converted to the destination data type without error or data loss.</span></span> <span data-ttu-id="f89bb-171">Angenommen, Sie haben eine `String` wissen Sie entweder "True" oder "False" enthält, können Sie die `CBool` Schlüsselwort umzuwandeln `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="f89bb-171">For example, if you have a `String` that you know contains either "True" or "False," you can use the `CBool` keyword to convert it to `Boolean`.</span></span>  
  
## <a name="exceptions-during-conversion"></a><span data-ttu-id="f89bb-172">Ausnahmen während der Konvertierung</span><span class="sxs-lookup"><span data-stu-id="f89bb-172">Exceptions During Conversion</span></span>  
 <span data-ttu-id="f89bb-173">Da immer erweiternde Konvertierungen erfolgreich ausgeführt werden, werden sie keine Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="f89bb-173">Because widening conversions always succeed, they do not throw exceptions.</span></span> <span data-ttu-id="f89bb-174">Die folgenden Ausnahmen einschränkende Konvertierungen, wenn sie sich nicht am häufigsten ausgelöst werden:</span><span class="sxs-lookup"><span data-stu-id="f89bb-174">Narrowing conversions, when they fail, most commonly throw the following exceptions:</span></span>  
  
-   <span data-ttu-id="f89bb-175"><xref:System.InvalidCastException>– Wenn keine Konvertierung zwischen den beiden Typen definiert ist</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="f89bb-175"><xref:System.InvalidCastException> — if no conversion is defined between the two types</span></span>  
  
-   <span data-ttu-id="f89bb-176"><xref:System.OverflowException>– (nur bei ganzzahligen Typen) Wenn der konvertierte Wert für den Zieltyp zu groß ist.</xref:System.OverflowException></span><span class="sxs-lookup"><span data-stu-id="f89bb-176"><xref:System.OverflowException> — (integral types only) if the converted value is too large for the target type</span></span>  
  
 <span data-ttu-id="f89bb-177">Wenn eine Klasse oder Struktur definiert ein [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) als Operator für die Konvertierung in oder aus dieser Klasse oder Struktur an, die `CType` geeignete Ausnahmen auslösen können.</span><span class="sxs-lookup"><span data-stu-id="f89bb-177">If a class or structure defines a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to serve as a conversion operator to or from that class or structure, that `CType` can throw any exception it deems appropriate.</span></span> <span data-ttu-id="f89bb-178">Darüber hinaus, `CType` Aufrufen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Funktionen oder [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] -Methoden, die wiederum verschiedene Ausnahmen auslösen können.</span><span class="sxs-lookup"><span data-stu-id="f89bb-178">In addition, that `CType` might call [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] functions or [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] methods, which in turn could throw a variety of exceptions.</span></span>  
  
## <a name="changes-during-reference-type-conversions"></a><span data-ttu-id="f89bb-179">Änderungen, die während der Verweis Typumwandlungen</span><span class="sxs-lookup"><span data-stu-id="f89bb-179">Changes During Reference Type Conversions</span></span>  
 <span data-ttu-id="f89bb-180">Eine Konvertierung von einem *Referenztyp* wird nur der Zeiger auf den Wert.</span><span class="sxs-lookup"><span data-stu-id="f89bb-180">A conversion from a *reference type* copies only the pointer to the value.</span></span> <span data-ttu-id="f89bb-181">Der Wert selbst werden nicht kopiert oder in keiner Weise geändert.</span><span class="sxs-lookup"><span data-stu-id="f89bb-181">The value itself is neither copied nor changed in any way.</span></span> <span data-ttu-id="f89bb-182">Das einzige, das ändern können ist der Datentyp der Variablen den Zeiger.</span><span class="sxs-lookup"><span data-stu-id="f89bb-182">The only thing that can change is the data type of the variable holding the pointer.</span></span> <span data-ttu-id="f89bb-183">Im folgenden Beispiel wird der Datentyp von deren Basisklasse aus der abgeleiteten Klasse konvertiert das Objekt, dem nun beide Variablen verweisen ist allerdings nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="f89bb-183">In the following example, the data type is converted from the derived class to its base class, but the object that both variables now point to is unchanged.</span></span>  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a><span data-ttu-id="f89bb-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f89bb-184">See Also</span></span>  
 <span data-ttu-id="f89bb-185">[Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="f89bb-185">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="f89bb-186"> [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="f89bb-186"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="f89bb-187"> [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="f89bb-187"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="f89bb-188"> [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span><span class="sxs-lookup"><span data-stu-id="f89bb-188"> [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span></span>  
<span data-ttu-id="f89bb-189"> [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="f89bb-189"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="f89bb-190"> [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="f89bb-190"> [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span></span>  
<span data-ttu-id="f89bb-191"> [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="f89bb-191"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="f89bb-192"> [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)</span><span class="sxs-lookup"><span data-stu-id="f89bb-192"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)</span></span>
