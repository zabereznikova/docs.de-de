---
title: Situationen für die Verwendung von Enumerationen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ab152687f4f9e4ba6bd032ae7c1352f65af715f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="f0b93-102">Situationen für die Verwendung von Enumerationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0b93-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="f0b93-103">Enumerationen bieten eine einfache Möglichkeit zum Arbeiten mit Gruppen verwandter Konstanten.</span><span class="sxs-lookup"><span data-stu-id="f0b93-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="f0b93-104">Eine Enumeration oder `Enum`, ist ein symbolischer Namen für einen Satz von Werten.</span><span class="sxs-lookup"><span data-stu-id="f0b93-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="f0b93-105">Enumerationen werden als Datentypen behandelt können, und sie Sätze von Konstanten für die Verwendung mit Variablen und Eigenschaften zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0b93-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="f0b93-106">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f0b93-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="f0b93-107">Wenn eine Prozedur eine begrenzte Anzahl von Variablen akzeptiert werden, sollten erwägen Sie, eine Enumeration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0b93-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="f0b93-108">Enumerationen stellen für Code besser lesbar, insbesondere dann, wenn Sie aussagekräftige Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0b93-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="f0b93-109">Vorteile der Verwendung von Enumerationen:</span><span class="sxs-lookup"><span data-stu-id="f0b93-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="f0b93-110">Fehler durch Transponieren oder falsch eingegebene Zahlen wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="f0b93-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="f0b93-111">Vereinfacht die Werte in der Zukunft ändern.</span><span class="sxs-lookup"><span data-stu-id="f0b93-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="f0b93-112">Macht Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler einschleichen können.</span><span class="sxs-lookup"><span data-stu-id="f0b93-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="f0b93-113">Stellt Aufwärtskompatibilität sicher.</span><span class="sxs-lookup"><span data-stu-id="f0b93-113">Ensures forward compatibility.</span></span> <span data-ttu-id="f0b93-114">Mit Enumerationen ist der Code weniger wahrscheinlich, dass Sie einen Fehler, wenn in der Zukunft jemand die Namen der entsprechenden Werte ändert.</span><span class="sxs-lookup"><span data-stu-id="f0b93-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="f0b93-115">Benennen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f0b93-115">Naming Enumerations</span></span>  
 <span data-ttu-id="f0b93-116">Verwenden Sie eine Benennungskonvention für Enumerationsmember.</span><span class="sxs-lookup"><span data-stu-id="f0b93-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="f0b93-117">Wenn in Visual Basic einen Enumerationsmembernamen auftritt, kann eine Ausnahme ausgelöst werden, wenn andere Bibliotheken referenzierten Typ den gleichen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f0b93-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="f0b93-118">Verwenden Sie ein eindeutiges Präfix, das die Werte aus Ihrer Anwendung oder Komponente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f0b93-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="f0b93-119">Beim Verweisen auf einen Member einer Enumeration, Sie müssen den Membernamen mit dem Enumerationsnamen qualifizieren, da sonst verwenden die `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f0b93-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="f0b93-120">Weitere Informationen finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="f0b93-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="f0b93-121">Vordefinierte Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f0b93-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="f0b93-122">Visual Basic bietet eine Reihe von vordefinierten Enumerationen, z. B. `FirstDayOfWeek` und `MsgBoxResult`, um Ihren Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f0b93-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="f0b93-123">Eine Liste dieser finden Sie unter [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="f0b93-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b93-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0b93-124">See Also</span></span>  
 [<span data-ttu-id="f0b93-125">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="f0b93-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="f0b93-126">Gewusst wie: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="f0b93-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="f0b93-127">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="f0b93-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="f0b93-128">Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0b93-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="f0b93-129">Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0b93-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="f0b93-130">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0b93-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="f0b93-131">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f0b93-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
