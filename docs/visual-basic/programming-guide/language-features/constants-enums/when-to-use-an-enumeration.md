---
title: "Situationen für die Verwendung von Enumerationen (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3b2937cc71c0c31bd8dce3d77fb33f48e1b5750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="0cd44-102">Situationen für die Verwendung von Enumerationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cd44-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="0cd44-103">Enumerationen bieten eine einfache Möglichkeit zum Arbeiten mit Gruppen verwandter Konstanten.</span><span class="sxs-lookup"><span data-stu-id="0cd44-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="0cd44-104">Eine Enumeration oder `Enum`, ist ein symbolischer Namen für einen Satz von Werten.</span><span class="sxs-lookup"><span data-stu-id="0cd44-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="0cd44-105">Enumerationen werden als Datentypen behandelt können, und sie Sätze von Konstanten für die Verwendung mit Variablen und Eigenschaften zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cd44-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="0cd44-106">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0cd44-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="0cd44-107">Wenn eine Prozedur eine begrenzte Anzahl von Variablen akzeptiert werden, sollten erwägen Sie, eine Enumeration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cd44-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="0cd44-108">Enumerationen stellen für Code besser lesbar, insbesondere dann, wenn Sie aussagekräftige Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cd44-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="0cd44-109">Vorteile der Verwendung von Enumerationen:</span><span class="sxs-lookup"><span data-stu-id="0cd44-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="0cd44-110">Fehler durch Transponieren oder falsch eingegebene Zahlen wird reduziert.</span><span class="sxs-lookup"><span data-stu-id="0cd44-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="0cd44-111">Vereinfacht die Werte in der Zukunft ändern.</span><span class="sxs-lookup"><span data-stu-id="0cd44-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="0cd44-112">Macht Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler einschleichen können.</span><span class="sxs-lookup"><span data-stu-id="0cd44-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="0cd44-113">Stellt Aufwärtskompatibilität sicher.</span><span class="sxs-lookup"><span data-stu-id="0cd44-113">Ensures forward compatibility.</span></span> <span data-ttu-id="0cd44-114">Mit Enumerationen ist der Code weniger wahrscheinlich, dass Sie einen Fehler, wenn in der Zukunft jemand die Namen der entsprechenden Werte ändert.</span><span class="sxs-lookup"><span data-stu-id="0cd44-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="0cd44-115">Benennen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0cd44-115">Naming Enumerations</span></span>  
 <span data-ttu-id="0cd44-116">Verwenden Sie eine Benennungskonvention für Enumerationsmember.</span><span class="sxs-lookup"><span data-stu-id="0cd44-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="0cd44-117">Wenn [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] trifft eine Enumeration der Elementname, eine Ausnahme wird möglicherweise ausgelöst, wenn andere Bibliotheken referenzierten Typ den gleichen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0cd44-117">When [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="0cd44-118">Verwenden Sie ein eindeutiges Präfix, das die Werte aus Ihrer Anwendung oder Komponente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0cd44-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="0cd44-119">Beim Verweisen auf einen Member einer Enumeration, Sie müssen den Membernamen mit dem Enumerationsnamen qualifizieren, da sonst verwenden die `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0cd44-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="0cd44-120">Weitere Informationen finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="0cd44-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="0cd44-121">Vordefinierte Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0cd44-121">Predefined Enumerations</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="0cd44-122">Stellt eine Reihe vordefinierter Enumerationen bereit, z. B. `FirstDayOfWeek` und `MsgBoxResult`, um Ihren Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="0cd44-122"> provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="0cd44-123">Eine Liste dieser finden Sie unter [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="0cd44-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd44-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cd44-124">See Also</span></span>  
 [<span data-ttu-id="0cd44-125">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="0cd44-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="0cd44-126">Gewusst wie: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="0cd44-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="0cd44-127">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="0cd44-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="0cd44-128">Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0cd44-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="0cd44-129">Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0cd44-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="0cd44-130">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0cd44-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="0cd44-131">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0cd44-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
