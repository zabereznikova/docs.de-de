---
title: Visual Basic-Codierungskonventionen | Microsoft-Dokumentation
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
- coding conventions, Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
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
ms.openlocfilehash: 16d4ddccd3a16c48e58f297faf8909148899013f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="94854-102">Codierungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94854-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="94854-103">Microsoft entwickelt Beispiele und Dokumentation, die den Richtlinien in diesem Thema folgen.</span><span class="sxs-lookup"><span data-stu-id="94854-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="94854-104">Wenn Sie dieselben Codierungskonventionen beachten, erhalten Sie möglicherweise folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="94854-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="94854-105">Der Code erhält eine konsistente Gestaltung, damit sich die Leser mehr auf den Inhalt und nicht auf das Layout konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="94854-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="94854-106">Leser verstehen den Code schneller, da sie Rückschlüsse aus früheren Erfahrungen ziehen können.</span><span class="sxs-lookup"><span data-stu-id="94854-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="94854-107">Sie können den Code kopieren, ändern und leichter pflegen.</span><span class="sxs-lookup"><span data-stu-id="94854-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="94854-108">Sie können sicherstellen, dass der Code die "empfohlenen Vorgehensweisen" für Visual Basic berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="94854-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="94854-109">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="94854-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="94854-110">Informationen zu Benennungsrichtlinien finden Sie unter [Benennungsrichtlinien](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) Thema.</span><span class="sxs-lookup"><span data-stu-id="94854-110">For information about naming guidelines, see [Naming Guidelines](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) topic.</span></span>  
  
-   <span data-ttu-id="94854-111">Verwenden Sie nicht "My" oder "my" als Teil eines Variablennamens.</span><span class="sxs-lookup"><span data-stu-id="94854-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="94854-112">Diese Vorgehensweise führt zu Verwechslungen mit den `My`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="94854-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="94854-113">Sie müssen die Namen von Objekten in automatisch generiertem Code nicht ändern, um sie an die Richtlinien anzupassen.</span><span class="sxs-lookup"><span data-stu-id="94854-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="94854-114">Layoutkonventionen</span><span class="sxs-lookup"><span data-stu-id="94854-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="94854-115">Fügen Sie Registerkarten als Leerzeichen ein, und verwenden Sie intelligenten Einzug mit vier Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="94854-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="94854-116">Verwendung **ziemlich auflisten (nachträgliche) Code** , Code im Code-Editor neu zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="94854-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="94854-117">Weitere Informationen finden Sie unter [Optionen, Text-Editor, Standard (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="94854-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="94854-118">Verwenden Sie pro Zeile nur eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="94854-118">Use only one statement per line.</span></span> <span data-ttu-id="94854-119">Verwenden Sie nicht das Visual Basic-Zeilentrennzeichen (:).</span><span class="sxs-lookup"><span data-stu-id="94854-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="94854-120">Vermeiden Sie, das explizite Zeilenfortsetzungszeichen "_" zugunsten der impliziten Zeilenfortsetzung, wenn die Sprache dies ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="94854-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="94854-121">Verwenden Sie pro Zeile nur eine Deklaration.</span><span class="sxs-lookup"><span data-stu-id="94854-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="94854-122">Wenn **ziemlich auflisten (nachträgliche) Code** nicht Fortsetzungszeilen automatisch zum einrücken manuell Fortsetzung einen Tabstopp.</span><span class="sxs-lookup"><span data-stu-id="94854-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="94854-123">In einer Liste werden jedoch die Elemente immer links ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="94854-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="94854-124">Fügen Sie zwischen Methoden- und Eigenschaftendefinitionen mindestens eine Leerzeile ein.</span><span class="sxs-lookup"><span data-stu-id="94854-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="94854-125">Konventionen für Kommentare</span><span class="sxs-lookup"><span data-stu-id="94854-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="94854-126">Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="94854-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="94854-127">Beginnen Sie den Kommentartext mit einem Großbuchstaben, und beenden Sie ihn mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="94854-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="94854-128">Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (') und dem Kommentartext ein.</span><span class="sxs-lookup"><span data-stu-id="94854-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     <span data-ttu-id="94854-129">[!code-vb[VbVbalrGuidelines&#2;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-129">[!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span></span>  
  
-   <span data-ttu-id="94854-130">Erstellen Sie keine formatierten Blöcke von Sternchen, die die Kommentare umgeben.</span><span class="sxs-lookup"><span data-stu-id="94854-130">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="94854-131">Programmstruktur</span><span class="sxs-lookup"><span data-stu-id="94854-131">Program Structure</span></span>  
  
-   <span data-ttu-id="94854-132">Wenn Sie die `Main`-Methode verwenden, verwenden Sie das Standardkonstrukt für neue Konsolenanwendungen, und verwenden Sie `My` für Befehlszeilenargumente.</span><span class="sxs-lookup"><span data-stu-id="94854-132">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     <span data-ttu-id="94854-133">[!code-vb[VbVbalrGuidelines&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-133">[!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="94854-134">Sprachrichtlinien</span><span class="sxs-lookup"><span data-stu-id="94854-134">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="94854-135">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="94854-135">String Data Type</span></span>  
  
-   <span data-ttu-id="94854-136">Um Zeichenfolgen verketten, verwenden Sie ein kaufmännisches Und-Zeichen (&).</span><span class="sxs-lookup"><span data-stu-id="94854-136">To concatenate strings, use an ampersand (&).</span></span>  
  
     <span data-ttu-id="94854-137">[!code-vb[VbVbalrGuidelines&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-137">[!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span></span>  
  
-   <span data-ttu-id="94854-138">Um Zeichenfolgen in Schleifen anzufügen, verwenden Sie die <xref:System.Text.StringBuilder>Objekt.</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="94854-138">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="94854-139">[!code-vb[VbVbalrGuidelines&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-139">[!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span></span>  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="94854-140">Weniger strenge Delegaten in Ereignishandlern</span><span class="sxs-lookup"><span data-stu-id="94854-140">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="94854-141">Um Ereignishandler zu vermeiden, qualifizieren Sie die Argumente (Object und EventArgs) nicht explizit.</span><span class="sxs-lookup"><span data-stu-id="94854-141">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="94854-142">Wenn Sie nicht die Ereignisargumente verwenden, die an ein Ereignis übergeben werden (z. B. Sender als Objekt, „e“ als EventArgs), verwenden Sie weniger strenge Delegaten, und lassen Sie die Ereignisargumente im Code aus:</span><span class="sxs-lookup"><span data-stu-id="94854-142">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 <span data-ttu-id="94854-143">[!code-vb[VbVbalrGuidelines&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-143">[!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="94854-144">Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="94854-144">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="94854-145">Verwenden Sie `Integer` anstelle von Typen ohne Vorzeichen, wenn sie nicht notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="94854-145">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="94854-146">Arrays</span><span class="sxs-lookup"><span data-stu-id="94854-146">Arrays</span></span>  
  
-   <span data-ttu-id="94854-147">Verwenden Sie die kurze Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren.</span><span class="sxs-lookup"><span data-stu-id="94854-147">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="94854-148">Sie können z. B. folgende Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="94854-148">For example, use the following syntax.</span></span>  
  
     <span data-ttu-id="94854-149">[!code-vb[VbVbalrGuidelines&#8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-149">[!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span></span>  
  
     <span data-ttu-id="94854-150">Verwenden Sie nicht die folgende Syntax.</span><span class="sxs-lookup"><span data-stu-id="94854-150">Do not use the following syntax.</span></span>  
  
     <span data-ttu-id="94854-151">[!code-vb[VbVbalrGuidelines&#9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-151">[!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span></span>  
  
-   <span data-ttu-id="94854-152">Legen Sie den Arraybezeichner im Typ und nicht in der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="94854-152">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="94854-153">Sie können z. B. folgende Syntax verwenden:</span><span class="sxs-lookup"><span data-stu-id="94854-153">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="94854-154">[!code-vb[VbVbalrGuidelines&#11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-154">[!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span></span>  
  
     <span data-ttu-id="94854-155">Verwenden Sie nicht die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="94854-155">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="94854-156">[!code-vb[VbVbalrGuidelines&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-156">[!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span></span>  
  
-   <span data-ttu-id="94854-157">Verwenden Sie die { }-Syntax, wenn Sie Arrays aus grundlegenden Datentypen deklarieren und initialisieren.</span><span class="sxs-lookup"><span data-stu-id="94854-157">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="94854-158">Sie können z. B. folgende Syntax verwenden:</span><span class="sxs-lookup"><span data-stu-id="94854-158">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="94854-159">[!code-vb[VbVbalrGuidelines&#12;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-159">[!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span></span>  
  
     <span data-ttu-id="94854-160">Verwenden Sie nicht die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="94854-160">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="94854-161">[!code-vb[VbVbalrGuidelines&#13;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-161">[!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span></span>  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="94854-162">Verwenden des with-Schlüsselworts</span><span class="sxs-lookup"><span data-stu-id="94854-162">Use the With Keyword</span></span>  
 <span data-ttu-id="94854-163">Wenn Sie eine Reihe von Aufrufen eines Objekts ausführen, sollten Sie erwägen, das `With`-Schlüsselwort zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="94854-163">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 <span data-ttu-id="94854-164">[!code-vb[VbVbalrGuidelines&#15;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-164">[!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span></span>  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="94854-165">Verwenden Sie try-catch-Anweisungen zur Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="94854-165">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="94854-166">Verwenden Sie nicht `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="94854-166">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="94854-167">Verwenden des IsNot-Schlüsselworts</span><span class="sxs-lookup"><span data-stu-id="94854-167">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="94854-168">Verwenden Sie das Schlüsselwort `IsNot` statt `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="94854-168">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="94854-169">New-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="94854-169">New Keyword</span></span>  
  
-   <span data-ttu-id="94854-170">Verwenden Sie die kurze Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="94854-170">Use short instantiation.</span></span> <span data-ttu-id="94854-171">Sie können z. B. folgende Syntax verwenden:</span><span class="sxs-lookup"><span data-stu-id="94854-171">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="94854-172">[!code-vb[VbVbalrGuidelines&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-172">[!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span></span>  
  
     <span data-ttu-id="94854-173">Die vorangehende Zeile entspricht der Folgenden:</span><span class="sxs-lookup"><span data-stu-id="94854-173">The preceding line is equivalent to this:</span></span>  
  
     <span data-ttu-id="94854-174">[!code-vb[VbVbalrGuidelines&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-174">[!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span></span>  
  
-   <span data-ttu-id="94854-175">Verwenden Sie für neue Objekte Objektinitialisierer anstelle des parameterlosen Konstruktors:</span><span class="sxs-lookup"><span data-stu-id="94854-175">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     <span data-ttu-id="94854-176">[!code-vb[VbVbalrGuidelines&23;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-176">[!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="94854-177">Ereignisbehandlung</span><span class="sxs-lookup"><span data-stu-id="94854-177">Event Handling</span></span>  
  
-   <span data-ttu-id="94854-178">Verwenden Sie eher `Handles` als `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="94854-178">Use `Handles` rather than `AddHandler`:</span></span>  
  
     <span data-ttu-id="94854-179">[!code-vb[VbVbalrGuidelines&#24;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-179">[!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span></span>  
  
-   <span data-ttu-id="94854-180">Verwenden Sie `AddressOf`, und instanziieren Sie den Delegaten nicht explizit:</span><span class="sxs-lookup"><span data-stu-id="94854-180">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     <span data-ttu-id="94854-181">[!code-vb[VbVbalrGuidelines&#25;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-181">[!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span></span>  
  
-   <span data-ttu-id="94854-182">Wenn Sie ein Ereignis definieren, verwenden Sie die kurze Syntax, und lassen Sie den Delegaten vom Compiler definieren:</span><span class="sxs-lookup"><span data-stu-id="94854-182">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     <span data-ttu-id="94854-183">[!code-vb[VbVbalrGuidelines&#26;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-183">[!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span></span>  
  
-   <span data-ttu-id="94854-184">Überprüfen Sie nicht, ob ein Ereignis `Nothing` (NULL) ist, bevor Sie die `RaiseEvent`-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="94854-184">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="94854-185">Die `RaiseEvent`-Methode führt vor dem Auslösen des Ereignisses eine Überprüfung auf den Wert `Nothing` durch.</span><span class="sxs-lookup"><span data-stu-id="94854-185">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="94854-186">Verwenden von Shared-Membern</span><span class="sxs-lookup"><span data-stu-id="94854-186">Using Shared Members</span></span>  
 <span data-ttu-id="94854-187">Rufen Sie `Shared`-Member über den Klassennamen auf, nicht von einer Instanzvariablen aus.</span><span class="sxs-lookup"><span data-stu-id="94854-187">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="94854-188">Verwenden von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="94854-188">Use XML Literals</span></span>  
 <span data-ttu-id="94854-189">XML-Literale vereinfachen allgemeine Aufgaben bei der Arbeit mit XML (z. B. Laden, Abfragen und Umwandeln).</span><span class="sxs-lookup"><span data-stu-id="94854-189">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="94854-190">Beachten Sie bei der Entwicklung mit XML die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="94854-190">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="94854-191">Verwenden Sie zum Erstellen von XML-Dokumenten und –Fragmenten XML-Literale, anstatt die XML-APIs direkt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="94854-191">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="94854-192">Importieren Sie XML-Namespaces auf Datei- oder Projektebene, um die Leistungsoptimierung für XML-Literale zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="94854-192">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="94854-193">Verwenden Sie die XML-Achseneigenschaften, um auf Elemente und Attribute in einem XML-Dokument zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="94854-193">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="94854-194">Verwenden Sie eingebettete Ausdrücke, um Werte einzuschließen und XML aus vorhandenen Werten zu erstellen, anstatt API-Aufrufe wie die `Add`-Methode zu nutzen:</span><span class="sxs-lookup"><span data-stu-id="94854-194">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     <span data-ttu-id="94854-195">[!code-vb[VbVbalrGuidelines&#27;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-195">[!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="94854-196">LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="94854-196">LINQ Queries</span></span>  
  
-   <span data-ttu-id="94854-197">Verwenden Sie aussagekräftige Namen für Abfragevariablen:</span><span class="sxs-lookup"><span data-stu-id="94854-197">Use meaningful names for query variables:</span></span>  
  
     <span data-ttu-id="94854-198">[!code-vb[VbVbalrGuidelines&#28;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-198">[!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span></span>  
  
-   <span data-ttu-id="94854-199">Geben Sie Aliasnamen für Elemente in einer Abfrage an, um eine korrekte Großschreibung von Eigenschaftennamen anonymer Typen in Pascal-Schreibweise sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="94854-199">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     <span data-ttu-id="94854-200">[!code-vb[VbVbalrGuidelines&#29;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-200">[!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span></span>  
  
-   <span data-ttu-id="94854-201">Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="94854-201">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="94854-202">Wenn die Abfrage beispielsweise einen Kundennamen und eine Auftrags-ID zurückgibt, sollten Sie diese im Ergebnis umbenennen, anstatt `Name` und `ID` zu übernehmen:</span><span class="sxs-lookup"><span data-stu-id="94854-202">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     <span data-ttu-id="94854-203">[!code-vb[VbVbalrGuidelines&#30;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-203">[!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span></span>  
  
-   <span data-ttu-id="94854-204">Verwenden Sie den Typrückschluss in der Deklaration von Abfragevariablen und Bereichsvariablen:</span><span class="sxs-lookup"><span data-stu-id="94854-204">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     <span data-ttu-id="94854-205">[!code-vb[VbVbalrGuidelines&#31;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-205">[!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span></span>  
  
-   <span data-ttu-id="94854-206">Richten Sie Abfrageklauseln unter der `From`-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="94854-206">Align query clauses under the `From` statement:</span></span>  
  
     <span data-ttu-id="94854-207">[!code-vb[VbVbalrGuidelines&#32;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-207">[!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span></span>  
  
-   <span data-ttu-id="94854-208">Verwenden Sie vor anderen Abfrageklauseln `Where`-Klauseln, sodass die nachfolgenden Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="94854-208">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     <span data-ttu-id="94854-209">[!code-vb[VbVbalrGuidelines&33;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-209">[!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span></span>  
  
-   <span data-ttu-id="94854-210">Verwenden Sie zum expliziten Definieren eines Verbindungsvorgangs die `Join`-Klausel anstelle der `Where`-Klausel, bei der ein Verbindungsvorgang implizit definiert wird:</span><span class="sxs-lookup"><span data-stu-id="94854-210">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     <span data-ttu-id="94854-211">[!code-vb[VbVbalrGuidelines&#34;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span><span class="sxs-lookup"><span data-stu-id="94854-211">[!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94854-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94854-212">See Also</span></span>  
 [<span data-ttu-id="94854-213">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="94854-213">Secure Coding Guidelines</span></span>](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
