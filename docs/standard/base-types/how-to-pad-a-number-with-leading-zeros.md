---
title: 'Gewusst wie: Auffüllen einer Zahl mit führenden Nullen'
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ce3b59db027ffebf616a035b018629cb7aed30c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569771"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="893ad-102">Gewusst wie: Auffüllen einer Zahl mit führenden Nullen</span><span class="sxs-lookup"><span data-stu-id="893ad-102">How to: Pad a Number with Leading Zeros</span></span>
<span data-ttu-id="893ad-103">Führende Nullen können Sie mithilfe der [numerischen Standardformatzeichenfolge](../../../docs/standard/base-types/standard-numeric-format-strings.md) „D“ zusammen mit einem Genauigkeitsbezeichner zu einer Ganzzahl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="893ad-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="893ad-104">Ganz- und Gleitkommazahlen können Sie führende Nullen mithilfe einer [benutzerdefinierten numerischen Formatzeichenfolge](../../../docs/standard/base-types/custom-numeric-format-strings.md) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="893ad-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="893ad-105">In diesem Thema lernen Sie beide Methoden zum Auffüllen einer Zahl mit führenden Nullen kennen.</span><span class="sxs-lookup"><span data-stu-id="893ad-105">This topic shows how to use both methods to pad a number with leading zeros.</span></span>  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="893ad-106">Ganzzahl bis zu einer bestimmten Länge mit führenden Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="893ad-106">To pad an integer with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="893ad-107">Bestimmen Sie die Mindestanzahl an Ziffern, die der Ganzzahlwert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="893ad-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="893ad-108">Schließen Sie alle führenden Ziffern in diese Zahl ein.</span><span class="sxs-lookup"><span data-stu-id="893ad-108">Include any leading digits in this number.</span></span>  
  
2.  <span data-ttu-id="893ad-109">Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="893ad-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>  
  
    -   <span data-ttu-id="893ad-110">Um sie als Dezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge "D*n*" als Wert des `format`-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="893ad-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
    -   <span data-ttu-id="893ad-111">Um sie als Hexadezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge "X*n*" als Wert des `format`-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="893ad-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
     <span data-ttu-id="893ad-112">Sie können die Formatzeichenfolge auch in einer Methode wie <xref:System.String.Format%2A> oder <xref:System.Console.WriteLine%2A> verwenden, die die [kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="893ad-112">You can also use the format string in a method, such as <xref:System.String.Format%2A> or <xref:System.Console.WriteLine%2A>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="893ad-113">Im folgenden Beispiel sind mehrere Ganzzahlwerte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Zeichen beträgt.</span><span class="sxs-lookup"><span data-stu-id="893ad-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="893ad-114">Ganzzahl mit einer bestimmten Anzahl führender Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="893ad-114">To pad an integer with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="893ad-115">Bestimmen Sie, wie viele führende Nullen der Ganzzahlwert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="893ad-115">Determine how many leading zeros you want the integer value to display.</span></span>  
  
2.  <span data-ttu-id="893ad-116">Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="893ad-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span> <span data-ttu-id="893ad-117">Zum Formatieren der Ganzzahl als Dezimalwert benötigen Sie den Standardformatbezeichner "D", für einen Hexadezimalwert benötigen Sie den Standardformatbezeichner "X".</span><span class="sxs-lookup"><span data-stu-id="893ad-117">Formatting it as a decimal value requires that you use the "D" standard format specifier; formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>  
  
3.  <span data-ttu-id="893ad-118">Bestimmen Sie die Länge der noch nicht mit Nullen aufgefüllten numerischen Zeichenfolge, indem Sie die `ToString("D").Length`- oder die `ToString("X").Length`-Methode des Ganzzahlwerts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="893ad-118">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>  
  
4.  <span data-ttu-id="893ad-119">Fügen Sie die Anzahl der führenden Nullen, die in die formatierte Zeichenfolge eingefügt werden sollen, zur Länge der nicht aufgefüllten numerischen Zeichenfolge hinzu.</span><span class="sxs-lookup"><span data-stu-id="893ad-119">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="893ad-120">Dies ergibt die Gesamtlänge der mit Nullen aufgefüllten Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="893ad-120">This defines the total length of the padded string.</span></span>  
  
5.  <span data-ttu-id="893ad-121">Rufen Sie die `ToString(String)`-Methode des Ganzzahlwerts auf, und übergeben Sie die Zeichenfolge „D*n*“ für Dezimalzeichenfolgen und „X*n*“ für Hexadezimalzeichenfolgen, wobei *n* die Gesamtlänge der aufgefüllten Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="893ad-121">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="893ad-122">Sie können die Formatzeichenfolge „D*n*“ oder „X*n*“ auch in Methoden verwenden, die die kombinierte Formatierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="893ad-122">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="893ad-123">Im folgenden Beispiel wird ein Ganzzahlwert mit fünf führenden Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="893ad-123">The following example pads an integer value with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="893ad-124">Numerischen Wert bis zu einer bestimmten Länge mit führenden Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="893ad-124">To pad a numeric value with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="893ad-125">Bestimmen Sie, über wie viele Ziffern links des Dezimaltrennzeichens die Zeichenfolgendarstellung der Zahl verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="893ad-125">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="893ad-126">Schließen Sie alle führenden Nullen in diese Gesamtzahl der Ziffern ein.</span><span class="sxs-lookup"><span data-stu-id="893ad-126">Include any leading zeros in this total number of digits.</span></span>  
  
2.  <span data-ttu-id="893ad-127">Definieren Sie eine benutzerdefinierte numerische Formatzeichenfolge, in der die Mindestanzahl an Nullen mit dem Null-Platzhalter ("0") dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="893ad-127">Define a custom numeric format string that uses the zero placeholder ("0") to represent the minimum number of zeros.</span></span>  
  
3.  <span data-ttu-id="893ad-128">Rufen Sie die `ToString(String)`-Methode der Zahl auf und übergeben sie die benutzerdefinierte Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="893ad-128">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="893ad-129">Sie können die benutzerdefinierte Formatzeichenfolge auch mit Methoden verwenden, die kombinierte Formatierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="893ad-129">You can also use the custom format string with a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="893ad-130">Im folgenden Beispiel sind mehrere numerische Werte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Ziffern links des Dezimaltrennzeichens beträgt.</span><span class="sxs-lookup"><span data-stu-id="893ad-130">The following example formats several numeric values with leading zeros so that the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="893ad-131">Numerischen Wert mit einer bestimmten Anzahl führender Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="893ad-131">To pad a numeric value with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="893ad-132">Bestimmen Sie, über wie viele führende Nullen der numerische Wert verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="893ad-132">Determine how many leading zeros you want the numeric value to have.</span></span>  
  
2.  <span data-ttu-id="893ad-133">Bestimmen Sie die Anzahl der Ziffern links des Dezimaltrennzeichens in der nicht aufgefüllten numerischen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="893ad-133">Determine the number of digits to the left of the decimal in the unpadded numeric string.</span></span> <span data-ttu-id="893ad-134">Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="893ad-134">To do this:</span></span>  
  
    1.  <span data-ttu-id="893ad-135">Bestimmen Sie, ob die Zeichenfolgendarstellung der Zahl ein Symbol für das Dezimaltrennzeichen beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="893ad-135">Determine whether the string representation of a number includes a decimal point symbol.</span></span>  
  
    2.  <span data-ttu-id="893ad-136">Wenn sie ein Dezimaltrennzeichen enthält, bestimmen Sie die Anzahl der Zeichen links des Dezimaltrennzeichens.</span><span class="sxs-lookup"><span data-stu-id="893ad-136">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>  
  
         <span data-ttu-id="893ad-137">- oder - </span><span class="sxs-lookup"><span data-stu-id="893ad-137">-or-</span></span>  
  
         <span data-ttu-id="893ad-138">Wenn sie kein Dezimaltrennzeichen enthält, bestimmen Sie die Länge der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="893ad-138">If it does not include a decimal point symbol, determine the string's length.</span></span>  
  
3.  <span data-ttu-id="893ad-139">Erstellen Sie eine benutzerdefinierte Formatzeichenfolge, in der die gewünschte Anzahl führender Nullen in der Zeichenfolge mit dem Null-Platzhalter ("0") und die Ziffern in der Standardzeichenfolge mit dem Null-Platzhalter ("0") oder dem Ziffernplatzhalter ("#") angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="893ad-139">Create a custom format string that uses the zero placeholder ("0") for each of the leading zeros to appear in the string, and that uses either the zero placeholder or the digit placeholder ("#") to represent each digit in the default string.</span></span>  
  
4.  <span data-ttu-id="893ad-140">Übergeben Sie die benutzerdefinierte Formatzeichenfolge als Parameter an die `ToString(String)`-Methode der Zahl oder an eine Methode, die kombinierte Formatierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="893ad-140">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="893ad-141">Im folgenden Beispiel werden zwei <xref:System.Double>-Werte mit fünf führenden Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="893ad-141">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="893ad-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="893ad-142">See Also</span></span>  
 [<span data-ttu-id="893ad-143">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="893ad-143">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)  
 [<span data-ttu-id="893ad-144">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="893ad-144">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)  
 [<span data-ttu-id="893ad-145">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="893ad-145">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
