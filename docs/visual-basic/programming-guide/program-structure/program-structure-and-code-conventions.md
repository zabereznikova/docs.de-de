---
title: Programmstruktur und Codekonventionen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9980a815d83b21214f1be441d641c3da38c1b541
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="9454e-102">Programmstruktur und Codekonventionen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9454e-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="9454e-103">In diesem Abschnitt führt die typische Visual Basic-Programmstruktur, bietet ein einfaches Visual Basic-Programm "Hello, World" und Visual Basic-Code-Konventionen erläutert.</span><span class="sxs-lookup"><span data-stu-id="9454e-103">This section introduces the typical Visual Basic program structure, provides a simple Visual Basic program, "Hello, World", and discusses Visual Basic code conventions.</span></span> <span data-ttu-id="9454e-104">Codekonventionen sind Vorschläge, die sich nicht auf die Logik eines Programms, sondern auf seine physische Struktur und sein Erscheinungsbild konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="9454e-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="9454e-105">Wenn Sie diese Konventionen einhalten, ist Programmcode besser lesbar, leichter verständlich und einfacher zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9454e-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="9454e-106">Codekonventionen umfassen u. a.:</span><span class="sxs-lookup"><span data-stu-id="9454e-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="9454e-107">Standardisierte Formate für Bezeichnungen und Kommentare im Code.</span><span class="sxs-lookup"><span data-stu-id="9454e-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="9454e-108">Richtlinien für die Verwendung von Leerzeichen, Formatierungen und Einzügen beim Code.</span><span class="sxs-lookup"><span data-stu-id="9454e-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="9454e-109">Benennungskonventionen für Objekte, Variablen und Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="9454e-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="9454e-110">Die folgenden Themen enthalten eine Reihe von Programmierungsrichtlinien für Visual Basic-Programme, zusammen mit Beispielen, die richtige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="9454e-110">The following topics present a set of programming guidelines for Visual Basic programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9454e-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9454e-111">In This Section</span></span>  
 [<span data-ttu-id="9454e-112">Struktur eines Visual Basic-Programms</span><span class="sxs-lookup"><span data-stu-id="9454e-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="9454e-113">Bietet eine Übersicht über die Elemente, aus denen ein Visual Basic-Programm besteht.</span><span class="sxs-lookup"><span data-stu-id="9454e-113">Provides an overview of the elements that make up a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="9454e-114">Main-Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9454e-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="9454e-115">Erörtert die Prozedur, die als Ausgangspunkt und Gesamtsteuerung für die Anwendung fungiert.</span><span class="sxs-lookup"><span data-stu-id="9454e-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="9454e-116">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9454e-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="9454e-117">Erläutert, wie auf Objekte in anderen Assemblys verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9454e-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="9454e-118">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9454e-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="9454e-119">Beschreibt, wie Namespaces Objekte innerhalb von Assemblys organisieren.</span><span class="sxs-lookup"><span data-stu-id="9454e-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="9454e-120">Visual Basic-Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="9454e-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="9454e-121">Umfasst allgemeine Richtlinien für die Benennung von Prozeduren, Konstanten, Variablen, Argumenten und Objekten.</span><span class="sxs-lookup"><span data-stu-id="9454e-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="9454e-122">Visual Basic-Codierungskonventionen</span><span class="sxs-lookup"><span data-stu-id="9454e-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="9454e-123">Erläutert die Richtlinien, die beim Entwickeln der Beispiele in dieser Dokumentation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9454e-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="9454e-124">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="9454e-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="9454e-125">Beschreibt die selektive Kompilierung bestimmter Codeblöcke, indem der Compiler angewiesen wird, andere Blöcke zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="9454e-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="9454e-126">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code</span><span class="sxs-lookup"><span data-stu-id="9454e-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="9454e-127">Zeigt, wie lange Anweisungen in mehrere Zeilen aufgeteilt und kurze Anweisungen zu einer Zeile zusammengefasst werden können.</span><span class="sxs-lookup"><span data-stu-id="9454e-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="9454e-128">Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten</span><span class="sxs-lookup"><span data-stu-id="9454e-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="9454e-129">Zeigt, wie reduzieren und blenden Sie Codeabschnitte im Visual Basic Codeeditor.</span><span class="sxs-lookup"><span data-stu-id="9454e-129">Shows how to collapse and hide sections of code in the Visual Basic code editor.</span></span>  
  
 [<span data-ttu-id="9454e-130">Gewusst wie: Bezeichnen von Anweisungen</span><span class="sxs-lookup"><span data-stu-id="9454e-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="9454e-131">Veranschaulicht, wie Codezeilen für die Verwendung mit Anweisungen, z. B. `On Error Goto`, gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="9454e-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="9454e-132">Sonderzeichen in Code</span><span class="sxs-lookup"><span data-stu-id="9454e-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="9454e-133">Zeigt, wie und an welcher Stelle nicht numerische und nicht alphabetische Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9454e-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="9454e-134">Kommentare in Code</span><span class="sxs-lookup"><span data-stu-id="9454e-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="9454e-135">Beschreibt, wie dem Code beschreibende Kommentare hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="9454e-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="9454e-136">Schlüsselwörter als Elementnamen in Code</span><span class="sxs-lookup"><span data-stu-id="9454e-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="9454e-137">Beschreibt, wie mithilfe von eckigen Klammern (`[]`) zur Begrenzung von Variablennamen, die auch Visual Basic-Schlüsselwörter sind.</span><span class="sxs-lookup"><span data-stu-id="9454e-137">Describes how to use brackets (`[]`) to delimit variable names that are also Visual Basic keywords.</span></span>  
  
 [<span data-ttu-id="9454e-138">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="9454e-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="9454e-139">Beschreibt verschiedene Verfahren zum Verweisen auf Elemente eines Visual Basic-Programms.</span><span class="sxs-lookup"><span data-stu-id="9454e-139">Describes various ways to refer to elements of a Visual Basic program.</span></span>  
  
 [<span data-ttu-id="9454e-140">Beschränkungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9454e-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="9454e-141">Erläutert die Entfernung bekannter codierungsbeschränkungen in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9454e-141">Discusses the removal of known coding limits within Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9454e-142">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="9454e-142">Related Sections</span></span>  
 [<span data-ttu-id="9454e-143">Typografische und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="9454e-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="9454e-144">Enthält Standardcodierungskonventionen für Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9454e-144">Provides standard coding conventions for Visual Basic.</span></span>  
  
 [<span data-ttu-id="9454e-145">Schreiben von Code</span><span class="sxs-lookup"><span data-stu-id="9454e-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="9454e-146">Beschreibt Funktionen, die Ihnen das Schreiben und Verwalten von Code erleichtern.</span><span class="sxs-lookup"><span data-stu-id="9454e-146">Describes features that make it easier for you to write and manage your code.</span></span>
