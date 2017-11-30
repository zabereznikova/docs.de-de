---
title: "Gewusst wie: Auffüllen einer Zahl mit führenden Nullen"
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
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6266807a01e8119ae1410a1ba09cab55c788b4d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="fb241-102">Gewusst wie: Auffüllen einer Zahl mit führenden Nullen</span><span class="sxs-lookup"><span data-stu-id="fb241-102">How to: Pad a Number with Leading Zeros</span></span>
<span data-ttu-id="fb241-103">Führende Nullen können Sie mithilfe der [numerischen Standardformatzeichenfolge](../../../docs/standard/base-types/standard-numeric-format-strings.md) „D“ zusammen mit einem Genauigkeitsbezeichner zu einer Ganzzahl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb241-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="fb241-104">Ganz- und Gleitkommazahlen können Sie führende Nullen mithilfe einer [benutzerdefinierten numerischen Formatzeichenfolge](../../../docs/standard/base-types/custom-numeric-format-strings.md) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb241-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="fb241-105">In diesem Thema lernen Sie beide Methoden zum Auffüllen einer Zahl mit führenden Nullen kennen.</span><span class="sxs-lookup"><span data-stu-id="fb241-105">This topic shows how to use both methods to pad a number with leading zeros.</span></span>  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="fb241-106">Ganzzahl bis zu einer bestimmten Länge mit führenden Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="fb241-106">To pad an integer with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="fb241-107">Bestimmen Sie die Mindestanzahl an Ziffern, die der Ganzzahlwert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="fb241-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="fb241-108">Schließen Sie alle führenden Ziffern in diese Zahl ein.</span><span class="sxs-lookup"><span data-stu-id="fb241-108">Include any leading digits in this number.</span></span>  
  
2.  <span data-ttu-id="fb241-109">Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb241-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>  
  
    -   <span data-ttu-id="fb241-110">Um die Ganzzahl als Dezimalwert anzuzeigen, rufen seine `ToString(String)` -Methode und übergeben Sie die Zeichenfolge "D*n*" als Wert des der `format` -Parameter, in dem  *n*  die minimale Länge der Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="fb241-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
    -   <span data-ttu-id="fb241-111">Um die ganze Zahl als Hexadezimalwert anzuzeigen, rufen die `ToString(String)` -Methode und übergeben Sie die Zeichenfolge "X*n*" als Wert des der `format` -Parameter, in dem  *n*  die minimale Länge der Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="fb241-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
     <span data-ttu-id="fb241-112">Sie können auch die Formatzeichenfolge in einer Methode wie z. B. <xref:System.String.Format%2A> oder <xref:System.Console.WriteLine%2A>, verwendet [kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="fb241-112">You can also use the format string in a method, such as <xref:System.String.Format%2A> or <xref:System.Console.WriteLine%2A>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="fb241-113">Im folgenden Beispiel sind mehrere Ganzzahlwerte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Zeichen beträgt.</span><span class="sxs-lookup"><span data-stu-id="fb241-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="fb241-114">Ganzzahl mit einer bestimmten Anzahl führender Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="fb241-114">To pad an integer with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="fb241-115">Bestimmen Sie, wie viele führende Nullen der Ganzzahlwert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="fb241-115">Determine how many leading zeros you want the integer value to display.</span></span>  
  
2.  <span data-ttu-id="fb241-116">Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb241-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span> <span data-ttu-id="fb241-117">Zum Formatieren der Ganzzahl als Dezimalwert benötigen Sie den Standardformatbezeichner "D", für einen Hexadezimalwert benötigen Sie den Standardformatbezeichner "X".</span><span class="sxs-lookup"><span data-stu-id="fb241-117">Formatting it as a decimal value requires that you use the "D" standard format specifier; formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>  
  
3.  <span data-ttu-id="fb241-118">Bestimmen Sie die Länge der noch nicht mit Nullen aufgefüllten numerischen Zeichenfolge, indem Sie die `ToString("D").Length`- oder die `ToString("X").Length`-Methode des Ganzzahlwerts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fb241-118">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>  
  
4.  <span data-ttu-id="fb241-119">Fügen Sie die Anzahl der führenden Nullen, die in die formatierte Zeichenfolge eingefügt werden sollen, zur Länge der nicht aufgefüllten numerischen Zeichenfolge hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb241-119">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="fb241-120">Dies ergibt die Gesamtlänge der mit Nullen aufgefüllten Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fb241-120">This defines the total length of the padded string.</span></span>  
  
5.  <span data-ttu-id="fb241-121">Rufen Sie des Ganzzahlwerts `ToString(String)` -Methode und übergeben Sie die Zeichenfolge "D*n*" für Dezimalzeichenfolgen und "X*n*" für Hexadezimalzeichenfolgen, in dem  *n*  die Gesamtlänge der mit Nullen aufgefüllten Zeichenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="fb241-121">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="fb241-122">Sie können auch die "D*n*" oder "X*n*"-Formatzeichenfolge in eine Methode, die kombinierte Formatierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb241-122">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="fb241-123">Im folgenden Beispiel wird ein Ganzzahlwert mit fünf führenden Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fb241-123">The following example pads an integer value with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="fb241-124">Numerischen Wert bis zu einer bestimmten Länge mit führenden Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="fb241-124">To pad a numeric value with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="fb241-125">Bestimmen Sie, über wie viele Ziffern links des Dezimaltrennzeichens die Zeichenfolgendarstellung der Zahl verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="fb241-125">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="fb241-126">Schließen Sie alle führenden Nullen in diese Gesamtzahl der Ziffern ein.</span><span class="sxs-lookup"><span data-stu-id="fb241-126">Include any leading zeros in this total number of digits.</span></span>  
  
2.  <span data-ttu-id="fb241-127">Definieren Sie eine benutzerdefinierte numerische Formatzeichenfolge, in der die Mindestanzahl an Nullen mit dem Null-Platzhalter ("0") dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fb241-127">Define a custom numeric format string that uses the zero placeholder ("0") to represent the minimum number of zeros.</span></span>  
  
3.  <span data-ttu-id="fb241-128">Rufen Sie die `ToString(String)`-Methode der Zahl auf und übergeben sie die benutzerdefinierte Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fb241-128">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="fb241-129">Sie können die benutzerdefinierte Formatzeichenfolge auch mit Methoden verwenden, die kombinierte Formatierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb241-129">You can also use the custom format string with a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="fb241-130">Im folgenden Beispiel sind mehrere numerische Werte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Ziffern links des Dezimaltrennzeichens beträgt.</span><span class="sxs-lookup"><span data-stu-id="fb241-130">The following example formats several numeric values with leading zeros so that the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="fb241-131">Numerischen Wert mit einer bestimmten Anzahl führender Nullen auffüllen</span><span class="sxs-lookup"><span data-stu-id="fb241-131">To pad a numeric value with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="fb241-132">Bestimmen Sie, über wie viele führende Nullen der numerische Wert verfügen soll.</span><span class="sxs-lookup"><span data-stu-id="fb241-132">Determine how many leading zeros you want the numeric value to have.</span></span>  
  
2.  <span data-ttu-id="fb241-133">Bestimmen Sie die Anzahl der Ziffern links des Dezimaltrennzeichens in der nicht aufgefüllten numerischen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fb241-133">Determine the number of digits to the left of the decimal in the unpadded numeric string.</span></span> <span data-ttu-id="fb241-134">Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="fb241-134">To do this:</span></span>  
  
    1.  <span data-ttu-id="fb241-135">Bestimmen Sie, ob die Zeichenfolgendarstellung der Zahl ein Symbol für das Dezimaltrennzeichen beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="fb241-135">Determine whether the string representation of a number includes a decimal point symbol.</span></span>  
  
    2.  <span data-ttu-id="fb241-136">Wenn sie ein Dezimaltrennzeichen enthält, bestimmen Sie die Anzahl der Zeichen links des Dezimaltrennzeichens.</span><span class="sxs-lookup"><span data-stu-id="fb241-136">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>  
  
         <span data-ttu-id="fb241-137">- oder - </span><span class="sxs-lookup"><span data-stu-id="fb241-137">-or-</span></span>  
  
         <span data-ttu-id="fb241-138">Wenn sie kein Dezimaltrennzeichen enthält, bestimmen Sie die Länge der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fb241-138">If it does not include a decimal point symbol, determine the string's length.</span></span>  
  
3.  <span data-ttu-id="fb241-139">Erstellen Sie eine benutzerdefinierte Formatzeichenfolge, in der die gewünschte Anzahl führender Nullen in der Zeichenfolge mit dem Null-Platzhalter ("0") und die Ziffern in der Standardzeichenfolge mit dem Null-Platzhalter ("0") oder dem Ziffernplatzhalter ("#") angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fb241-139">Create a custom format string that uses the zero placeholder ("0") for each of the leading zeros to appear in the string, and that uses either the zero placeholder or the digit placeholder ("#") to represent each digit in the default string.</span></span>  
  
4.  <span data-ttu-id="fb241-140">Übergeben Sie die benutzerdefinierte Formatzeichenfolge als Parameter an die `ToString(String)`-Methode der Zahl oder an eine Methode, die kombinierte Formatierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb241-140">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="fb241-141">Im folgenden Beispiel werden zwei <xref:System.Double>-Werte mit fünf führenden Nullen aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fb241-141">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fb241-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb241-142">See Also</span></span>  
 [<span data-ttu-id="fb241-143">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="fb241-143">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)  
 [<span data-ttu-id="fb241-144">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="fb241-144">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)  
 [<span data-ttu-id="fb241-145">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="fb241-145">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
