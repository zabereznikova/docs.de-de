---
title: Verwendung von Enumerationen (Visual Basic) | Microsoft-Dokumentation
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
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
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
ms.openlocfilehash: 3853950382fd4336c569f9d772aea3c1312f2ebc
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="8952a-102">Situationen für die Verwendung von Enumerationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8952a-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="8952a-103">Enumerationen bieten eine einfache Möglichkeit zum Arbeiten mit Gruppen verwandter Konstanten.</span><span class="sxs-lookup"><span data-stu-id="8952a-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="8952a-104">Eine Enumeration oder `Enum`, ein symbolischer Namen für einen Satz von Werten ist.</span><span class="sxs-lookup"><span data-stu-id="8952a-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="8952a-105">Enumerationen werden als Datentypen behandelt, und Sie können diese Konstanten für die Verwendung mit Variablen und Eigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="8952a-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="8952a-106">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8952a-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="8952a-107">Wenn eine Prozedur eine begrenzte Menge von Variablen annimmt, sollten erwägen Sie, eine Enumeration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8952a-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="8952a-108">Enumerationen stellen für Code besser lesbar, insbesondere wenn aussagekräftige Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8952a-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="8952a-109">Die Verwendung von Enumerationen hat folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="8952a-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="8952a-110">Fehler aufgrund eines vertauschen oder falsch eingegebene Zahlen wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="8952a-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="8952a-111">Erleichtert die Werte in der Zukunft ändern.</span><span class="sxs-lookup"><span data-stu-id="8952a-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="8952a-112">Ist der Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler einschleichen können.</span><span class="sxs-lookup"><span data-stu-id="8952a-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="8952a-113">Sicherstellung der Vorwärtskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="8952a-113">Ensures forward compatibility.</span></span> <span data-ttu-id="8952a-114">Mit Enumerationen ist der Code weniger wahrscheinlich fehlschlägt, wenn jemand die Namen der entsprechenden Werte ändert.</span><span class="sxs-lookup"><span data-stu-id="8952a-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="8952a-115">Benennen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8952a-115">Naming Enumerations</span></span>  
 <span data-ttu-id="8952a-116">Verwenden Sie eine Namenskonvention für Enumerationsmember.</span><span class="sxs-lookup"><span data-stu-id="8952a-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="8952a-117">Wenn [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen Enumerationsmembernamen trifft möglicherweise eine Ausnahme ausgelöst, falls andere Typbibliotheken, auf die verwiesen wird, denselben Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8952a-117">When [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="8952a-118">Verwenden Sie ein eindeutiges Präfix an, das die Werte aus der Anwendung oder Komponente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8952a-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="8952a-119">In Bezug auf einen Member einer Enumeration Sie müssen den Membernamen mit dem Enumerationsnamen qualifizieren, da sonst verwenden die `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8952a-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="8952a-120">Weitere Informationen finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="8952a-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="8952a-121">Vordefinierte Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8952a-121">Predefined Enumerations</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8952a-122">Stellt eine Reihe vordefinierter Enumerationen bereit, z. B. `FirstDayOfWeek` und `MsgBoxResul`t, um Ihren Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="8952a-122"> provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResul`t, to facilitate your code.</span></span> <span data-ttu-id="8952a-123">Eine Liste dieser finden Sie unter [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="8952a-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8952a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8952a-124">See Also</span></span>  
 <span data-ttu-id="8952a-125">[Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="8952a-125">[How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="8952a-126"> [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="8952a-126"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="8952a-127"> [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="8952a-127"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="8952a-128"> [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="8952a-128"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="8952a-129"> [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="8952a-129"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="8952a-130"> [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8952a-130"> [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="8952a-131"> [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="8952a-131"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
