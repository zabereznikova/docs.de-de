---
title: 'Vorgehensweise: Auffüllen einer Zahl mit führenden Nullen'
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
ms.openlocfilehash: bc3c4b75c484274c214141d8fbfcf8ac592b0b99
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131978"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="86454-102">Vorgehensweise: Auffüllen einer Zahl mit führenden Nullen</span><span class="sxs-lookup"><span data-stu-id="86454-102">How to: Pad a Number with Leading Zeros</span></span>

<span data-ttu-id="86454-103">Führende Nullen können Sie mithilfe der [numerischen Standardformatzeichenfolge](../../../docs/standard/base-types/standard-numeric-format-strings.md) „D“ zusammen mit einem Genauigkeitsbezeichner zu einer Ganzzahl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="86454-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="86454-104">Ganz- und Gleitkommazahlen können Sie führende Nullen mithilfe einer [benutzerdefinierten numerischen Formatzeichenfolge](../../../docs/standard/base-types/custom-numeric-format-strings.md) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="86454-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="86454-105">In diesem Artikel lernen Sie beide Methoden zum Auffüllen einer Zahl mit führenden Nullen kennen.</span><span class="sxs-lookup"><span data-stu-id="86454-105">This article shows how to use both methods to pad a number with leading zeros.</span></span>

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="86454-106">Ganzzahl bis zu einer bestimmten Länge mit führenden Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="86454-106">To pad an integer with leading zeros to a specific length</span></span>

1. <span data-ttu-id="86454-107">Bestimmen Sie die Mindestanzahl an Ziffern, die der Ganzzahlwert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="86454-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="86454-108">Schließen Sie alle führenden Ziffern in diese Zahl ein.</span><span class="sxs-lookup"><span data-stu-id="86454-108">Include any leading digits in this number.</span></span>

1. <span data-ttu-id="86454-109">Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="86454-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="86454-110">Um sie als Dezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge "D*n*" als Wert des `format`-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="86454-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>

    - <span data-ttu-id="86454-111">Um die ganze Zahl als Hexadezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge „X*n*“ als Wert des format-Parameters, wobei *n* die Mindestlänge der Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="86454-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the format parameter, where *n* represents the minimum length of the string.</span></span>

<span data-ttu-id="86454-112">Sie können auch die Formatzeichenfolge in einer interpolierten Zeichenfolge sowohl in [C#](../../csharp/language-reference/tokens/interpolated.md) als auch [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) verwenden, oder Sie können eine Methode aufrufen, z. B. <xref:System.String.Format%2A?displayProperty=nameWithType> oder <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, die [kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="86454-112">You can also use the format string in an interpolated string in both [C#](../../csharp/language-reference/tokens/interpolated.md) and [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), or you can call a method, such as <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>

<span data-ttu-id="86454-113">Im folgenden Beispiel sind mehrere Ganzzahlwerte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Zeichen beträgt.</span><span class="sxs-lookup"><span data-stu-id="86454-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="86454-114">Ganzzahl mit einer bestimmten Anzahl führender Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="86454-114">To pad an integer with a specific number of leading zeros</span></span>

1. <span data-ttu-id="86454-115">Bestimmen Sie, wie viele führende Nullen der Ganzzahlwert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="86454-115">Determine how many leading zeros you want the integer value to display.</span></span>

1. <span data-ttu-id="86454-116">Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="86454-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="86454-117">Das Formatieren der Ganzzahl als Dezimalwert erfordert die Verwendung des Standardformatbezeichners „D“.</span><span class="sxs-lookup"><span data-stu-id="86454-117">Formatting it as a decimal value requires that you use the "D" standard format specifier.</span></span>

    - <span data-ttu-id="86454-118">Das Formatieren der Ganzzahl als Hexadezimalwert erfordert die Verwendung des Standardformatbezeichners „X“.</span><span class="sxs-lookup"><span data-stu-id="86454-118">Formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>

1. <span data-ttu-id="86454-119">Bestimmen Sie die Länge der noch nicht mit Nullen aufgefüllten numerischen Zeichenfolge, indem Sie die `ToString("D").Length`- oder die `ToString("X").Length`-Methode des Ganzzahlwerts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="86454-119">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>

1. <span data-ttu-id="86454-120">Fügen Sie die Anzahl der führenden Nullen, die in die formatierte Zeichenfolge eingefügt werden sollen, zur Länge der nicht aufgefüllten numerischen Zeichenfolge hinzu.</span><span class="sxs-lookup"><span data-stu-id="86454-120">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="86454-121">Durch Hinzufügen der Anzahl der führenden Nullen wird die Gesamtlänge der aufgefüllten Zeichenfolge definiert.</span><span class="sxs-lookup"><span data-stu-id="86454-121">Adding the number of leading zeros defines the total length of the padded string.</span></span>

1. <span data-ttu-id="86454-122">Rufen Sie die `ToString(String)`-Methode des Ganzzahlwerts auf, und übergeben Sie die Zeichenfolge „D*n*“ für Dezimalzeichenfolgen und „X*n*“ für Hexadezimalzeichenfolgen, wobei *n* die Gesamtlänge der aufgefüllten Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="86454-122">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="86454-123">Sie können die Formatzeichenfolge „D*n*“ oder „X*n*“ auch in Methoden verwenden, die die kombinierte Formatierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="86454-123">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>

<span data-ttu-id="86454-124">Im folgenden Beispiel wird ein Ganzzahlwert mit fünf führenden Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="86454-124">The following example pads an integer value with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="86454-125">Numerischen Wert bis zu einer bestimmten Länge mit führenden Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="86454-125">To pad a numeric value with leading zeros to a specific length</span></span>

1. <span data-ttu-id="86454-126">Bestimmen Sie, über wie viele Ziffern links des Dezimaltrennzeichens die Zeichenfolgendarstellung der Zahl verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="86454-126">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="86454-127">Schließen Sie alle führenden Nullen in diese Gesamtzahl der Ziffern ein.</span><span class="sxs-lookup"><span data-stu-id="86454-127">Include any leading zeros in this total number of digits.</span></span>

1. <span data-ttu-id="86454-128">Definieren Sie eine benutzerdefinierte numerische Formatzeichenfolge, in der die Mindestanzahl an Nullen mit dem Null-Platzhalter („0“) dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="86454-128">Define a custom numeric format string that uses the zero placeholder "0" to represent the minimum number of zeros.</span></span>

1. <span data-ttu-id="86454-129">Rufen Sie die `ToString(String)`-Methode der Zahl auf und übergeben sie die benutzerdefinierte Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="86454-129">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="86454-130">Sie können die benutzerdefinierte Formatzeichenfolge auch mit Zeichenfolgeninterpolation oder mit Methoden verwenden, die kombinierte Formatierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="86454-130">You can also use the custom format string with string interpolation or with a method that supports composite formatting.</span></span>

<span data-ttu-id="86454-131">Im folgenden Beispiel werden mehrere numerische Werte mit führenden Nullen formatiert.</span><span class="sxs-lookup"><span data-stu-id="86454-131">The following example formats several numeric values with leading zeros.</span></span> <span data-ttu-id="86454-132">Daher beträgt die Gesamtlänge der formatierten Zahl links vom Dezimaltrennzeichen mindestens acht Ziffern.</span><span class="sxs-lookup"><span data-stu-id="86454-132">As a result, the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="86454-133">Numerischen Wert mit einer bestimmten Anzahl führender Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="86454-133">To pad a numeric value with a specific number of leading zeros</span></span>

1. <span data-ttu-id="86454-134">Bestimmen Sie, über wie viele führende Nullen der numerische Wert verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="86454-134">Determine how many leading zeros you want the numeric value to have.</span></span>

1. <span data-ttu-id="86454-135">Bestimmen Sie die Anzahl der Ziffern links des Dezimaltrennzeichens in der nicht aufgefüllten numerischen Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="86454-135">Determine the number of digits to the left of the decimal in the unpadded numeric string:</span></span>

    1. <span data-ttu-id="86454-136">Bestimmen Sie, ob die Zeichenfolgendarstellung der Zahl ein Symbol für das Dezimaltrennzeichen beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="86454-136">Determine whether the string representation of a number includes a decimal point symbol.</span></span>

    1. <span data-ttu-id="86454-137">Wenn sie ein Dezimaltrennzeichen enthält, bestimmen Sie die Anzahl der Zeichen links des Dezimaltrennzeichens.</span><span class="sxs-lookup"><span data-stu-id="86454-137">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>

         <span data-ttu-id="86454-138">Oder</span><span class="sxs-lookup"><span data-stu-id="86454-138">-or-</span></span>

         <span data-ttu-id="86454-139">Wenn sie kein Dezimaltrennzeichen enthält, bestimmen Sie die Länge der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="86454-139">If it doesn't include a decimal point symbol, determine the string's length.</span></span>

1. <span data-ttu-id="86454-140">Erstellen Sie eine benutzerdefinierte Formatzeichenfolge, die Folgendes verwendet:</span><span class="sxs-lookup"><span data-stu-id="86454-140">Create a custom format string that uses:</span></span>

    - <span data-ttu-id="86454-141">Den Nullplatzhalter „0“ für jede der führenden Nullen, die in der Zeichenfolge enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="86454-141">The zero placeholder "0" for each of the leading zeros to appear in the string.</span></span>

    - <span data-ttu-id="86454-142">Entweder den Nullplatzhalter oder den Ziffernplatzhalter „#“ zur Darstellung der einzelnen Ziffern in der Standardzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="86454-142">Either the zero placeholder or the digit placeholder "#" to represent each digit in the default string.</span></span>

1. <span data-ttu-id="86454-143">Übergeben Sie die benutzerdefinierte Formatzeichenfolge als Parameter an die `ToString(String)`-Methode der Zahl oder an eine Methode, die kombinierte Formatierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="86454-143">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>

<span data-ttu-id="86454-144">Im folgenden Beispiel werden zwei <xref:System.Double>-Werte mit fünf führenden Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="86454-144">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="86454-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86454-145">See also</span></span>

- [<span data-ttu-id="86454-146">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="86454-146">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [<span data-ttu-id="86454-147">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="86454-147">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="86454-148">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="86454-148">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
