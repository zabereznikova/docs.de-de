---
title: Dokumentieren von Code mit XML-Kommentaren
description: Informationen zum Dokumentieren Ihres Codes mit XML-Dokumentationskommentaren und zum Erstellen einer XML-Dokumentationsdatei zum Zeitpunkt der Kompilierung.
ms.date: 02/14/2017
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: c858a92309710a0ac6b68e9194f2d7ef4c9577a0
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140666"
---
# <a name="documenting-your-code-with-xml-comments"></a><span data-ttu-id="a153c-103">Dokumentieren von Code mit XML-Kommentaren</span><span class="sxs-lookup"><span data-stu-id="a153c-103">Documenting your code with XML comments</span></span>

<span data-ttu-id="a153c-104">XML-Dokumentationskommentare sind eine besondere Art von Kommentaren, die über der Definition von benutzerdefinierten Typen oder Membern hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a153c-104">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span>
<span data-ttu-id="a153c-105">Sie sind besonders, da sie vom Compiler verarbeitet werden können, um eine XML-Dokumentationsdatei zur Kompilierzeit zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-105">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="a153c-106">Die vom Compiler generierte XML-Datei kann zusammen mit Ihrer .NET-Assembly verteilt werden, damit Visual Studio und andere IDEs mit IntelliSense QuickInfos über Typen oder Member anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="a153c-106">The compiler generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="a153c-107">Darüber hinaus kann die XML-Datei mithilfe von Tools wie [DocFX](https://dotnet.github.io/docfx/) und [Sandcastle](https://github.com/EWSoftware/SHFB) ausgeführt werden, um API-Verweiswebsites zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-107">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="a153c-108">XML-Dokumentationskommentare werden wie alle anderen Kommentare vom Compiler ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a153c-108">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="a153c-109">Sie können die XML-Datei zur Kompilierzeit generieren, indem Sie eine der folgenden Aktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="a153c-109">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="a153c-110">Wenn Sie eine Anwendung mit .NET Core über die Befehlszeile entwickeln, können Sie im Abschnitt `<PropertyGroup>` der CSPROJ-Projektdatei ein `GenerateDocumentationFile`-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a153c-110">If you are developing an application with .NET Core from the command line, you can add a `GenerateDocumentationFile` element to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="a153c-111">Ferner können Sie den Pfad zur Dokumentationsdatei direkt mithilfe des [`DocumentationFile`-Elements](/visualstudio/msbuild/common-msbuild-project-properties) angeben.</span><span class="sxs-lookup"><span data-stu-id="a153c-111">You can also specify the path to the documentation file directly using [`DocumentationFile` element](/visualstudio/msbuild/common-msbuild-project-properties).</span></span> <span data-ttu-id="a153c-112">Im folgenden Beispiel wird eine XML-Datei im Projektverzeichnis mit dem gleichen Stammdateinamen wie die Assembly generiert:</span><span class="sxs-lookup"><span data-stu-id="a153c-112">The following example generates an XML file in the project directory with the same root filename as the assembly:</span></span>

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```
   
   <span data-ttu-id="a153c-113">Dieser Ausdruck ist äquivalent zu Folgendem:</span><span class="sxs-lookup"><span data-stu-id="a153c-113">This is equivalent to the following:</span></span>
   
   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

- <span data-ttu-id="a153c-114">Wenn Sie eine Anwendung mit Visual Studio entwickeln, klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a153c-114">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="a153c-115">Wählen Sie im Eigenschaftendialogfeld die Registerkarte **Erstellen** aus, und aktivieren Sie das Kontrollkästchen bei **XML-Dokumentationsdatei**.</span><span class="sxs-lookup"><span data-stu-id="a153c-115">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="a153c-116">Sie können auch den Speicherort ändern, an den der Compiler die Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="a153c-116">You can also change the location to which the compiler writes the file.</span></span>

- <span data-ttu-id="a153c-117">Wenn Sie eine .NET Framework-Anwendung über die Befehlszeile kompilieren, fügen Sie beim Kompilieren die [-doc-Compileroption](language-reference/compiler-options/doc-compiler-option.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="a153c-117">If you are compiling a .NET Framework application from the command line, add the [-doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="a153c-118">XML-Dokumentationskommentare verwenden dreifache Schrägstriche (`///`) und einen Kommentartext im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="a153c-118">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="a153c-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a153c-119">For example:</span></span>

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a><span data-ttu-id="a153c-120">Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="a153c-120">Walkthrough</span></span>

<span data-ttu-id="a153c-121">Betrachten wir das Dokumentieren einer sehr einfachen math-Bibliothek, um neuen Entwicklern das Verstehen/Beitragen und Entwicklern von Drittanbietern das Verwenden zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="a153c-121">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third party developers to use.</span></span>

<span data-ttu-id="a153c-122">Hier der Code für die einfache math-Bibliothek:</span><span class="sxs-lookup"><span data-stu-id="a153c-122">Here's code for the simple math library:</span></span>

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

<span data-ttu-id="a153c-123">Die Beispielbibliothek unterstützt die vier wichtigen arithmetischen Operationen `add`, `subtract`, `multiply` und `divide` auf den Datentypen `int` und `double`.</span><span class="sxs-lookup"><span data-stu-id="a153c-123">The sample library supports four major arithmetic operations `add`, `subtract`, `multiply` and `divide` on `int` and `double` data types.</span></span>

<span data-ttu-id="a153c-124">Nun möchten Sie in der Lage sein, ein API-Referenzdokument aus dem Code für Entwickler von Drittanbietern zu erstellen, die Ihre Bibliothek verwenden, aber keinen Zugriff auf den Quellcode haben.</span><span class="sxs-lookup"><span data-stu-id="a153c-124">Now you want to be able to create an API reference document from your code for third party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="a153c-125">Wie bereits in der vorhandenen Dokumentation zu XML zu lesen ist, können Tags verwendet werden, um dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="a153c-125">As mentioned earlier XML documentation tags can be used to achieve this.</span></span> <span data-ttu-id="a153c-126">Im Folgenden stellen wir Ihnen die XML-Standardtags vor, die vom C#-Compiler unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a153c-126">You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

## <a name="summary"></a><span data-ttu-id="a153c-127">\<summary></span><span class="sxs-lookup"><span data-stu-id="a153c-127">\<summary></span></span>

<span data-ttu-id="a153c-128">Das `<summary>`-Tag fügt kurze Informationen über einen Typ oder Member hinzu.</span><span class="sxs-lookup"><span data-stu-id="a153c-128">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="a153c-129">Die Verwendung wird veranschaulicht, indem es zur `Math`-Klassendefinition und zur ersten `Add`-Methode hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a153c-129">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="a153c-130">Sie können es gerne auf den Rest Ihres Codes anwenden.</span><span class="sxs-lookup"><span data-stu-id="a153c-130">Feel free to apply it to the rest of your code.</span></span>

[!code-csharp[Summary Tag](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

<span data-ttu-id="a153c-131">Das `<summary>`-Tag ist sehr wichtig, und es wird empfohlen, dass Sie es einfügen, da sein Inhalt die primäre Quelle für Informationen über Typ oder Member in IntelliSense oder in einem API-Referenzdokument ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-131">The `<summary>` tag is very important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

## <a name="remarks"></a><span data-ttu-id="a153c-132">\<remarks></span><span class="sxs-lookup"><span data-stu-id="a153c-132">\<remarks></span></span>

<span data-ttu-id="a153c-133">Das `<remarks>`-Tag ergänzt die Informationen über Typen oder Member, die das `<summary>`-Tag enthält.</span><span class="sxs-lookup"><span data-stu-id="a153c-133">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="a153c-134">In diesem Beispiel fügen Sie es einfach der Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="a153c-134">In this example, you'll just add it to the class.</span></span>

[!code-csharp[Remarks Tag](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## <a name="returns"></a><span data-ttu-id="a153c-135">\<returns></span><span class="sxs-lookup"><span data-stu-id="a153c-135">\<returns></span></span>

<span data-ttu-id="a153c-136">Das `<returns>`-Tag beschreibt den Rückgabewert der Deklaration einer Methode.</span><span class="sxs-lookup"><span data-stu-id="a153c-136">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="a153c-137">Wie zuvor veranschaulicht das folgende Beispiel das `<returns>`-Tag bei der ersten `Add`-Methode.</span><span class="sxs-lookup"><span data-stu-id="a153c-137">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="a153c-138">Sie können dasselbe bei anderen Methoden vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a153c-138">You can do the same on other methods.</span></span>

[!code-csharp[Returns Tag](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## <a name="value"></a><span data-ttu-id="a153c-139">\<Wert></span><span class="sxs-lookup"><span data-stu-id="a153c-139">\<value></span></span>

<span data-ttu-id="a153c-140">Das `<value>`-Tag ist mit dem `<returns>`-Tag vergleichbar, wird aber für Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="a153c-140">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="a153c-141">Falls Ihre `Math`-Bibliothek über eine statische Eigenschaft namens `PI` verfügt, können Sie dieses Tag wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="a153c-141">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

[!code-csharp[Value Tag](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## <a name="example"></a><span data-ttu-id="a153c-142">\<example></span><span class="sxs-lookup"><span data-stu-id="a153c-142">\<example></span></span>

<span data-ttu-id="a153c-143">Das `<example>`-Tag wird verwendet, um ein Beispiel in die XML-Dokumentation aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="a153c-143">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="a153c-144">Dies beinhaltet die Verwendung des untergeordneten `<code>`-Tags.</span><span class="sxs-lookup"><span data-stu-id="a153c-144">This involves using the child `<code>` tag.</span></span>

[!code-csharp[Example Tag](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

<span data-ttu-id="a153c-145">Das `code`-Tag behält Zeilenumbrüche und Einzug für längere Beispiele bei.</span><span class="sxs-lookup"><span data-stu-id="a153c-145">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

## <a name="para"></a><span data-ttu-id="a153c-146">\<para></span><span class="sxs-lookup"><span data-stu-id="a153c-146">\<para></span></span>

<span data-ttu-id="a153c-147">Das `<para>`-Tag wird verwendet, um den Inhalt innerhalb seines übergeordneten Tags zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-147">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="a153c-148">`<para>` wird in der Regel innerhalb eines Tags wie `<remarks>` oder `<returns>` verwendet, um Text in Absätze zu unterteilen.</span><span class="sxs-lookup"><span data-stu-id="a153c-148">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="a153c-149">Sie können die Inhalte des `<remarks>`-Tags für Ihre Klassendefinition formatieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-149">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

[!code-csharp[Para Tag](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## <a name="c"></a><span data-ttu-id="a153c-150">\<c></span><span class="sxs-lookup"><span data-stu-id="a153c-150">\<c></span></span>

<span data-ttu-id="a153c-151">Bei der Formatierung wird außerdem das `<c>`-Tag verwendet, um einen Teil des Texts als Code zu markieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-151">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="a153c-152">Es ist wie das `<code>`-Tag, aber inline.</span><span class="sxs-lookup"><span data-stu-id="a153c-152">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="a153c-153">Es ist nützlich, wenn Sie ein schnelles Codebeispiel als Teil des Taginhalts anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="a153c-153">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="a153c-154">Aktualisieren wir die Dokumentation für die `Math`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="a153c-154">Let's update the documentation for the `Math` class.</span></span>

[!code-csharp[C Tag](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## <a name="exception"></a><span data-ttu-id="a153c-155">\<exception></span><span class="sxs-lookup"><span data-stu-id="a153c-155">\<exception></span></span>

<span data-ttu-id="a153c-156">Mithilfe des `<exception>`-Tags können Sie Ihre Entwickler wissen lassen, dass eine Methode bestimmte Ausnahmen auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="a153c-156">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="a153c-157">In Ihrer `Math`-Bibliothek sehen Sie, dass beide `Add`-Methoden eine Ausnahme auslösen, wenn eine bestimmte Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-157">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="a153c-158">Nicht so offensichtlich ist jedoch, dass die ganzzahlige `Divide`-Methode auch auslöst, wenn der `b`-Parameter null ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-158">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="a153c-159">Fügen Sie nun eine Ausnahmendokumentation zu dieser Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="a153c-159">Now add exception documentation to this method.</span></span>

[!code-csharp[Exception Tag](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

<span data-ttu-id="a153c-160">Das `cref`-Attribut stellt einen Verweis auf eine Ausnahme dar, die von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-160">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="a153c-161">Dies kann jeder Typ sein, der im Projekt definiert ist, oder eine Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a153c-161">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="a153c-162">Der Compiler wird eine Warnung ausgeben, wenn sein Wert nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="a153c-162">The compiler will issue a warning if its value cannot be resolved.</span></span>

## <a name="see"></a><span data-ttu-id="a153c-163">\<see></span><span class="sxs-lookup"><span data-stu-id="a153c-163">\<see></span></span>

<span data-ttu-id="a153c-164">Das `<see>`-Tag ermöglicht die Erstellung eines klickbaren Links zu einer Dokumentationsseite für ein anderes Codeelement.</span><span class="sxs-lookup"><span data-stu-id="a153c-164">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="a153c-165">Im nächsten Beispiel wird ein klickbarer Link zwischen den beiden `Add`-Methoden erstellt.</span><span class="sxs-lookup"><span data-stu-id="a153c-165">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

[!code-csharp[See Tag](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

<span data-ttu-id="a153c-166">Das `cref`-Attribut ist ein **erforderliches** Attribut, das einen Verweis auf einen Typ oder auf dessen Member darstellt, der von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-166">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="a153c-167">Dies kann jeder Typ sein, der im Projekt definiert ist, oder eine Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a153c-167">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="seealso"></a><span data-ttu-id="a153c-168">\<seealso></span><span class="sxs-lookup"><span data-stu-id="a153c-168">\<seealso></span></span>

<span data-ttu-id="a153c-169">Das `<seealso>`-Tag wird auf die gleiche Weise verwendet wie das `<see>`-Tag.</span><span class="sxs-lookup"><span data-stu-id="a153c-169">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="a153c-170">Der einzige Unterschied ist, dass dessen Inhalt in der Regel in einem „See Also“-Abschnitt („Siehe auch“) platziert wird.</span><span class="sxs-lookup"><span data-stu-id="a153c-170">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="a153c-171">Hier fügen wir ein `seealso`-Tag auf die ganzzahlige `Add`-Methode hinzu, um auf andere Methoden in der Klasse zu verweisen, die ganzzahlige Parameter akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="a153c-171">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

[!code-csharp[Seealso Tag](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

<span data-ttu-id="a153c-172">Das `cref`-Attribut stellt einen Verweis auf einen Typ oder auf dessen Member dar, der von der aktuellen Kompilierungsumgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-172">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="a153c-173">Dies kann jeder Typ sein, der im Projekt definiert ist, oder eine Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a153c-173">This can be any type defined in the project or a referenced assembly.</span></span>

## <a name="param"></a><span data-ttu-id="a153c-174">\<param></span><span class="sxs-lookup"><span data-stu-id="a153c-174">\<param></span></span>

<span data-ttu-id="a153c-175">Das `<param>`-Tag wird verwendet, um die Parameter einer Methode zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a153c-175">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="a153c-176">Hier sehen Sie ein Beispiel für die doppelte `Add`-Methode: Der Parameter, den der Tag beschreibt, ist im **erforderlichen** `name`-Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="a153c-176">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Param Tag](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## <a name="typeparam"></a><span data-ttu-id="a153c-177">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="a153c-177">\<typeparam></span></span>

<span data-ttu-id="a153c-178">Das `<typeparam>`-Tag wird genau wie das `<param>`-Tag verwendet, aber für den generischen Typ oder Methodendeklarationen, um einen generischen Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a153c-178">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="a153c-179">Fügen Sie der `Math`-Klasse eine schnelle generische Methode hinzu, um zu überprüfen, ob eine Menge größer als die andere ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-179">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

[!code-csharp[Typeparam Tag](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## <a name="paramref"></a><span data-ttu-id="a153c-180">\<paramref></span><span class="sxs-lookup"><span data-stu-id="a153c-180">\<paramref></span></span>

<span data-ttu-id="a153c-181">Manchmal beschreiben Sie möglicherweise gerade die Funktionsweise einer Methode in einem möglichen `<summary>`-Tag und wollen dann auf einen Parameter verweisen.</span><span class="sxs-lookup"><span data-stu-id="a153c-181">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="a153c-182">Der `<paramref>`-Tag eignet sich hervorragend dafür.</span><span class="sxs-lookup"><span data-stu-id="a153c-182">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="a153c-183">Aktualisieren wir die Zusammenfassung der doppelt basierten `Add`-Methode.</span><span class="sxs-lookup"><span data-stu-id="a153c-183">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="a153c-184">Wie beim `<param>`-Tag wird der Name des Parameters im **erforderlichen** `name`-Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="a153c-184">Like the `<param>` tag the parameter name is specified in the **required** `name` attribute.</span></span>

[!code-csharp[Paramref Tag](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## <a name="typeparamref"></a><span data-ttu-id="a153c-185">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="a153c-185">\<typeparamref></span></span>

<span data-ttu-id="a153c-186">Das `<typeparamref>`-Tag wird genau wie das `<paramref>`-Tag verwendet, aber für den generischen Typ oder Methodendeklarationen, um einen generischen Parameter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a153c-186">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="a153c-187">Sie können die gleiche generische Methode verwenden, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a153c-187">You can use the same generic method you previously created.</span></span>

[!code-csharp[Typeparamref Tag](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## <a name="list"></a><span data-ttu-id="a153c-188">\<list></span><span class="sxs-lookup"><span data-stu-id="a153c-188">\<list></span></span>

<span data-ttu-id="a153c-189">Das `<list>`-Tag wird verwendet, um Dokumentationsinformationen als sortierte Liste, unsortierte Liste oder Tabelle zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-189">You use the `<list>` tag to format documentation information as an ordered list, unordered list or table.</span></span>
<span data-ttu-id="a153c-190">Erstellen Sie eine unsortierte Liste aller mathematischen Operationen, die Ihre `Math`-Bibliothek unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a153c-190">Make an unordered list of every math operation your `Math` library supports.</span></span>

[!code-csharp[List Tag](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

<span data-ttu-id="a153c-191">Sie können eine sortierte Liste oder eine Tabelle erstellen, indem Sie das Attribut `type` auf `number` bzw. `table` ändern.</span><span class="sxs-lookup"><span data-stu-id="a153c-191">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="a153c-192">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="a153c-192">Putting it all together</span></span>

<span data-ttu-id="a153c-193">Wenn Sie diesem Tutorial gefolgt sind und die Tags soweit erforderlich für Ihren Code übernommen haben, sollte Ihr Code nun ähnlich wie der folgende aussehen:</span><span class="sxs-lookup"><span data-stu-id="a153c-193">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

[!code-csharp[Tagged Library](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

<span data-ttu-id="a153c-194">Aus Ihrem Code können Sie eine detaillierte Dokumentationswebsite mit klickbaren Querverweisen generieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-194">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="a153c-195">Sie sehen sich jedoch mit einem anderen Problem konfrontiert: Ihr Code ist schwer zu lesen.</span><span class="sxs-lookup"><span data-stu-id="a153c-195">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="a153c-196">Dies ist ein Albtraum für jeden Entwickler, der zu diesem Code beitragen möchte, da er so viele Informationen durchsuchen muss.</span><span class="sxs-lookup"><span data-stu-id="a153c-196">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span>
<span data-ttu-id="a153c-197">Zum Glück gibt es ein XML-Tag, das Ihnen dabei helfen kann:</span><span class="sxs-lookup"><span data-stu-id="a153c-197">Thankfully there's an XML tag that can help you deal with this:</span></span>

## <a name="include"></a><span data-ttu-id="a153c-198">\<include></span><span class="sxs-lookup"><span data-stu-id="a153c-198">\<include></span></span>

<span data-ttu-id="a153c-199">Mit dem `<include>`-Tag kann auf Kommentare in einer separaten XML-Datei verwiesen werden, die die Typen und Member im Quellcode beschreibt, anstatt Dokumentationskommentare direkt in der Quellcodedatei zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-199">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="a153c-200">Nun verschieben Sie alle XML-Tags in eine separate XML-Datei mit dem Namen `docs.xml`.</span><span class="sxs-lookup"><span data-stu-id="a153c-200">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="a153c-201">Sie können die Datei beliebig benennen.</span><span class="sxs-lookup"><span data-stu-id="a153c-201">Feel free to name the file whatever you want.</span></span>

[!code-xml[Sample XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]

<span data-ttu-id="a153c-202">Im obigen XML werden die Dokumentationskommentare jedes Members direkt innerhalb eines Tags angezeigt, das nach der Funktion benannt ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-202">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="a153c-203">Sie können Ihre eigene Strategie auswählen.</span><span class="sxs-lookup"><span data-stu-id="a153c-203">You can choose your own strategy.</span></span>
<span data-ttu-id="a153c-204">Ihre XML-Kommentare befinden sich nun in einer separaten Datei. Sehen wir uns an, wie der Code mit dem `<include>`-Tag besser lesbar gemacht werden kann:</span><span class="sxs-lookup"><span data-stu-id="a153c-204">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

[!code-csharp[Include Tag](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

<span data-ttu-id="a153c-205">Nun ist der Code wieder gut lesbar, und es sind keine Dokumentationsinformationen verloren gegangen.</span><span class="sxs-lookup"><span data-stu-id="a153c-205">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span>

<span data-ttu-id="a153c-206">Das `file`-Attribut stellt den Namen der XML-Datei dar, die die Dokumentation enthält.</span><span class="sxs-lookup"><span data-stu-id="a153c-206">The `file` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="a153c-207">Das `path`-Attribut stellt eine [XPath](../standard/data/xml/xpath-queries-and-namespaces.md)-Abfrage an den vorhandenen `tag name` im angegebenen `file` dar.</span><span class="sxs-lookup"><span data-stu-id="a153c-207">The `path` attribute represents an [XPath](../standard/data/xml/xpath-queries-and-namespaces.md) query to the `tag name` present in the specified `file`.</span></span>

<span data-ttu-id="a153c-208">Das `name`-Attribut stellt den Namensbezeichner in dem Tag dar, das sich vor den Kommentaren befindet.</span><span class="sxs-lookup"><span data-stu-id="a153c-208">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="a153c-209">Das `id`-Attribut, das anstelle von `name` verwendet werden kann, stellt die ID für das Tag dar, das sich vor den Kommentaren befindet.</span><span class="sxs-lookup"><span data-stu-id="a153c-209">The `id` attribute which can be used in place of `name` represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="a153c-210">Benutzerdefinierte Tags</span><span class="sxs-lookup"><span data-stu-id="a153c-210">User Defined Tags</span></span>

<span data-ttu-id="a153c-211">Alle oben genannten Tags werden vom C#-Compiler erkannt.</span><span class="sxs-lookup"><span data-stu-id="a153c-211">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="a153c-212">Ein Benutzer kann jedoch auch eigene Tags definieren.</span><span class="sxs-lookup"><span data-stu-id="a153c-212">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="a153c-213">Tools wie Sandcastle bieten Unterstützung für zusätzliche Tags wie [`<event>`](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) oder [`<note>`](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) und unterstützen sogar [documenting namespaces (Dokumentieren von Namespaces)](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span><span class="sxs-lookup"><span data-stu-id="a153c-213">Tools like Sandcastle bring support for extra tags like [`<event>`](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) and even support [documenting namespaces](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="a153c-214">Benutzerdefinierte oder interne Dokumentationsgenerierungstools können auch mit den Standardtags verwendet werden, und mehrere Ausgabeformate von HTML in PDF können unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a153c-214">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="a153c-215">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="a153c-215">Recommendations</span></span>

<span data-ttu-id="a153c-216">Das Dokumentieren von Code wird aus vielen Gründen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a153c-216">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="a153c-217">Es folgen einige bewährte Methoden, allgemeine Anwendungsfallszenarios und Dinge, die Sie wissen sollten, wenn Sie XML-Dokumentationstags in Ihrem C#-Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="a153c-217">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

- <span data-ttu-id="a153c-218">Aus Gründen der Konsistenz sollten alle öffentlich sichtbaren Typen und deren Member dokumentiert werden.</span><span class="sxs-lookup"><span data-stu-id="a153c-218">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="a153c-219">Tun Sie dies wenn nötig vollständig.</span><span class="sxs-lookup"><span data-stu-id="a153c-219">If you must do it, do it all.</span></span>
- <span data-ttu-id="a153c-220">Private Member können auch mithilfe von XML-Kommentaren dokumentiert werden.</span><span class="sxs-lookup"><span data-stu-id="a153c-220">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="a153c-221">Dadurch wird jedoch das (potenziell vertrauliche) Innenleben Ihrer Bibliothek verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="a153c-221">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
- <span data-ttu-id="a153c-222">Als absolutes Minimum sollten Typen und deren Member über ein `<summary>`-Tag verfügen, da dessen Inhalt für IntelliSense erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a153c-222">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
- <span data-ttu-id="a153c-223">Dokumentationstext sollte in vollständigen Sätze geschrieben werden, die mit Punkten enden.</span><span class="sxs-lookup"><span data-stu-id="a153c-223">Documentation text should be written using complete sentences ending with full stops.</span></span>
- <span data-ttu-id="a153c-224">Partielle Klassen werden vollständig unterstützt, und Dokumentationsinformationen werden zu einem einzigen Eintrag für diesen Typ verkettet.</span><span class="sxs-lookup"><span data-stu-id="a153c-224">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
- <span data-ttu-id="a153c-225">Der Compiler überprüft die Syntax der Tags `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` und `<typeparam>`.</span><span class="sxs-lookup"><span data-stu-id="a153c-225">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` and `<typeparam>` tags.</span></span>
- <span data-ttu-id="a153c-226">Der Compiler überprüft die Parameter, die Dateipfade und Verweise auf andere Teile des Codes enthalten.</span><span class="sxs-lookup"><span data-stu-id="a153c-226">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="a153c-227">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a153c-227">See also</span></span>

- [<span data-ttu-id="a153c-228">XML-Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a153c-228">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/index.md)
- [<span data-ttu-id="a153c-229">Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a153c-229">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
