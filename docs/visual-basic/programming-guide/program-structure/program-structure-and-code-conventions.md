---
title: Programmstruktur und Codekonventionen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions [Visual Basic], Visual Basic
- programs [Visual Basic], structure
- program structure [Visual Basic]
- naming conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- Visual Basic code
- programming [Visual Basic], Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b38ba9623a20dcd1be4bc96f4aff1eb646b0a053
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="7c10d-102">Programmstruktur und Codekonventionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c10d-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="7c10d-103">In diesem Abschnitt werden die typische [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Programmstruktur eingeführt, das einfache [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Programm "Hello, World" vorgestellt und die Codekonventionen von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erörtert.</span><span class="sxs-lookup"><span data-stu-id="7c10d-103">This section introduces the typical [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program structure, provides a simple [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program, "Hello, World", and discusses [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code conventions.</span></span> <span data-ttu-id="7c10d-104">Codekonventionen sind Vorschläge, die sich nicht auf die Logik eines Programms, sondern auf seine physische Struktur und sein Erscheinungsbild konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="7c10d-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="7c10d-105">Wenn Sie diese Konventionen einhalten, ist Programmcode besser lesbar, leichter verständlich und einfacher zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="7c10d-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="7c10d-106">Codekonventionen umfassen u. a.:</span><span class="sxs-lookup"><span data-stu-id="7c10d-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="7c10d-107">Standardisierte Formate für Bezeichnungen und Kommentare im Code.</span><span class="sxs-lookup"><span data-stu-id="7c10d-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="7c10d-108">Richtlinien für die Verwendung von Leerzeichen, Formatierungen und Einzügen beim Code.</span><span class="sxs-lookup"><span data-stu-id="7c10d-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="7c10d-109">Benennungskonventionen für Objekte, Variablen und Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="7c10d-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="7c10d-110">Die folgenden Themen enthalten eine Reihe von Programmierungsrichtlinien für [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Programme und Beispiele für die richtige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="7c10d-110">The following topics present a set of programming guidelines for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c10d-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7c10d-111">In This Section</span></span>  
 [<span data-ttu-id="7c10d-112">Struktur eines Visual Basic-Programms</span><span class="sxs-lookup"><span data-stu-id="7c10d-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="7c10d-113">Bietet eine Übersicht über die Elemente, aus denen ein [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Programm besteht.</span><span class="sxs-lookup"><span data-stu-id="7c10d-113">Provides an overview of the elements that make up a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="7c10d-114">Main-Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7c10d-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="7c10d-115">Erörtert die Prozedur, die als Ausgangspunkt und Gesamtsteuerung für die Anwendung fungiert.</span><span class="sxs-lookup"><span data-stu-id="7c10d-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="7c10d-116">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7c10d-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="7c10d-117">Erläutert, wie auf Objekte in anderen Assemblys verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7c10d-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="7c10d-118">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7c10d-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="7c10d-119">Beschreibt, wie Namespaces Objekte innerhalb von Assemblys organisieren.</span><span class="sxs-lookup"><span data-stu-id="7c10d-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="7c10d-120">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="7c10d-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="7c10d-121">Umfasst allgemeine Richtlinien für die Benennung von Prozeduren, Konstanten, Variablen, Argumenten und Objekten.</span><span class="sxs-lookup"><span data-stu-id="7c10d-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="7c10d-122">Visual Basic-Codierungskonventionen</span><span class="sxs-lookup"><span data-stu-id="7c10d-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="7c10d-123">Erläutert die Richtlinien, die beim Entwickeln der Beispiele in dieser Dokumentation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="7c10d-124">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="7c10d-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="7c10d-125">Beschreibt die selektive Kompilierung bestimmter Codeblöcke, indem der Compiler angewiesen wird, andere Blöcke zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="7c10d-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="7c10d-126">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="7c10d-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="7c10d-127">Zeigt, wie lange Anweisungen in mehrere Zeilen aufgeteilt und kurze Anweisungen zu einer Zeile zusammengefasst werden können.</span><span class="sxs-lookup"><span data-stu-id="7c10d-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="7c10d-128">Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten</span><span class="sxs-lookup"><span data-stu-id="7c10d-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="7c10d-129">Erläutert das Reduzieren und Ausblenden von Codeabschnitten im Code-Editor von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c10d-129">Shows how to collapse and hide sections of code in the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code editor.</span></span>  
  
 [<span data-ttu-id="7c10d-130">Gewusst wie: Bezeichnen von Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7c10d-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="7c10d-131">Veranschaulicht, wie Codezeilen für die Verwendung mit Anweisungen, z. B. `On Error Goto`, gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="7c10d-132">Sonderzeichen in Code</span><span class="sxs-lookup"><span data-stu-id="7c10d-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="7c10d-133">Zeigt, wie und an welcher Stelle nicht numerische und nicht alphabetische Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="7c10d-134">Kommentare in Code</span><span class="sxs-lookup"><span data-stu-id="7c10d-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="7c10d-135">Beschreibt, wie dem Code beschreibende Kommentare hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="7c10d-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="7c10d-136">Schlüsselwörter als Elementnamen in Code</span><span class="sxs-lookup"><span data-stu-id="7c10d-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="7c10d-137">Beschreibt, wie Variablennamen, die gleichzeitig `[]`-Schlüsselwörter sind, mithilfe von eckigen Klammern ([!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]) begrenzt werden.</span><span class="sxs-lookup"><span data-stu-id="7c10d-137">Describes how to use brackets (`[]`) to delimit variable names that are also [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keywords.</span></span>  
  
 [<span data-ttu-id="7c10d-138">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="7c10d-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="7c10d-139">Beschreibt verschiedene Möglichkeiten, auf Elemente eines [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Programms zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="7c10d-139">Describes various ways to refer to elements of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="7c10d-140">Beschränkungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7c10d-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="7c10d-141">Erläutert die Entfernung bekannter Codierungsbeschränkungen in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c10d-141">Discusses the removal of known coding limits within [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7c10d-142">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7c10d-142">Related Sections</span></span>  
 [<span data-ttu-id="7c10d-143">Typografische und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="7c10d-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="7c10d-144">Enthält Standardcodierungskonventionen für [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c10d-144">Provides standard coding conventions for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [<span data-ttu-id="7c10d-145">Schreiben von Code</span><span class="sxs-lookup"><span data-stu-id="7c10d-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="7c10d-146">Beschreibt Funktionen, die Ihnen das Schreiben und Verwalten von Code erleichtern.</span><span class="sxs-lookup"><span data-stu-id="7c10d-146">Describes features that make it easier for you to write and manage your code.</span></span>
