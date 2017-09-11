---
title: Sonstige Datentypen (Visual Basic) | Microsoft-Dokumentation
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
- Object data type, data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
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
ms.openlocfilehash: ed7b61a5ec57ff85347f2c257e321ab9ec425274
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="771a6-102">Sonstige Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="771a6-102">Miscellaneous Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="771a6-103">bietet verschiedene Datentypen, die nicht auf Zahlen oder Zeichen ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="771a6-103"> supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="771a6-104">Stattdessen behandeln sie spezielle Daten wie z. B. Ja/Nein-Werte, Datum/Uhrzeit-Werte und Objekt-Adressen.</span><span class="sxs-lookup"><span data-stu-id="771a6-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="771a6-105">Eine Tabelle mit einer Side-by-Side-Vergleich der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen finden Sie in [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="771a6-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="771a6-106">Boolean-Typ</span><span class="sxs-lookup"><span data-stu-id="771a6-106">Boolean Type</span></span>  
 <span data-ttu-id="771a6-107">Die [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) ist ein Wert ohne Vorzeichen, der entweder als interpretiert wird `True` oder `False`.</span><span class="sxs-lookup"><span data-stu-id="771a6-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="771a6-108">Die Datenbreite hängt von der implementierenden Plattform ab.</span><span class="sxs-lookup"><span data-stu-id="771a6-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="771a6-109">Wenn eine Variable nur zwei Werten wie z. B. wahr/falsch, Ja/Nein oder ein/aus enthalten kann kann, deklarieren Sie es als `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="771a6-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="771a6-110">Date-Typ</span><span class="sxs-lookup"><span data-stu-id="771a6-110">Date Type</span></span>  
 <span data-ttu-id="771a6-111">Die [Date-Datentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md) ist ein 64-Bit-Wert, der Datum und Uhrzeit enthält.</span><span class="sxs-lookup"><span data-stu-id="771a6-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="771a6-112">Jedes Inkrement stellt 100 Nanosekunden verstrichene Zeit seit dem Beginn (00:00 Uhr) des 1. Januar des Jahres 1 im gregorianischen Kalender dar.</span><span class="sxs-lookup"><span data-stu-id="771a6-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="771a6-113">Wenn eine Variable einen Datumswert und/oder eine Uhrzeitwert enthalten kann, deklarieren Sie es als `Date`.</span><span class="sxs-lookup"><span data-stu-id="771a6-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="771a6-114">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="771a6-114">Object Type</span></span>  
 <span data-ttu-id="771a6-115">Die [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) ist eine 32-Bit-Adresse, die auf eine Objektinstanz innerhalb Ihrer Anwendung oder in einer anderen Anwendung verweist.</span><span class="sxs-lookup"><span data-stu-id="771a6-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="771a6-116">Ein `Object` Variable verweisen kann, auf ein beliebiges Objekt, das die Anwendung erkennt, oder auf Daten eines beliebigen Datentyps.</span><span class="sxs-lookup"><span data-stu-id="771a6-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="771a6-117">Dazu gehören *Werttypen*, wie z. B. `Integer`, `Boolean`, und Strukturinstanzen und *Verweistypen*, sind Instanzen von Objekten, die von Klassen erstellt haben, wie z. B. `String` und <xref:System.Windows.Forms.Form>, und array-Instanzen.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="771a6-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="771a6-118">Wenn eine Variable einen Zeiger auf eine Instanz einer Klasse speichert, die Sie zur Kompilierzeit nicht bekannt ist oder es auf Daten von verschiedenen Datentypen verweisen kann, deklarieren Sie sie als `Object`.</span><span class="sxs-lookup"><span data-stu-id="771a6-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="771a6-119">Der Vorteil der `Object` -Datentyp ist, Sie zum Speichern von Daten eines beliebigen Datentyps verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="771a6-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="771a6-120">Der Nachteil besteht darin, dass zusätzliche Operationen erforderlich sind, die weitere Ausführung Zeit in Anspruch nehmen und die Anwendung verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="771a6-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="771a6-121">Wenn Sie verwenden ein `Object` fallen-Variable für Werttypen, *Boxing* und *unboxing*.</span><span class="sxs-lookup"><span data-stu-id="771a6-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="771a6-122">Wenn Sie bei Verweistypen verwenden, fallen *spätes Binden*.</span><span class="sxs-lookup"><span data-stu-id="771a6-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="771a6-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="771a6-123">See Also</span></span>  
 <span data-ttu-id="771a6-124">[Typzeichen](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="771a6-124">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
<span data-ttu-id="771a6-125"> [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="771a6-125"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="771a6-126"> [Numerische Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="771a6-126"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="771a6-127"> [Zeichendatentypen](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="771a6-127"> [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span></span>  
<span data-ttu-id="771a6-128"> [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="771a6-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="771a6-129"> [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="771a6-129"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
