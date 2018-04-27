---
title: Sonstige Datentypen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f80aacccab4c215b3e3917cc73097080aa6b9941
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="miscellaneous-data-types-visual-basic"></a><span data-ttu-id="47a6e-102">Sonstige Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47a6e-102">Miscellaneous Data Types (Visual Basic)</span></span>
<span data-ttu-id="47a6e-103">Visual Basic bietet verschiedene Datentypen, die nicht auf Zahlen oder Zeichen ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="47a6e-103">Visual Basic supplies several data types that are not oriented toward numbers or characters.</span></span> <span data-ttu-id="47a6e-104">Stattdessen verarbeiten sie spezielle Daten wie z. B. Ja/Nein-Werte, Datums-/Uhrzeitwerte und Objekt-Adressen.</span><span class="sxs-lookup"><span data-stu-id="47a6e-104">Instead, they deal with specialized data such as yes/no values, date/time values, and object addresses.</span></span>  
  
 <span data-ttu-id="47a6e-105">Eine Tabelle mit einer Seite-an-Seite-Vergleich der Visual Basic-Datentypen, finden Sie unter [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="47a6e-105">For a table showing a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="boolean-type"></a><span data-ttu-id="47a6e-106">Boolean-Typ</span><span class="sxs-lookup"><span data-stu-id="47a6e-106">Boolean Type</span></span>  
 <span data-ttu-id="47a6e-107">Die [booleschen Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) ist ein Wert ohne Vorzeichen, die entweder als interpretiert wird `True` oder `False`.</span><span class="sxs-lookup"><span data-stu-id="47a6e-107">The [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) is an unsigned value that is interpreted as either `True` or `False`.</span></span> <span data-ttu-id="47a6e-108">Die Breite hängt von der implementierenden Plattform ab.</span><span class="sxs-lookup"><span data-stu-id="47a6e-108">Its data width depends on the implementing platform.</span></span> <span data-ttu-id="47a6e-109">Wenn eine Variable Ja/Nein, oder ein/aus nur zwei Status Werte wie wahr/falsch, enthalten kann, deklarieren Sie es als `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="47a6e-109">If a variable can contain only two-state values such as true/false, yes/no, or on/off, declare it as `Boolean`.</span></span>  
  
## <a name="date-type"></a><span data-ttu-id="47a6e-110">Date-Typ</span><span class="sxs-lookup"><span data-stu-id="47a6e-110">Date Type</span></span>  
 <span data-ttu-id="47a6e-111">Die [Datumsdatentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md) ist ein 64-Bit-Wert, der Datums-und Uhrzeitinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="47a6e-111">The [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) is a 64-bit value that holds both date and time information.</span></span> <span data-ttu-id="47a6e-112">Jedes Inkrement stellt 100 Nanosekunden verstrichener Zeit seit dem Beginn (00:00 Uhr) des 1. Januar des Jahres 1 im gregorianischen Kalender dar.</span><span class="sxs-lookup"><span data-stu-id="47a6e-112">Each increment represents 100 nanoseconds of elapsed time since the beginning (12:00 AM) of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="47a6e-113">Wenn eine Variable einen Datumswert und/oder einen Time-Wert enthalten kann, deklarieren Sie es als `Date`.</span><span class="sxs-lookup"><span data-stu-id="47a6e-113">If a variable can contain a date value, a time value, or both, declare it as `Date`.</span></span>  
  
## <a name="object-type"></a><span data-ttu-id="47a6e-114">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="47a6e-114">Object Type</span></span>  
 <span data-ttu-id="47a6e-115">Die [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) ist eine 32-Bit-Adresse, die auf eine Objektinstanz innerhalb der Anwendung oder in einer anderen Anwendung verweist.</span><span class="sxs-lookup"><span data-stu-id="47a6e-115">The [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) is a 32-bit address that points to an object instance within your application or in some other application.</span></span> <span data-ttu-id="47a6e-116">Ein `Object` Variable verweisen kann, auf ein beliebiges Objekt, das die Anwendung erkennt, oder klicken Sie auf Daten eines beliebigen Datentyps.</span><span class="sxs-lookup"><span data-stu-id="47a6e-116">An `Object` variable can refer to any object your application recognizes, or to data of any data type.</span></span> <span data-ttu-id="47a6e-117">Dies schließt sowohl *Werttypen*, wie z. B. `Integer`, `Boolean`, und Strukturinstanzen und *Referenztypen*, wobei es sich um Instanzen von Objekten, z. B. von Klassen erstellt `String`und <xref:System.Windows.Forms.Form>, und die array-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="47a6e-117">This includes both *value types*, such as `Integer`, `Boolean`, and structure instances, and *reference types*, which are instances of objects created from classes such as `String` and <xref:System.Windows.Forms.Form>, and array instances.</span></span>  
  
 <span data-ttu-id="47a6e-118">Wenn eine Variable ein Zeiger auf eine Instanz einer Klasse gespeichert, die Sie zur Kompilierzeit nicht kennen oder es auf Daten von verschiedenen Datentypen verweisen kann, deklarieren Sie es als `Object`.</span><span class="sxs-lookup"><span data-stu-id="47a6e-118">If a variable stores a pointer to an instance of a class that you do not know at compile time, or if it can point to data of various data types, declare it as `Object`.</span></span>  
  
 <span data-ttu-id="47a6e-119">Der Vorteil der `Object` -Datentyp ist, dass Sie zum Speichern von Daten eines beliebigen Datentyps verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="47a6e-119">The advantage of the `Object` data type is that you can use it to store data of any data type.</span></span> <span data-ttu-id="47a6e-120">Der Nachteil ist, dass Sie zusätzliche Vorgänge verursacht, die weitere Ausführung Zeit in Anspruch nehmen, und stellen Ihre Anwendung langsamer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="47a6e-120">The disadvantage is that you incur extra operations that take more execution time and make your application perform slower.</span></span> <span data-ttu-id="47a6e-121">Bei Verwendung einer `Object` Variable für Werttypen anfallen *Boxing* und *unboxing*.</span><span class="sxs-lookup"><span data-stu-id="47a6e-121">If you use an `Object` variable for value types, you incur *boxing* and *unboxing*.</span></span> <span data-ttu-id="47a6e-122">Wenn Sie es für Verweistypen verwenden, verursachen *spätes Binden*.</span><span class="sxs-lookup"><span data-stu-id="47a6e-122">If you use it for reference types, you incur *late binding*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a6e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47a6e-123">See Also</span></span>  
 [<span data-ttu-id="47a6e-124">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="47a6e-124">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="47a6e-125">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="47a6e-125">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="47a6e-126">Numerische Datentypen</span><span class="sxs-lookup"><span data-stu-id="47a6e-126">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="47a6e-127">Zeichendatentypen</span><span class="sxs-lookup"><span data-stu-id="47a6e-127">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="47a6e-128">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="47a6e-128">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="47a6e-129">Frühes und spätes Binden</span><span class="sxs-lookup"><span data-stu-id="47a6e-129">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
