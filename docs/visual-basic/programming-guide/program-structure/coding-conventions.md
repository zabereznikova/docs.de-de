---
title: Codierungskonventionen
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: 36cd3a927d2fdf197e6b496d9308fc43a555d59b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346158"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="36c0e-102">Codierungskonventionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="36c0e-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="36c0e-103">Microsoft entwickelt Beispiele und Dokumentation, die den Richtlinien in diesem Thema folgen.</span><span class="sxs-lookup"><span data-stu-id="36c0e-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="36c0e-104">Wenn Sie dieselben Codierungskonventionen beachten, erhalten Sie möglicherweise folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="36c0e-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
- <span data-ttu-id="36c0e-105">Der Code erhält eine konsistente Gestaltung, damit sich die Leser mehr auf den Inhalt und nicht auf das Layout konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="36c0e-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
- <span data-ttu-id="36c0e-106">Leser verstehen den Code schneller, da sie Rückschlüsse aus früheren Erfahrungen ziehen können.</span><span class="sxs-lookup"><span data-stu-id="36c0e-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="36c0e-107">Sie können den Code kopieren, ändern und leichter pflegen.</span><span class="sxs-lookup"><span data-stu-id="36c0e-107">You can copy, change, and maintain the code more easily.</span></span>  
  
- <span data-ttu-id="36c0e-108">Sie können sicherstellen, dass der Code die "empfohlenen Vorgehensweisen" für Visual Basic berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="36c0e-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="36c0e-109">Namenskonventionen</span><span class="sxs-lookup"><span data-stu-id="36c0e-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="36c0e-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span><span class="sxs-lookup"><span data-stu-id="36c0e-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
- <span data-ttu-id="36c0e-111">Verwenden Sie nicht "My" oder "my" als Teil eines Variablennamens.</span><span class="sxs-lookup"><span data-stu-id="36c0e-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="36c0e-112">Diese Vorgehensweise führt zu Verwechslungen mit den `My`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="36c0e-112">This practice creates confusion with the `My` objects.</span></span>  
  
- <span data-ttu-id="36c0e-113">Sie müssen die Namen von Objekten in automatisch generiertem Code nicht ändern, um sie an die Richtlinien anzupassen.</span><span class="sxs-lookup"><span data-stu-id="36c0e-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="36c0e-114">Layoutkonventionen</span><span class="sxs-lookup"><span data-stu-id="36c0e-114">Layout Conventions</span></span>  
  
- <span data-ttu-id="36c0e-115">Fügen Sie Registerkarten als Leerzeichen ein, und verwenden Sie intelligenten Einzug mit vier Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="36c0e-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
- <span data-ttu-id="36c0e-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span><span class="sxs-lookup"><span data-stu-id="36c0e-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="36c0e-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="36c0e-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
- <span data-ttu-id="36c0e-118">Verwenden Sie pro Zeile nur eine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="36c0e-118">Use only one statement per line.</span></span> <span data-ttu-id="36c0e-119">Verwenden Sie nicht das Visual Basic-Zeilentrennzeichen (:).</span><span class="sxs-lookup"><span data-stu-id="36c0e-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
- <span data-ttu-id="36c0e-120">Vermeiden Sie, das explizite Zeilenfortsetzungszeichen "_" zugunsten der impliziten Zeilenfortsetzung, wenn die Sprache dies ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="36c0e-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
- <span data-ttu-id="36c0e-121">Verwenden Sie pro Zeile nur eine Deklaration.</span><span class="sxs-lookup"><span data-stu-id="36c0e-121">Use only one declaration per line.</span></span>  
  
- <span data-ttu-id="36c0e-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span><span class="sxs-lookup"><span data-stu-id="36c0e-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="36c0e-123">In einer Liste werden jedoch die Elemente immer links ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="36c0e-123">However, always left-align items in a list.</span></span>  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- <span data-ttu-id="36c0e-124">Fügen Sie zwischen Methoden- und Eigenschaftendefinitionen mindestens eine Leerzeile ein.</span><span class="sxs-lookup"><span data-stu-id="36c0e-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="36c0e-125">Konventionen für Kommentare</span><span class="sxs-lookup"><span data-stu-id="36c0e-125">Commenting Conventions</span></span>  
  
- <span data-ttu-id="36c0e-126">Fügen Sie den Kommentar in einer eigenen Zeile und nicht am Ende einer Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="36c0e-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
- <span data-ttu-id="36c0e-127">Beginnen Sie den Kommentartext mit einem Großbuchstaben, und beenden Sie ihn mit einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="36c0e-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
- <span data-ttu-id="36c0e-128">Fügen Sie ein Leerzeichen zwischen dem Kommentartrennzeichen (') und dem Kommentartext ein.</span><span class="sxs-lookup"><span data-stu-id="36c0e-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- <span data-ttu-id="36c0e-129">Erstellen Sie keine formatierten Blöcke von Sternchen, die die Kommentare umgeben.</span><span class="sxs-lookup"><span data-stu-id="36c0e-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="36c0e-130">Programmstruktur</span><span class="sxs-lookup"><span data-stu-id="36c0e-130">Program Structure</span></span>  
  
- <span data-ttu-id="36c0e-131">Wenn Sie die `Main`-Methode verwenden, verwenden Sie das Standardkonstrukt für neue Konsolenanwendungen, und verwenden Sie `My` für Befehlszeilenargumente.</span><span class="sxs-lookup"><span data-stu-id="36c0e-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="36c0e-132">Sprachrichtlinien</span><span class="sxs-lookup"><span data-stu-id="36c0e-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="36c0e-133">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="36c0e-133">String Data Type</span></span>  
  
- <span data-ttu-id="36c0e-134">Verwenden Sie die [Zeichenfolgeninterpolation](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings), um wie im folgenden Code gezeigt kurze Zeichenfolgen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="36c0e-134">Use [string interpolation](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings) to concatenate short strings, as shown in the following code.</span></span>
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- <span data-ttu-id="36c0e-135">Verwenden Sie das <xref:System.Text.StringBuilder>-Objekt, um Zeichenfolgen in Schleifen anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="36c0e-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="36c0e-136">Weniger strenge Delegaten in Ereignishandlern</span><span class="sxs-lookup"><span data-stu-id="36c0e-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="36c0e-137">Um Ereignishandler zu vermeiden, qualifizieren Sie die Argumente (Object und EventArgs) nicht explizit.</span><span class="sxs-lookup"><span data-stu-id="36c0e-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="36c0e-138">Wenn Sie nicht die Ereignisargumente verwenden, die an ein Ereignis übergeben werden (z. B. Sender als Objekt, "e" als EventArgs), verwenden Sie weniger strenge Delegaten, und lassen Sie die Ereignisargumente im Code aus:</span><span class="sxs-lookup"><span data-stu-id="36c0e-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="36c0e-139">Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="36c0e-139">Unsigned Data Type</span></span>  
  
- <span data-ttu-id="36c0e-140">Verwenden Sie `Integer` anstelle von Typen ohne Vorzeichen, wenn sie nicht notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="36c0e-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="36c0e-141">Arrays</span><span class="sxs-lookup"><span data-stu-id="36c0e-141">Arrays</span></span>  
  
- <span data-ttu-id="36c0e-142">Verwenden Sie die kurze Syntax, wenn Sie Arrays in der Deklarationszeile initialisieren.</span><span class="sxs-lookup"><span data-stu-id="36c0e-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="36c0e-143">Sie können z. B. folgende Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="36c0e-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="36c0e-144">Verwenden Sie nicht die folgende Syntax.</span><span class="sxs-lookup"><span data-stu-id="36c0e-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- <span data-ttu-id="36c0e-145">Legen Sie den Arraybezeichner im Typ und nicht in der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="36c0e-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="36c0e-146">Sie können z. B. folgende Syntax verwenden:</span><span class="sxs-lookup"><span data-stu-id="36c0e-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="36c0e-147">Verwenden Sie nicht die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="36c0e-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- <span data-ttu-id="36c0e-148">Verwenden Sie die { }-Syntax, wenn Sie Arrays aus grundlegenden Datentypen deklarieren und initialisieren.</span><span class="sxs-lookup"><span data-stu-id="36c0e-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="36c0e-149">Sie können z. B. folgende Syntax verwenden:</span><span class="sxs-lookup"><span data-stu-id="36c0e-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     <span data-ttu-id="36c0e-150">Verwenden Sie nicht die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="36c0e-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="36c0e-151">Verwenden des with-Schlüsselworts</span><span class="sxs-lookup"><span data-stu-id="36c0e-151">Use the With Keyword</span></span>  
 <span data-ttu-id="36c0e-152">Wenn Sie eine Reihe von Aufrufen eines Objekts ausführen, sollten Sie erwägen, das `With`-Schlüsselwort zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="36c0e-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="36c0e-153">Verwenden Sie try-catch-Anweisungen zur Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="36c0e-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="36c0e-154">Verwenden Sie nicht `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="36c0e-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="36c0e-155">Verwenden des IsNot-Schlüsselworts</span><span class="sxs-lookup"><span data-stu-id="36c0e-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="36c0e-156">Verwenden Sie das Schlüsselwort `IsNot` statt `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="36c0e-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="36c0e-157">New-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="36c0e-157">New Keyword</span></span>  
  
- <span data-ttu-id="36c0e-158">Verwenden Sie die kurze Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="36c0e-158">Use short instantiation.</span></span> <span data-ttu-id="36c0e-159">Sie können z. B. folgende Syntax verwenden:</span><span class="sxs-lookup"><span data-stu-id="36c0e-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="36c0e-160">Die vorangehende Zeile entspricht der Folgenden:</span><span class="sxs-lookup"><span data-stu-id="36c0e-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- <span data-ttu-id="36c0e-161">Verwenden Sie für neue Objekte Objektinitialisierer anstelle des parameterlosen Konstruktors:</span><span class="sxs-lookup"><span data-stu-id="36c0e-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="36c0e-162">Ereignisbehandlung</span><span class="sxs-lookup"><span data-stu-id="36c0e-162">Event Handling</span></span>  
  
- <span data-ttu-id="36c0e-163">Verwenden Sie eher `Handles` als `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="36c0e-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- <span data-ttu-id="36c0e-164">Verwenden Sie `AddressOf`, und instanziieren Sie den Delegaten nicht explizit:</span><span class="sxs-lookup"><span data-stu-id="36c0e-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- <span data-ttu-id="36c0e-165">Wenn Sie ein Ereignis definieren, verwenden Sie die kurze Syntax, und lassen Sie den Delegaten vom Compiler definieren:</span><span class="sxs-lookup"><span data-stu-id="36c0e-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- <span data-ttu-id="36c0e-166">Überprüfen Sie nicht, ob ein Ereignis `Nothing` (NULL) ist, bevor Sie die `RaiseEvent`-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="36c0e-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="36c0e-167">Die `RaiseEvent`-Methode führt vor dem Auslösen des Ereignisses eine Überprüfung auf den Wert `Nothing` durch.</span><span class="sxs-lookup"><span data-stu-id="36c0e-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="36c0e-168">Verwenden von Shared-Membern</span><span class="sxs-lookup"><span data-stu-id="36c0e-168">Using Shared Members</span></span>  
 <span data-ttu-id="36c0e-169">Rufen Sie `Shared`-Member über den Klassennamen auf, nicht von einer Instanzvariablen aus.</span><span class="sxs-lookup"><span data-stu-id="36c0e-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="36c0e-170">Verwenden von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="36c0e-170">Use XML Literals</span></span>  
 <span data-ttu-id="36c0e-171">XML-Literale vereinfachen allgemeine Aufgaben bei der Arbeit mit XML (z. B. Laden, Abfragen und Transformieren).</span><span class="sxs-lookup"><span data-stu-id="36c0e-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="36c0e-172">Beachten Sie bei der Entwicklung mit XML die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="36c0e-172">When you develop with XML, follow these guidelines:</span></span>  
  
- <span data-ttu-id="36c0e-173">Verwenden Sie zum Erstellen von XML-Dokumenten und –Fragmenten XML-Literale, anstatt die XML-APIs direkt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="36c0e-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
- <span data-ttu-id="36c0e-174">Importieren Sie XML-Namespaces auf Datei- oder Projektebene, um die Leistungsoptimierung für XML-Literale zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="36c0e-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
- <span data-ttu-id="36c0e-175">Verwenden Sie die XML-Achseneigenschaften, um auf Elemente und Attribute in einem XML-Dokument zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="36c0e-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
- <span data-ttu-id="36c0e-176">Verwenden Sie eingebettete Ausdrücke, um Werte einzuschließen und XML aus vorhandenen Werten zu erstellen, anstatt API-Aufrufe wie die `Add`-Methode zu nutzen:</span><span class="sxs-lookup"><span data-stu-id="36c0e-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="36c0e-177">LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="36c0e-177">LINQ Queries</span></span>  
  
- <span data-ttu-id="36c0e-178">Verwenden Sie aussagekräftige Namen für Abfragevariablen:</span><span class="sxs-lookup"><span data-stu-id="36c0e-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- <span data-ttu-id="36c0e-179">Geben Sie Aliasnamen für Elemente in einer Abfrage an, um eine korrekte Großschreibung von Eigenschaftennamen anonymer Typen in Pascal-Schreibweise sicherzustellen:</span><span class="sxs-lookup"><span data-stu-id="36c0e-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- <span data-ttu-id="36c0e-180">Benennen Sie Eigenschaften um, wenn die Eigenschaftennamen im Ergebnis nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="36c0e-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="36c0e-181">Wenn die Abfrage beispielsweise einen Kundennamen und eine Auftrags-ID zurückgibt, sollten Sie diese im Ergebnis umbenennen, anstatt `Name` und `ID` zu übernehmen:</span><span class="sxs-lookup"><span data-stu-id="36c0e-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- <span data-ttu-id="36c0e-182">Verwenden Sie den Typrückschluss in der Deklaration von Abfragevariablen und Bereichsvariablen:</span><span class="sxs-lookup"><span data-stu-id="36c0e-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- <span data-ttu-id="36c0e-183">Richten Sie Abfrageklauseln unter der `From`-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="36c0e-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- <span data-ttu-id="36c0e-184">Verwenden Sie vor anderen Abfrageklauseln `Where`-Klauseln, sodass die nachfolgenden Abfrageklauseln für den reduzierten, gefilterten Datensatz ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="36c0e-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- <span data-ttu-id="36c0e-185">Verwenden Sie zum expliziten Definieren eines Verbindungsvorgangs die `Join`-Klausel anstelle der `Where`-Klausel, bei der ein Verbindungsvorgang implizit definiert wird:</span><span class="sxs-lookup"><span data-stu-id="36c0e-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="36c0e-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36c0e-186">See also</span></span>

- [<span data-ttu-id="36c0e-187">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="36c0e-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
