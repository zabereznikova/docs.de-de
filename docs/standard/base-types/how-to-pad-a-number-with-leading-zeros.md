---
title: 'Vorgehensweise: Auffüllen einer Zahl mit führenden Nullen'
description: Erfahren Sie, wie Sie eine Zahl mit führenden Nullen auffüllen. Fügen Sie führende Nullen zu ganzen Zahlen oder numerischen Werten bis zu einer bestimmten Gesamtlänge oder einer bestimmten Anzahl führender Nullen hinzu.
ms.date: 02/25/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
ms.openlocfilehash: 6ef0ddb37f1bc73254aa639d7c018ec6a01abd9b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447185"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="bccde-104">Vorgehensweise: Auffüllen einer Zahl mit führenden Nullen</span><span class="sxs-lookup"><span data-stu-id="bccde-104">How to: Pad a Number with Leading Zeros</span></span>

<span data-ttu-id="bccde-105">Führende Nullen können Sie mithilfe der [numerischen Standardformatzeichenfolge](standard-numeric-format-strings.md) „D“ zusammen mit einem Genauigkeitsbezeichner zu einer Ganzzahl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bccde-105">You can add leading zeros to an integer by using the "D" [standard numeric format string](standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="bccde-106">Ganz- und Gleitkommazahlen können Sie führende Nullen mithilfe einer [benutzerdefinierten numerischen Formatzeichenfolge](custom-numeric-format-strings.md) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bccde-106">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](custom-numeric-format-strings.md).</span></span> <span data-ttu-id="bccde-107">In diesem Artikel lernen Sie beide Methoden zum Auffüllen einer Zahl mit führenden Nullen kennen.</span><span class="sxs-lookup"><span data-stu-id="bccde-107">This article shows how to use both methods to pad a number with leading zeros.</span></span>

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="bccde-108">Ganzzahl bis zu einer bestimmten Länge mit führenden Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="bccde-108">To pad an integer with leading zeros to a specific length</span></span>

1. <span data-ttu-id="bccde-109">Bestimmen Sie die Mindestanzahl an Ziffern, die der Ganzzahlwert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="bccde-109">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="bccde-110">Schließen Sie alle führenden Ziffern in diese Zahl ein.</span><span class="sxs-lookup"><span data-stu-id="bccde-110">Include any leading digits in this number.</span></span>

1. <span data-ttu-id="bccde-111">Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bccde-111">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="bccde-112">Um sie als Dezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge "D*n*" als Wert des `format`-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="bccde-112">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>

    - <span data-ttu-id="bccde-113">Um die ganze Zahl als Hexadezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge „X*n*“ als Wert des format-Parameters, wobei *n* die Mindestlänge der Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="bccde-113">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the format parameter, where *n* represents the minimum length of the string.</span></span>

<span data-ttu-id="bccde-114">Sie können auch die Formatzeichenfolge in einer interpolierten Zeichenfolge sowohl in [C#](../../csharp/language-reference/tokens/interpolated.md) als auch [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) verwenden, oder Sie können eine Methode aufrufen, z. B. <xref:System.String.Format%2A?displayProperty=nameWithType> oder <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, die [kombinierte Formatierung](composite-formatting.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="bccde-114">You can also use the format string in an interpolated string in both [C#](../../csharp/language-reference/tokens/interpolated.md) and [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), or you can call a method, such as <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, that uses [composite formatting](composite-formatting.md).</span></span>

<span data-ttu-id="bccde-115">Im folgenden Beispiel sind mehrere Ganzzahlwerte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Zeichen beträgt.</span><span class="sxs-lookup"><span data-stu-id="bccde-115">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="bccde-116">Ganzzahl mit einer bestimmten Anzahl führender Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="bccde-116">To pad an integer with a specific number of leading zeros</span></span>

1. <span data-ttu-id="bccde-117">Bestimmen Sie, wie viele führende Nullen der Ganzzahlwert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="bccde-117">Determine how many leading zeros you want the integer value to display.</span></span>

1. <span data-ttu-id="bccde-118">Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bccde-118">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="bccde-119">Das Formatieren der Ganzzahl als Dezimalwert erfordert die Verwendung des Standardformatbezeichners „D“.</span><span class="sxs-lookup"><span data-stu-id="bccde-119">Formatting it as a decimal value requires that you use the "D" standard format specifier.</span></span>

    - <span data-ttu-id="bccde-120">Das Formatieren der Ganzzahl als Hexadezimalwert erfordert die Verwendung des Standardformatbezeichners „X“.</span><span class="sxs-lookup"><span data-stu-id="bccde-120">Formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>

1. <span data-ttu-id="bccde-121">Bestimmen Sie die Länge der noch nicht mit Nullen aufgefüllten numerischen Zeichenfolge, indem Sie die `ToString("D").Length`- oder die `ToString("X").Length`-Methode des Ganzzahlwerts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bccde-121">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>

1. <span data-ttu-id="bccde-122">Fügen Sie die Anzahl der führenden Nullen, die in die formatierte Zeichenfolge eingefügt werden sollen, zur Länge der nicht aufgefüllten numerischen Zeichenfolge hinzu.</span><span class="sxs-lookup"><span data-stu-id="bccde-122">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="bccde-123">Durch Hinzufügen der Anzahl der führenden Nullen wird die Gesamtlänge der aufgefüllten Zeichenfolge definiert.</span><span class="sxs-lookup"><span data-stu-id="bccde-123">Adding the number of leading zeros defines the total length of the padded string.</span></span>

1. <span data-ttu-id="bccde-124">Rufen Sie die `ToString(String)`-Methode des Ganzzahlwerts auf, und übergeben Sie die Zeichenfolge „D*n*“ für Dezimalzeichenfolgen und „X*n*“ für Hexadezimalzeichenfolgen, wobei *n* die Gesamtlänge der aufgefüllten Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="bccde-124">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="bccde-125">Sie können die Formatzeichenfolge „D*n*“ oder „X*n*“ auch in Methoden verwenden, die die kombinierte Formatierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bccde-125">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>

<span data-ttu-id="bccde-126">Im folgenden Beispiel wird ein Ganzzahlwert mit fünf führenden Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="bccde-126">The following example pads an integer value with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="bccde-127">Numerischen Wert bis zu einer bestimmten Länge mit führenden Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="bccde-127">To pad a numeric value with leading zeros to a specific length</span></span>

1. <span data-ttu-id="bccde-128">Bestimmen Sie, über wie viele Ziffern links des Dezimaltrennzeichens die Zeichenfolgendarstellung der Zahl verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="bccde-128">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="bccde-129">Schließen Sie alle führenden Nullen in diese Gesamtzahl der Ziffern ein.</span><span class="sxs-lookup"><span data-stu-id="bccde-129">Include any leading zeros in this total number of digits.</span></span>

1. <span data-ttu-id="bccde-130">Definieren Sie eine benutzerdefinierte numerische Formatzeichenfolge, in der die Mindestanzahl an Nullen mit dem Null-Platzhalter („0“) dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bccde-130">Define a custom numeric format string that uses the zero placeholder "0" to represent the minimum number of zeros.</span></span>

1. <span data-ttu-id="bccde-131">Rufen Sie die `ToString(String)`-Methode der Zahl auf und übergeben sie die benutzerdefinierte Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bccde-131">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="bccde-132">Sie können die benutzerdefinierte Formatzeichenfolge auch mit Zeichenfolgeninterpolation oder mit Methoden verwenden, die kombinierte Formatierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bccde-132">You can also use the custom format string with string interpolation or with a method that supports composite formatting.</span></span>

<span data-ttu-id="bccde-133">Im folgenden Beispiel werden mehrere numerische Werte mit führenden Nullen formatiert.</span><span class="sxs-lookup"><span data-stu-id="bccde-133">The following example formats several numeric values with leading zeros.</span></span> <span data-ttu-id="bccde-134">Daher beträgt die Gesamtlänge der formatierten Zahl links vom Dezimaltrennzeichen mindestens acht Ziffern.</span><span class="sxs-lookup"><span data-stu-id="bccde-134">As a result, the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="bccde-135">Numerischen Wert mit einer bestimmten Anzahl führender Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="bccde-135">To pad a numeric value with a specific number of leading zeros</span></span>

1. <span data-ttu-id="bccde-136">Bestimmen Sie, über wie viele führende Nullen der numerische Wert verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="bccde-136">Determine how many leading zeros you want the numeric value to have.</span></span>

1. <span data-ttu-id="bccde-137">Bestimmen Sie die Anzahl der Ziffern links des Dezimaltrennzeichens in der nicht aufgefüllten numerischen Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="bccde-137">Determine the number of digits to the left of the decimal in the unpadded numeric string:</span></span>

    1. <span data-ttu-id="bccde-138">Bestimmen Sie, ob die Zeichenfolgendarstellung der Zahl ein Symbol für das Dezimaltrennzeichen beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="bccde-138">Determine whether the string representation of a number includes a decimal point symbol.</span></span>

    1. <span data-ttu-id="bccde-139">Wenn sie ein Dezimaltrennzeichen enthält, bestimmen Sie die Anzahl der Zeichen links des Dezimaltrennzeichens.</span><span class="sxs-lookup"><span data-stu-id="bccde-139">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>

         <span data-ttu-id="bccde-140">- oder -</span><span class="sxs-lookup"><span data-stu-id="bccde-140">-or-</span></span>

         <span data-ttu-id="bccde-141">Wenn sie kein Dezimaltrennzeichen enthält, bestimmen Sie die Länge der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bccde-141">If it doesn't include a decimal point symbol, determine the string's length.</span></span>

1. <span data-ttu-id="bccde-142">Erstellen Sie eine benutzerdefinierte Formatzeichenfolge, die Folgendes verwendet:</span><span class="sxs-lookup"><span data-stu-id="bccde-142">Create a custom format string that uses:</span></span>

    - <span data-ttu-id="bccde-143">Den Nullplatzhalter „0“ für jede der führenden Nullen, die in der Zeichenfolge enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="bccde-143">The zero placeholder "0" for each of the leading zeros to appear in the string.</span></span>

    - <span data-ttu-id="bccde-144">Entweder den Nullplatzhalter oder den Ziffernplatzhalter „#“ zur Darstellung der einzelnen Ziffern in der Standardzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bccde-144">Either the zero placeholder or the digit placeholder "#" to represent each digit in the default string.</span></span>

1. <span data-ttu-id="bccde-145">Übergeben Sie die benutzerdefinierte Formatzeichenfolge als Parameter an die `ToString(String)`-Methode der Zahl oder an eine Methode, die kombinierte Formatierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bccde-145">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>

<span data-ttu-id="bccde-146">Im folgenden Beispiel werden zwei <xref:System.Double>-Werte mit fünf führenden Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="bccde-146">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="bccde-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bccde-147">See also</span></span>

- [<span data-ttu-id="bccde-148">Benutzerdefinierte Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="bccde-148">Custom Numeric Format Strings</span></span>](custom-numeric-format-strings.md)
- [<span data-ttu-id="bccde-149">Standardmäßige Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="bccde-149">Standard Numeric Format Strings</span></span>](standard-numeric-format-strings.md)
- [<span data-ttu-id="bccde-150">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="bccde-150">Composite Formatting</span></span>](composite-formatting.md)
