---
title: "Übersicht über Konstanten (Visual Basic) | Microsoft-Dokumentation"
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
- constants
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
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
ms.openlocfilehash: 2df21b9e3e814c654b355472aa645481060c6f68
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="a2e00-102">Übersicht über Konstanten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2e00-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="a2e00-103">Eine Konstante ist ein aussagekräftiger Name, der anstelle einer Zahl oder Zeichenfolge, die nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a2e00-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="a2e00-104">Konstanten speichern Werte, die, wie der Name schon sagt, während der Ausführung einer Anwendung unverändert bleiben.</span><span class="sxs-lookup"><span data-stu-id="a2e00-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="a2e00-105">Sie können erheblich verbessern die Lesbarkeit des Codes und zu verwalten, indem Sie mithilfe von Konstanten erleichtern.</span><span class="sxs-lookup"><span data-stu-id="a2e00-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="a2e00-106">In Code, der Werte enthält, die wieder verwenden oder das hängt vom bestimmte Zahlen, die schwer zu merken oder keine offensichtliche Bedeutung haben.</span><span class="sxs-lookup"><span data-stu-id="a2e00-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="a2e00-107">Gewusst wie: Erstellen und Verwenden von Konstanten</span><span class="sxs-lookup"><span data-stu-id="a2e00-107">How to Create and Use Constants</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="a2e00-108">enthält eine Reihe von vordefinierten Konstanten, die hauptsächlich zum Drucken und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2e00-108"> contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="a2e00-109">Sie können auch Ihre eigenen Konstanten durch Erstellen der `Const` Anweisung, verwenden Sie dieselben Richtlinien für die Erstellung eines Variablennamens.</span><span class="sxs-lookup"><span data-stu-id="a2e00-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="a2e00-110">Wenn `Option Strict` ist `On`, müssen Sie den Konstantentyp explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a2e00-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="a2e00-111">Der Gültigkeitsbereich einer Konstanten, die den Satz des gesamten Codes auf sie verweisen können, ohne dessen Namen zu qualifizieren, ist eine Variable, die am gleichen Speicherort identisch.</span><span class="sxs-lookup"><span data-stu-id="a2e00-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="a2e00-112">Um eine Konstante zu erstellen, die im Rahmen einer bestimmten Prozedur vorhanden ist, deklarieren sie innerhalb der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="a2e00-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="a2e00-113">Um eine Konstante zu erstellen, die innerhalb der gesamten Anwendung verfügbar ist, deklarieren Sie sie mithilfe der `Public` -Schlüsselwort in der Sie im Deklarationsabschnitt der Klasse.</span><span class="sxs-lookup"><span data-stu-id="a2e00-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2e00-114">Obwohl Konstanten etwas Variablen ähneln, nicht ändern oder neue Werte zuordnen wie Variablen.</span><span class="sxs-lookup"><span data-stu-id="a2e00-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="a2e00-115">Die Konstanten, die Sie in Ihrem Code verwenden, können das Objektmodell für Steuerelemente oder Komponenten definiert werden oder kann es sich um eine benutzerdefinierte (d. h. von Ihnen selbst erstellte).</span><span class="sxs-lookup"><span data-stu-id="a2e00-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="a2e00-116">Während der Kompilierung und Laufzeit-Konstanten</span><span class="sxs-lookup"><span data-stu-id="a2e00-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="a2e00-117">Eine Kompilierzeitkonstante wird zur Zeit berechnet, die der Code kompiliert wird, obwohl nur eine Konstante zur Laufzeit berechnet werden kann, während die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a2e00-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="a2e00-118">Eine Kompilierzeitkonstante haben den gleichen Wert jedes Mal, eine Anwendung ausgeführt wird, während eine Laufzeitkonstanten jedes Mal ändern kann.</span><span class="sxs-lookup"><span data-stu-id="a2e00-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="a2e00-119">Während der Kompilierung Konstanten sind z. B. Arraygrenzen, Case-Ausdrücke oder Enumerator Initialisierer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a2e00-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2e00-120">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a2e00-120">In This Section</span></span>  
  
|<span data-ttu-id="a2e00-121">Definition</span><span class="sxs-lookup"><span data-stu-id="a2e00-121">Definition</span></span>|<span data-ttu-id="a2e00-122">Begriff</span><span class="sxs-lookup"><span data-stu-id="a2e00-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="a2e00-123">Gewusst wie: Deklarieren einer Konstante</span><span class="sxs-lookup"><span data-stu-id="a2e00-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="a2e00-124">Erläutert, wie die `Const` -Anweisung zum Deklarieren einer Konstante und legen Sie seinen Wert; durch Deklarieren einer Konstante, weisen Sie einen aussagekräftigen Namen, dem Wert.</span><span class="sxs-lookup"><span data-stu-id="a2e00-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="a2e00-125">Benutzerdefinierte Konstanten</span><span class="sxs-lookup"><span data-stu-id="a2e00-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="a2e00-126">Beschreibt wie Sie Ihre eigenen Konstanten, einschließlich Informationen zum Gültigkeitsbereich zu erstellen und um Zirkelverweise zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a2e00-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="a2e00-127">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="a2e00-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="a2e00-128">Enthält Informationen darüber, wie der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Compiler Konstanten initialisiert, wenn `Option Explicit` deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="a2e00-128">Provides information on how the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="a2e00-129">Gewusst wie: Gruppieren verwandter konstanter Werte</span><span class="sxs-lookup"><span data-stu-id="a2e00-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="a2e00-130">Veranschaulicht, wie Konstante Werte gruppiert, die verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="a2e00-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="a2e00-131">Verweis</span><span class="sxs-lookup"><span data-stu-id="a2e00-131">Reference</span></span>  
  
|<span data-ttu-id="a2e00-132">Definition</span><span class="sxs-lookup"><span data-stu-id="a2e00-132">Definition</span></span>|<span data-ttu-id="a2e00-133">Begriff</span><span class="sxs-lookup"><span data-stu-id="a2e00-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="a2e00-134">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a2e00-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="a2e00-135">Listet die vordefinierten Konstanten [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2e00-135">Lists the constants predefined by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>|  
|[<span data-ttu-id="a2e00-136">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a2e00-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="a2e00-137">Beschreibt die `Const` Anweisung und deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="a2e00-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="a2e00-138">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a2e00-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="a2e00-139">Beschreibt die `Option Strict` Anweisung und deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="a2e00-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2e00-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2e00-140">See Also</span></span>  
 <span data-ttu-id="a2e00-141">[Übersicht über Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="a2e00-141">[Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="a2e00-142"> [Gewusst wie: Initialisieren einer Arrayvariablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span><span class="sxs-lookup"><span data-stu-id="a2e00-142"> [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
