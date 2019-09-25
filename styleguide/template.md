---
title:
- ARTIKELTITEL
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - MM/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: 3cd1096a07b1de39d1961fdc8c5add56604804ea
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151835"
---
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="d90a0-102">Metadaten und Markdownvorlage</span><span class="sxs-lookup"><span data-stu-id="d90a0-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="d90a0-103">Diese dotnet/docs-Vorlage enthält Beispiele der Markdownsyntax sowie einen Leitfaden zum Festlegen der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="d90a0-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="d90a0-104">Um die Vorlage bestmöglich zu nutzen, müssen Sie sowohl das [unformatierte Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) als auch die [gerenderte Ansicht](https://github.com/dotnet/docs/blob/master/styleguide/template.md) anzeigen (beispielsweise zeigt das unformatierte Markdown, anders als die gerenderte Ansicht, den Metadatenblock an).</span><span class="sxs-lookup"><span data-stu-id="d90a0-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (for instance, the raw Markdown shows the metadata block, while the rendered view does not).</span></span>

<span data-ttu-id="d90a0-105">Beim Erstellen einer Markdowndatei sollten Sie diese Vorlage in eine neue Datei kopieren, die Metadaten wie nachstehend angegeben ausfüllen, den H1-Header oben als Titel des Artikels festlegen und den Inhalt löschen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="d90a0-106">Metadaten</span><span class="sxs-lookup"><span data-stu-id="d90a0-106">Metadata</span></span>

<span data-ttu-id="d90a0-107">Der vollständige Metadatenblock befindet sich oben (im [unformatierten Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), unterteilt in erforderliche Felder und optionale Felder.</span><span class="sxs-lookup"><span data-stu-id="d90a0-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="d90a0-108">Wichtige Hinweise:</span><span class="sxs-lookup"><span data-stu-id="d90a0-108">Some key notes:</span></span>

- <span data-ttu-id="d90a0-109">Bei einem Metadatenelement **muss** ein Leerzeichen zwischen dem Doppelpunkt (:) und dem Wert stehen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="d90a0-110">Wenn ein optionales Metadatenelement keinen Wert hat, kommentieren Sie das Element mit einem #-Zeichen aus, oder entfernen Sie es. (Lassen Sie es nicht leer und verwenden Sie kein „k.A.“.)</span><span class="sxs-lookup"><span data-stu-id="d90a0-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="d90a0-111">Wenn Sie einen Wert zu einem auskommentierten Element hinzufügen, müssen Sie das #-Zeichen entfernen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="d90a0-112">Doppelpunkte in einem Wert (z.B. einem Titel) unterbrechen den Metadatenparser.</span><span class="sxs-lookup"><span data-stu-id="d90a0-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="d90a0-113">In diesem Fall setzen Sie den Titel in doppelte Anführungszeichen (z.B. `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="d90a0-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="d90a0-114">**title**: Wird in Suchmaschinenergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="d90a0-115">Der Titel darf nicht mit dem Titel in Ihrem H1-Header übereinstimmen, und er sollte höchstens 60 Zeichen umfassen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="d90a0-116">**description**: Bietet eine Zusammenfassung des Artikelinhalts.</span><span class="sxs-lookup"><span data-stu-id="d90a0-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="d90a0-117">Diese wird normalerweise auf der Seite mit den Suchergebnissen angezeigt, hat auf den Rang in den Suchergebnissen jedoch keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="d90a0-118">Die Länge sollte 115-145 Zeichen (einschließlich Leerzeichen) betragen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="d90a0-119">**author** und **ms.author**: Das Feld „author“ sollte den **GitHub-Benutzernamen** des Autors enthalten, nicht dessen Alias.</span><span class="sxs-lookup"><span data-stu-id="d90a0-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="d90a0-120">Das Feld **ms.author** hingegen sollte einen Microsoft-Alias enthalten und die für die Verwaltung des Artikels verantwortliche Person angeben.</span><span class="sxs-lookup"><span data-stu-id="d90a0-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="d90a0-121">**ms.topic**: Der Thementyp.</span><span class="sxs-lookup"><span data-stu-id="d90a0-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="d90a0-122">Der häufigste Wert ist `conceptual` und wird auf globaler Ebene festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="d90a0-123">Andere gängige Werte sind `tutorial`, `overview` und `reference`.</span><span class="sxs-lookup"><span data-stu-id="d90a0-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="d90a0-124">**ms.devlang** definiert den für das Thema angezeigten Sprachfilter.</span><span class="sxs-lookup"><span data-stu-id="d90a0-124">**ms.devlang** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="d90a0-125">Eine Liste der unterstützten Werte finden Sie im Abschnitt [Unterstützte Sprachen](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="d90a0-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="d90a0-126">Dieser Wert muss nur festgelegt werden, wenn mehr als eine Programmiersprache im Thema abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="d90a0-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="d90a0-127">In der Regel verwenden wir in unserem Inhalt nur `csharp`, `vb`, `fsharp` und `cpp` für diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="d90a0-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="d90a0-128">**ms.prod**: Die für BI-Zwecke verwendete Produktidentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d90a0-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="d90a0-129">Sie werden normalerweise auf globaler Ebene festgelegt und daher für gewöhnlich nicht im Metadatenblock jedes Artikels angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="d90a0-130">**ms.technology**: Zusätzliche BI-Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="d90a0-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="d90a0-131">Dies sind einige der unterstützten Werte: `devlang-csharp` für C#-Themen, `devlang-fsharp` für F#-Themen und `devlang-visual-basic` für VB-Themen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="d90a0-132">Da bei anderen Leitfäden die Werte variieren, wenden Sie sich bitte an ein Teammitglied.</span><span class="sxs-lookup"><span data-stu-id="d90a0-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="d90a0-133">**ms.date**: Ein Datum im Format MM/TT/JJJJ.</span><span class="sxs-lookup"><span data-stu-id="d90a0-133">**ms.date**: A date in the format MM/dd/yyyy.</span></span> <span data-ttu-id="d90a0-134">Wird auf der veröffentlichten Seite angezeigt und gibt das Datum der letzten wesentlichen Bearbeitung des Artikels an bzw. garantiert dessen Aktualität (d.h. der Artikel wurde überprüft und als aktuell eingestuft).</span><span class="sxs-lookup"><span data-stu-id="d90a0-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="d90a0-135">**helpviewer_keywords**: Einträge werden für den Index der Offlinebücher verwendet (Funktionalität in Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="d90a0-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="d90a0-136">**f1_keywords**: Verbindet den Artikel mit der F1-Taste (Funktionalität in Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="d90a0-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="d90a0-137">Grundlegendes Markdown, GFM und Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="d90a0-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="d90a0-138">Alles grundlegende Markdown sowie GitHub Flavored Markdown (GFM) wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="d90a0-139">Weitere Informationen dazu finden Sie auf den folgenden Seiten:</span><span class="sxs-lookup"><span data-stu-id="d90a0-139">For more information on these, see:</span></span>

- [<span data-ttu-id="d90a0-140">Grundlegende Markdownsyntax</span><span class="sxs-lookup"><span data-stu-id="d90a0-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="d90a0-141">GFM-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="d90a0-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="d90a0-142">Markdown verwendet Sonderzeichen wie z.B. \*, \`, und \# für die Formatierung.</span><span class="sxs-lookup"><span data-stu-id="d90a0-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="d90a0-143">Wenn Sie eines dieser Zeichen in Ihren Inhalt einschließen möchten, müssen Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="d90a0-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="d90a0-144">Setzen Sie einen umgekehrten Schrägstrich vor das Sonderzeichen, um es mit einem Escapezeichen zu versehen (z.B. `\*` für \*)</span><span class="sxs-lookup"><span data-stu-id="d90a0-144">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="d90a0-145">Verwenden Sie den [HTML-Entitätscode](https://www.ascii.cl/htmlcodes.htm) für das Zeichen (z.B. `&#42;` für ein &#42;).</span><span class="sxs-lookup"><span data-stu-id="d90a0-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="d90a0-146">Dateiname</span><span class="sxs-lookup"><span data-stu-id="d90a0-146">File name</span></span>

<span data-ttu-id="d90a0-147">Dateinamen verwenden die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="d90a0-147">File names use the following rules:</span></span>

- <span data-ttu-id="d90a0-148">Es sollten nur Kleinbuchstaben, Zahlen und Bindestriche enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="d90a0-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="d90a0-149">Keine Leer- oder Interpunktionszeichen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="d90a0-150">Trennen Sie Worte und Zahlen im Dateinamen durch Bindestriche.</span><span class="sxs-lookup"><span data-stu-id="d90a0-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="d90a0-151">Verwenden Sie Verben, die den Zweck angeben, z.B. develop, buy, build, troubleshoot.</span><span class="sxs-lookup"><span data-stu-id="d90a0-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="d90a0-152">Keine auf „-ing“ endenden Worte dürfen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-152">No -ing words.</span></span>
- <span data-ttu-id="d90a0-153">Keine kurzen Worte wie a, and, the, in, or usw. sind erlaubt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="d90a0-154">Muss in Markdown geschrieben werden und die Dateierweiterung .md verwenden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="d90a0-155">Halten Sie Dateinamen einigermaßen kurz.</span><span class="sxs-lookup"><span data-stu-id="d90a0-155">Keep file names reasonably short.</span></span> <span data-ttu-id="d90a0-156">Sie sind Teil der URL für Ihre Artikel.</span><span class="sxs-lookup"><span data-stu-id="d90a0-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="d90a0-157">Kopfzeilen</span><span class="sxs-lookup"><span data-stu-id="d90a0-157">Headings</span></span>

<span data-ttu-id="d90a0-158">Verwenden Sie die übliche Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="d90a0-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="d90a0-159">Schreiben Sie das erste Wort einer Überschrift immer groß, und beachten Sie die Regeln der Groß- und Kleinschreibung nach Doppelpunkten (z. B. „Vorgehensweise: Sortieren eines Arrays“).</span><span class="sxs-lookup"><span data-stu-id="d90a0-159">Always capitalize the first word of a heading, but don't capitalize the word following a colon in a title or heading (for example, "How to: sort an array").</span></span>

<span data-ttu-id="d90a0-160">Überschriften sollten mithilfe des atx-Stils erstellt werden, d.h. es sollten 1-6 Hash-Zeichen (#) am Anfang der Zeile verwendet werden, um eine Überschrift anzugeben, entsprechend der HTML-Überschriftenebenen H1 bis H6.</span><span class="sxs-lookup"><span data-stu-id="d90a0-160">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="d90a0-161">Beispiele für Header der ersten und zweiten Ebene werden oben verwendet.</span><span class="sxs-lookup"><span data-stu-id="d90a0-161">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="d90a0-162">In Ihrem Thema **darf** nur eine Überschrift der ersten Ebene (H1) enthalten sein, die als Titel auf der Seite angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d90a0-162">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="d90a0-163">Wenn Ihre Überschrift mit dem Zeichen `#` endet, müssen Sie ein zusätzliches `#`-Zeichen am Ende einfügen, damit der Titel richtig gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="d90a0-163">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="d90a0-164">Beispiel: `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="d90a0-164">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="d90a0-165">Überschriften der zweiten Ebene generieren das Inhaltsverzeichnis auf der Seite, das im Abschnitt „In diesem Artikel“ unterhalb des Titels auf der Seite angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d90a0-165">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="d90a0-166">Überschrift der dritten Ebene</span><span class="sxs-lookup"><span data-stu-id="d90a0-166">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="d90a0-167">Überschrift der vierten Ebene</span><span class="sxs-lookup"><span data-stu-id="d90a0-167">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="d90a0-168">Überschrift der fünften Ebene</span><span class="sxs-lookup"><span data-stu-id="d90a0-168">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="d90a0-169">Überschrift der sechsten Ebene</span><span class="sxs-lookup"><span data-stu-id="d90a0-169">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="d90a0-170">Textstil</span><span class="sxs-lookup"><span data-stu-id="d90a0-170">Text styling</span></span>

<span data-ttu-id="d90a0-171">*Kursiv*: wird für Dateien, Ordner, Pfade (lange Pfade sollten in einer eigenen Zeile stehen), neue Begriffe verwendet.</span><span class="sxs-lookup"><span data-stu-id="d90a0-171">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="d90a0-172">**Fett** wird für Benutzeroberflächenelemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="d90a0-172">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="d90a0-173">`Code`: wird für Inline-Code, Sprachschlüsselwörter, NuGet-Paketnamen, Befehlszeilenbefehle, Datenbanktabellen und Spaltennamen sowie URLs verwendet, die nicht klickbar sein müssen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-173">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="d90a0-174">Links</span><span class="sxs-lookup"><span data-stu-id="d90a0-174">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="d90a0-175">Interne Links</span><span class="sxs-lookup"><span data-stu-id="d90a0-175">Internal Links</span></span>

<span data-ttu-id="d90a0-176">Um auf einen Header in der gleichen Markdowndatei zu verlinken (auch als Ankerlinks bekannt), müssen Sie die ID des Headers ermitteln, auf den Sie verlinken möchten.</span><span class="sxs-lookup"><span data-stu-id="d90a0-176">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="d90a0-177">Um die ID zu bestätigen, zeigen Sie die Quelle des gerenderten Artikels an, suchen Sie nach der ID des Headers (z.B. `id="blockquote"`), und erstellen Sie den Link mithilfe von # + ID (z.B. `#blockquote`).</span><span class="sxs-lookup"><span data-stu-id="d90a0-177">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="d90a0-178">Die ID wird basierend auf dem Headertext automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="d90a0-178">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="d90a0-179">Wenn also beispielsweise ein eindeutiger Abschnitt `## Step 2` genannt wird, sieht die ID folgendermaßen aus: `id="step-2"`.</span><span class="sxs-lookup"><span data-stu-id="d90a0-179">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="d90a0-180">Beispiel: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` erzeugt [Deklarieren von Inlineblöcken mit einem Sprachbezeichner](#inline-code-blocks-with-language-identifier).</span><span class="sxs-lookup"><span data-stu-id="d90a0-180">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="d90a0-181">Um auf eine Markdowndatei im gleichen Repository zu verlinken, verwenden Sie [relative Links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), einschließlich „.md“ am Ende des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="d90a0-181">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="d90a0-182">Beispiel: `[Readme file](../README.md)` erzeugt [Infodatei](../README.md).</span><span class="sxs-lookup"><span data-stu-id="d90a0-182">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="d90a0-183">(Beachten Sie, dass bei Links die Groß-/Kleinschreibung beachtet wird.)</span><span class="sxs-lookup"><span data-stu-id="d90a0-183">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="d90a0-184">Beispiel: `[Welcome to .NET](../docs/welcome.md)` erzeugt [Willkommen bei .NET](../docs/welcome.md).</span><span class="sxs-lookup"><span data-stu-id="d90a0-184">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="d90a0-185">Um auf einen Header in einer Markdowndatei im gleichen Repository zu verlinken, verwenden Sie die relative Verlinkung + die Hashtag-Verlinkung.</span><span class="sxs-lookup"><span data-stu-id="d90a0-185">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="d90a0-186">Beispiel: `[.NET Community](../docs/welcome.md#open-source)` erzeugt [.NET-Community](../docs/welcome.md#open-source).</span><span class="sxs-lookup"><span data-stu-id="d90a0-186">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="d90a0-187">In den meisten Fällen verwenden wir die relativen Links und raten von der Verwendung von `~/` in Links ab, da sich relative Links in der Quelle auf GitHub auflösen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-187">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="d90a0-188">Wenn wir jedoch auf eine Datei in einem abhängigen Repository verweisen, verwenden wir das Zeichen `~/`, um den Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d90a0-188">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="d90a0-189">Da sich die Dateien im abhängigen Repository an einem anderen Ort in GitHub befinden, werden die Links nicht ordnungsgemäß mit relativen Links aufgelöst, unabhängig davon, wie sie geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-189">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="d90a0-190">Die C#-Sprachspezifikation und die Visual Basic-Sprachspezifikation sind in den .NET-Dokumenten enthalten, da die Quelle aus den Sprachrepositorys einbezogen wird.</span><span class="sxs-lookup"><span data-stu-id="d90a0-190">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="d90a0-191">Die Markdownquellen werden in den Repositorys [csharplang](https://github.com/dotnet/csharplang) und [visual basic](https://github.com/dotnet/vblang) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d90a0-191">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="d90a0-192">Links zur Spezifikation müssen auf die Quellverzeichnisse verweisen, in denen diese Spezifikationen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d90a0-192">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="d90a0-193">Für C# ist dies **~/_csharplang/spec** und für VB ist dies **~/_vblang/spec**.</span><span class="sxs-lookup"><span data-stu-id="d90a0-193">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="d90a0-194">Beispiel: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` erzeugt [C#-Abfrageausdrücke](~/_csharplang/spec/expressions.md#query-expressions).</span><span class="sxs-lookup"><span data-stu-id="d90a0-194">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="d90a0-195">Externe Links</span><span class="sxs-lookup"><span data-stu-id="d90a0-195">External Links</span></span>

<span data-ttu-id="d90a0-196">Um auf eine externe Datei zu verlinken, verwenden Sie als Link die vollständige URL.</span><span class="sxs-lookup"><span data-stu-id="d90a0-196">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="d90a0-197">Beispiel: `[GitHub](https://www.github.com)` erzeugt [GitHub](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="d90a0-197">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="d90a0-198">Wenn in einer Markdowndatei eine URL erscheint, wird diese in einen klickbaren Link verwandelt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-198">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="d90a0-199">Beispiel: `<https://www.github.com>` erzeugt <https://www.github.com>.</span><span class="sxs-lookup"><span data-stu-id="d90a0-199">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="d90a0-200">Bevorzugen Sie für externe Links das `https`-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="d90a0-200">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="d90a0-201">Verwenden Sie `http`-Links nur für Websites, die `https` nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-201">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="d90a0-202">Links zu APIs</span><span class="sxs-lookup"><span data-stu-id="d90a0-202">Links to APIs</span></span>

<span data-ttu-id="d90a0-203">Das Buildsystem verfügt über einige Erweiterungen, die es ermöglichen, auf .NET-APIs zu verlinken, ohne externe Links verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-203">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="d90a0-204">Wenn auf eine API verlinkt wird, können Sie deren eindeutigen Bezeichner (UID) verwenden, der automatisch aus dem Quellcode generiert wird.</span><span class="sxs-lookup"><span data-stu-id="d90a0-204">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="d90a0-205">Die UID entspricht dem vollqualifizierten Typ und Membernamen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-205">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="d90a0-206">Wenn Sie ein \* (oder %2A) nach der UID hinzufügen, stellt der Link dann die Überladungsseite und nicht eine bestimmte API dar.</span><span class="sxs-lookup"><span data-stu-id="d90a0-206">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="d90a0-207">Dies können Sie beispielsweise verwenden, wenn Sie generisch auf die Seite [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) anstelle einer bestimmten Überladung wie [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_) verweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="d90a0-207">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="d90a0-208">Sie können auch \* verwenden, um einen Link zu einer Memberseite zu erstellen, wenn das Member nicht überladen ist; so müssen Sie die Parameterliste nicht in die UID einschließen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-208">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="d90a0-209">Wenn Sie einen Link zu einer bestimmten Methodenüberladung erstellen möchten, müssen Sie den vollqualifizierten Typnamen jedes einzelnen Parameters der Methode angeben.</span><span class="sxs-lookup"><span data-stu-id="d90a0-209">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="d90a0-210">\<xref:System.DateTime.ToString> ist beispielsweise mit der parameterlosen Methode [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) verknüpft, während \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> mit der Methode  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="d90a0-210">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="d90a0-211">Sie können die UIDs eines bestimmten überladenen Members auf `https://xref.docs.microsoft.com/autocomplete` finden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-211">You can find the UIDs of a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="d90a0-212">Die Abfragezeichenfolge „?text= *\<Typmembername>* “ identifiziert den Typ oder das Member, dessen UIDs angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-212">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="d90a0-213">Beispielsweise ruft `https://xref.docs.microsoft.com/autocomplete?text=string.format` die [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format)-Überladungen ab.</span><span class="sxs-lookup"><span data-stu-id="d90a0-213">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="d90a0-214">Zum Erstellen eines Links zu einem generischen Typ wie [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1) verwenden Sie das Zeichen \` (%60) gefolgt von der Anzahl von generischen Typparametern.</span><span class="sxs-lookup"><span data-stu-id="d90a0-214">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="d90a0-215">\<xref:System.Nullable%601> erstellt einen Link zum Typ [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), während \<xref:System.Func%602> einen Link zum Delegaten [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) erstellt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-215">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="d90a0-216">Sie können eine der folgenden Syntaxen verwenden:</span><span class="sxs-lookup"><span data-stu-id="d90a0-216">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="d90a0-217">Automatischer Link: `<xref:UID>` oder `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="d90a0-217">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="d90a0-218">Der `displayProperty`-Abfrageparameter erzeugt einen vollqualifizierten Linktext.</span><span class="sxs-lookup"><span data-stu-id="d90a0-218">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="d90a0-219">Im Linktext wird standardmäßig nur der Member- oder Typname angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-219">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="d90a0-220">Markdownlink: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="d90a0-220">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="d90a0-221">Verwenden Sie diesen, wenn Sie den angezeigten Linktext anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="d90a0-221">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="d90a0-222">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d90a0-222">Examples:</span></span>

- <span data-ttu-id="d90a0-223">`<xref:System.String>` wird als [String](https://docs.microsoft.com/dotnet/api/system.string) gerendert</span><span class="sxs-lookup"><span data-stu-id="d90a0-223">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="d90a0-224">`<xref:System.String?displayProperty=nameWithType>` wird als [System.String](https://docs.microsoft.com/dotnet/api/system.string) gerendert</span><span class="sxs-lookup"><span data-stu-id="d90a0-224">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="d90a0-225">`[String class](xref:System.String)` wird als [String Class](https://docs.microsoft.com/dotnet/api/system.string) gerendert</span><span class="sxs-lookup"><span data-stu-id="d90a0-225">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="d90a0-226">Weitere Informationen zur Verwendung dieser Notation finden Sie unter [Using cross reference (Verwenden von Querverweisen)](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="d90a0-226">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="d90a0-227">Es gibt zwei Möglichkeiten, die UID zu bestimmen:</span><span class="sxs-lookup"><span data-stu-id="d90a0-227">There are two ways to find the UID:</span></span>

- <span data-ttu-id="d90a0-228">Sehen Sie sich die Quelle für die API-Seite an, die Sie verknüpfen möchten, und finden Sie den Wert „ms.assetid“.</span><span class="sxs-lookup"><span data-stu-id="d90a0-228">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="d90a0-229">Beachten Sie, dass einzelne Überladungswerte in der Quelle nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-229">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="d90a0-230">Verwenden Sie für die Suche nach UIDs folgendes Tool: https://xref.docs.microsoft.com/autocomplete?text=tostring (Ersetzen Sie „tostring“ durch Teile des API-Namens, nach dem Sie suchen).</span><span class="sxs-lookup"><span data-stu-id="d90a0-230">Use the following tool to search for UIDs: https://xref.docs.microsoft.com/autocomplete?text=tostring (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="d90a0-231">Das Tool sucht nach dem angegebenen `text`-Abfrageparameter in jedem Teil der UID.</span><span class="sxs-lookup"><span data-stu-id="d90a0-231">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="d90a0-232">Sie können zum Beispiel nach dem Membernamen (ToString), einem Teil des Membernamens (ToStri) oder dem Typ- und Membernamen (Double.ToString) suchen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-232">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="d90a0-233">Wenn die UID die Sonderzeichen \`, \# und \* enthält, muss der UID-Wert als `%60`, `%23` bzw. `%2A` HTML-codiert werden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-233">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="d90a0-234">In manchen Fällen werden Sie codierte Klammern sehen, dies ist jedoch nicht zwingend erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d90a0-234">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="d90a0-235">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d90a0-235">Examples:</span></span>

- <span data-ttu-id="d90a0-236">System.Threading.Tasks.Task\`1 wird `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="d90a0-236">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="d90a0-237">System.Exception.\#ctor wird `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="d90a0-237">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="d90a0-238">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) wird  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="d90a0-238">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="d90a0-239">Listen</span><span class="sxs-lookup"><span data-stu-id="d90a0-239">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="d90a0-240">Geordnete Liste</span><span class="sxs-lookup"><span data-stu-id="d90a0-240">Ordered lists</span></span>

1. <span data-ttu-id="d90a0-241">Dies</span><span class="sxs-lookup"><span data-stu-id="d90a0-241">This</span></span>
1. <span data-ttu-id="d90a0-242">Ist</span><span class="sxs-lookup"><span data-stu-id="d90a0-242">Is</span></span>
1. <span data-ttu-id="d90a0-243">Eine</span><span class="sxs-lookup"><span data-stu-id="d90a0-243">An</span></span>
1. <span data-ttu-id="d90a0-244">Geordnete</span><span class="sxs-lookup"><span data-stu-id="d90a0-244">Ordered</span></span>
1. <span data-ttu-id="d90a0-245">Liste</span><span class="sxs-lookup"><span data-stu-id="d90a0-245">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="d90a0-246">Geordnete Liste mit einer eingebetteten Liste</span><span class="sxs-lookup"><span data-stu-id="d90a0-246">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="d90a0-247">Hier</span><span class="sxs-lookup"><span data-stu-id="d90a0-247">Here</span></span>
1. <span data-ttu-id="d90a0-248">kommt</span><span class="sxs-lookup"><span data-stu-id="d90a0-248">comes</span></span>
1. <span data-ttu-id="d90a0-249">eine</span><span class="sxs-lookup"><span data-stu-id="d90a0-249">an</span></span>
1. <span data-ttu-id="d90a0-250">eingebettete</span><span class="sxs-lookup"><span data-stu-id="d90a0-250">embedded</span></span>
    1. <span data-ttu-id="d90a0-251">Frau Gloria</span><span class="sxs-lookup"><span data-stu-id="d90a0-251">Miss Scarlett</span></span>
    1. <span data-ttu-id="d90a0-252">Professor Bloom</span><span class="sxs-lookup"><span data-stu-id="d90a0-252">Professor Plum</span></span>
1. <span data-ttu-id="d90a0-253">geordnete</span><span class="sxs-lookup"><span data-stu-id="d90a0-253">ordered</span></span>
1. <span data-ttu-id="d90a0-254">list</span><span class="sxs-lookup"><span data-stu-id="d90a0-254">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="d90a0-255">Ungeordnete Listen</span><span class="sxs-lookup"><span data-stu-id="d90a0-255">Unordered Lists</span></span>

- <span data-ttu-id="d90a0-256">Dieses</span><span class="sxs-lookup"><span data-stu-id="d90a0-256">This</span></span>
- <span data-ttu-id="d90a0-257">ist</span><span class="sxs-lookup"><span data-stu-id="d90a0-257">is</span></span>
- <span data-ttu-id="d90a0-258">eine</span><span class="sxs-lookup"><span data-stu-id="d90a0-258">a</span></span>
- <span data-ttu-id="d90a0-259">Aufzählungs-</span><span class="sxs-lookup"><span data-stu-id="d90a0-259">bulleted</span></span>
- <span data-ttu-id="d90a0-260">Liste</span><span class="sxs-lookup"><span data-stu-id="d90a0-260">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="d90a0-261">Ungeordnete Liste mit einer eingebetteten Liste</span><span class="sxs-lookup"><span data-stu-id="d90a0-261">Unordered list with an embedded list</span></span>

- <span data-ttu-id="d90a0-262">Diese</span><span class="sxs-lookup"><span data-stu-id="d90a0-262">This</span></span>
- <span data-ttu-id="d90a0-263">Aufzählungs-</span><span class="sxs-lookup"><span data-stu-id="d90a0-263">bulleted</span></span>
- <span data-ttu-id="d90a0-264">list</span><span class="sxs-lookup"><span data-stu-id="d90a0-264">list</span></span>
  - <span data-ttu-id="d90a0-265">Baronin von Porz</span><span class="sxs-lookup"><span data-stu-id="d90a0-265">Mrs. Peacock</span></span>
  - <span data-ttu-id="d90a0-266">Reverend Grün</span><span class="sxs-lookup"><span data-stu-id="d90a0-266">Mr. Green</span></span>
- <span data-ttu-id="d90a0-267">enthält</span><span class="sxs-lookup"><span data-stu-id="d90a0-267">contains</span></span>
- <span data-ttu-id="d90a0-268">andere</span><span class="sxs-lookup"><span data-stu-id="d90a0-268">other</span></span>
  1. <span data-ttu-id="d90a0-269">Oberst von Gatow</span><span class="sxs-lookup"><span data-stu-id="d90a0-269">Colonel Mustard</span></span>
  1. <span data-ttu-id="d90a0-270">Frau Weiß</span><span class="sxs-lookup"><span data-stu-id="d90a0-270">Mrs. White</span></span>
- <span data-ttu-id="d90a0-271">Listen</span><span class="sxs-lookup"><span data-stu-id="d90a0-271">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="d90a0-272">Horizontale Regel</span><span class="sxs-lookup"><span data-stu-id="d90a0-272">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="d90a0-273">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d90a0-273">Tables</span></span>

| <span data-ttu-id="d90a0-274">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d90a0-274">Tables</span></span>        | <span data-ttu-id="d90a0-275">Sind</span><span class="sxs-lookup"><span data-stu-id="d90a0-275">Are</span></span>           | <span data-ttu-id="d90a0-276">Toll</span><span class="sxs-lookup"><span data-stu-id="d90a0-276">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="d90a0-277">col 3 ist</span><span class="sxs-lookup"><span data-stu-id="d90a0-277">col 3 is</span></span>      | <span data-ttu-id="d90a0-278">rechtsbündig</span><span class="sxs-lookup"><span data-stu-id="d90a0-278">right-aligned</span></span> | <span data-ttu-id="d90a0-279">$1600</span><span class="sxs-lookup"><span data-stu-id="d90a0-279">$1600</span></span> |
| <span data-ttu-id="d90a0-280">col 2 ist</span><span class="sxs-lookup"><span data-stu-id="d90a0-280">col 2 is</span></span>      | <span data-ttu-id="d90a0-281">zentriert</span><span class="sxs-lookup"><span data-stu-id="d90a0-281">centered</span></span>      |   <span data-ttu-id="d90a0-282">$12</span><span class="sxs-lookup"><span data-stu-id="d90a0-282">$12</span></span> |
| <span data-ttu-id="d90a0-283">col 1 ist der Standard</span><span class="sxs-lookup"><span data-stu-id="d90a0-283">col 1 is default</span></span> | <span data-ttu-id="d90a0-284">linksbündig</span><span class="sxs-lookup"><span data-stu-id="d90a0-284">left-aligned</span></span>     |    <span data-ttu-id="d90a0-285">$1</span><span class="sxs-lookup"><span data-stu-id="d90a0-285">$1</span></span> |

<span data-ttu-id="d90a0-286">Sie können ein [Markdowntool zum Generieren von Tabellen](https://www.tablesgenerator.com/markdown_tables) verwenden, um diese einfacher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-286">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="d90a0-287">Code</span><span class="sxs-lookup"><span data-stu-id="d90a0-287">Code</span></span>

<span data-ttu-id="d90a0-288">Die beste Methode zum Einschließen von Code ist, Codeausschnitte aus einem funktionierenden Beispiel einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-288">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="d90a0-289">Erstellen Sie Ihr Beispiel, indem Sie die Anweisungen im [Leitfaden für Mitwirkende](../CONTRIBUTING.md#contributing-to-samples) befolgen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-289">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="d90a0-290">Sie können den Code mithilfe folgender Syntax einschließen:</span><span class="sxs-lookup"><span data-stu-id="d90a0-290">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="d90a0-291">`-<language>` (*optional*, aber *empfohlen*)</span><span class="sxs-lookup"><span data-stu-id="d90a0-291">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="d90a0-292">Programmiersprache des Codeausschnitts, auf den verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d90a0-292">Language of the code snippet being referenced.</span></span> <span data-ttu-id="d90a0-293">Eine Liste mit unterstützten Werten finden Sie unter [Unterstützte Sprachen](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="d90a0-293">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="d90a0-294">`<name>` (*optional*)</span><span class="sxs-lookup"><span data-stu-id="d90a0-294">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="d90a0-295">Name für den Codeausschnitt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-295">Name for the code snippet.</span></span> <span data-ttu-id="d90a0-296">Dieser hat keinen Einfluss auf die HTML-Ausgabe, aber er ermöglicht eine bessere Lesbarkeit Ihrer Markdownquelle.</span><span class="sxs-lookup"><span data-stu-id="d90a0-296">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="d90a0-297">`<pathToFile>` (*erforderlich*)</span><span class="sxs-lookup"><span data-stu-id="d90a0-297">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="d90a0-298">Der relative Pfad im Dateisystem, der die Codeausschnittdatei angibt, auf die verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d90a0-298">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="d90a0-299">`<queryoption>` und `<queryoptionvalue>` (*optional*)</span><span class="sxs-lookup"><span data-stu-id="d90a0-299">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="d90a0-300">Zusammen verwendet, um festzulegen, wie der Code aus der Datei abgerufen werden soll:</span><span class="sxs-lookup"><span data-stu-id="d90a0-300">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="d90a0-301">`#`:  `#L{startlinenumber}-L{endlinenumber}` (Zeilenbereich) *oder* `#{tagname}` (Tagname).</span><span class="sxs-lookup"><span data-stu-id="d90a0-301">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="d90a0-302">Von der Verwendung von Zeilennummern wird abgeraten, da diese sehr anfällig sind.</span><span class="sxs-lookup"><span data-stu-id="d90a0-302">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="d90a0-303">Der Tagname ist die bevorzugte Methode zum Verweisen auf Codeausschnitte.</span><span class="sxs-lookup"><span data-stu-id="d90a0-303">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="d90a0-304">`range`: `?range=1,3-5` Ein Bereich von Zeilen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-304">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="d90a0-305">Dieses Beispiel umfasst die Zeilen 1, 3, 4 und 5.</span><span class="sxs-lookup"><span data-stu-id="d90a0-305">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="d90a0-306">`dedent`: `?dedent=8` Rückt die Zeilen um eine Anzahl von Leerzeichen ein – in diesem Fall 8.</span><span class="sxs-lookup"><span data-stu-id="d90a0-306">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="d90a0-307">Diese Methode kann mit `range` und anderen Abfrageoptionen kombiniert werden, die eine Teilmenge der Zeilen einer Datei auswählen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-307">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="d90a0-308">`outdent`: `?outdent=8` Kehrt den Einzug der Zeilen um eine Anzahl von Leerzeichen um – in diesem Fall 8.</span><span class="sxs-lookup"><span data-stu-id="d90a0-308">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="d90a0-309">Diese Methode kann mit `range` und anderen Abfrageoptionen kombiniert werden, die eine Teilmenge der Zeilen einer Datei auswählen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-309">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="d90a0-310">Es wird empfohlen, nach Möglichkeit die Option „Tagname“ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-310">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="d90a0-311">Der Tagname ist der Name eines Bereichs oder eines Codekommentars im Format von `Snippettagname`, der im Quellcode vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d90a0-311">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="d90a0-312">Im folgenden Beispiel wird gezeigt, wie auf den Tagnamen `1` verwiesen wird:</span><span class="sxs-lookup"><span data-stu-id="d90a0-312">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="d90a0-313">Außerdem können Sie sehen, wie die Codeausschnitttags in [dieser Quelldatei](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs) strukturiert sind.</span><span class="sxs-lookup"><span data-stu-id="d90a0-313">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="d90a0-314">Weitere Informationen zur Darstellung von Tagnamen in Codeausschnitten von Quelldateien nach Programmiersprache finden Sie in den [DocFX-Richtlinien](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="d90a0-314">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="d90a0-315">Durch das Einschließen von Ausschnitten aus vollen Programmen wird sichergestellt, dass der gesamte Code durch unser Continuous Integration-System (CI) läuft.</span><span class="sxs-lookup"><span data-stu-id="d90a0-315">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="d90a0-316">Wenn Sie jedoch etwas zeigen müssen, das Kompilierzeit- oder Laufzeitfehler verursacht, können Sie Inlinecodeblöcke verwenden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-316">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="d90a0-317">Inlinecodeblöcke mit Sprachen-ID</span><span class="sxs-lookup"><span data-stu-id="d90a0-317">Inline code blocks with language identifier</span></span>

<span data-ttu-id="d90a0-318">Verwenden Sie drei Graviszeichen (\`\`\`) + eine Sprachen-ID, um die sprachenspezifische Farbcodierung für einen Codeblock anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-318">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="d90a0-319">Im Folgenden finden Sie eine Liste der unterstützten Programmiersprachen, die die Markdownbezeichnung für jede Sprachen-ID anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-319">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="d90a0-320">Unterstützte Sprachen</span><span class="sxs-lookup"><span data-stu-id="d90a0-320">Supported languages</span></span>

|<span data-ttu-id="d90a0-321">NAME</span><span class="sxs-lookup"><span data-stu-id="d90a0-321">Name</span></span>|<span data-ttu-id="d90a0-322">Markdownbezeichnung</span><span class="sxs-lookup"><span data-stu-id="d90a0-322">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="d90a0-323">.NET-Konsole</span><span class="sxs-lookup"><span data-stu-id="d90a0-323">.NET Console</span></span>|<span data-ttu-id="d90a0-324">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="d90a0-324">dotnetcli</span></span>|
|<span data-ttu-id="d90a0-325">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="d90a0-325">ASP.NET (C#)</span></span>|<span data-ttu-id="d90a0-326">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="d90a0-326">aspx-csharp</span></span>|
|<span data-ttu-id="d90a0-327">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="d90a0-327">ASP.NET (VB)</span></span>|<span data-ttu-id="d90a0-328">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="d90a0-328">aspx-vb</span></span>|
|<span data-ttu-id="d90a0-329">Azure-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="d90a0-329">Azure CLI</span></span>|<span data-ttu-id="d90a0-330">azurecli</span><span class="sxs-lookup"><span data-stu-id="d90a0-330">azurecli</span></span>|
|<span data-ttu-id="d90a0-331">AzCopy</span><span class="sxs-lookup"><span data-stu-id="d90a0-331">AzCopy</span></span>|<span data-ttu-id="d90a0-332">azcopy</span><span class="sxs-lookup"><span data-stu-id="d90a0-332">azcopy</span></span>|
|<span data-ttu-id="d90a0-333">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90a0-333">Azure PowerShell</span></span>|<span data-ttu-id="d90a0-334">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="d90a0-334">azurepowershell</span></span>|
|<span data-ttu-id="d90a0-335">Bash</span><span class="sxs-lookup"><span data-stu-id="d90a0-335">Bash</span></span>|<span data-ttu-id="d90a0-336">Bash</span><span class="sxs-lookup"><span data-stu-id="d90a0-336">bash</span></span>|
|<span data-ttu-id="d90a0-337">C++</span><span class="sxs-lookup"><span data-stu-id="d90a0-337">C++</span></span>|<span data-ttu-id="d90a0-338">cpp</span><span class="sxs-lookup"><span data-stu-id="d90a0-338">cpp</span></span>|
|<span data-ttu-id="d90a0-339">C++/CX</span><span class="sxs-lookup"><span data-stu-id="d90a0-339">C++/CX</span></span>|<span data-ttu-id="d90a0-340">cppcx</span><span class="sxs-lookup"><span data-stu-id="d90a0-340">cppcx</span></span>|
|<span data-ttu-id="d90a0-341">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="d90a0-341">C++/WinRT</span></span>|<span data-ttu-id="d90a0-342">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="d90a0-342">cppwinrt</span></span>|
|<span data-ttu-id="d90a0-343">C#</span><span class="sxs-lookup"><span data-stu-id="d90a0-343">C#</span></span>|<span data-ttu-id="d90a0-344">csharp</span><span class="sxs-lookup"><span data-stu-id="d90a0-344">csharp</span></span>|
|<span data-ttu-id="d90a0-345">C# im Browser</span><span class="sxs-lookup"><span data-stu-id="d90a0-345">C# in browser</span></span>|<span data-ttu-id="d90a0-346">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="d90a0-346">csharp-interactive</span></span>|
|<span data-ttu-id="d90a0-347">Konsole</span><span class="sxs-lookup"><span data-stu-id="d90a0-347">Console</span></span>|<span data-ttu-id="d90a0-348">console</span><span class="sxs-lookup"><span data-stu-id="d90a0-348">console</span></span>|
|<span data-ttu-id="d90a0-349">CSHTML</span><span class="sxs-lookup"><span data-stu-id="d90a0-349">CSHTML</span></span>|<span data-ttu-id="d90a0-350">cshtml</span><span class="sxs-lookup"><span data-stu-id="d90a0-350">cshtml</span></span>|
|<span data-ttu-id="d90a0-351">DAX</span><span class="sxs-lookup"><span data-stu-id="d90a0-351">DAX</span></span>|<span data-ttu-id="d90a0-352">dax</span><span class="sxs-lookup"><span data-stu-id="d90a0-352">dax</span></span>|
|<span data-ttu-id="d90a0-353">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="d90a0-353">Dockerfile</span></span>|<span data-ttu-id="d90a0-354">dockerfile</span><span class="sxs-lookup"><span data-stu-id="d90a0-354">dockerfile</span></span>|
|<span data-ttu-id="d90a0-355">F#</span><span class="sxs-lookup"><span data-stu-id="d90a0-355">F#</span></span>|<span data-ttu-id="d90a0-356">fsharp</span><span class="sxs-lookup"><span data-stu-id="d90a0-356">fsharp</span></span>|
|<span data-ttu-id="d90a0-357">Go</span><span class="sxs-lookup"><span data-stu-id="d90a0-357">Go</span></span>|<span data-ttu-id="d90a0-358">go</span><span class="sxs-lookup"><span data-stu-id="d90a0-358">go</span></span>|
|<span data-ttu-id="d90a0-359">HTML</span><span class="sxs-lookup"><span data-stu-id="d90a0-359">HTML</span></span>|<span data-ttu-id="d90a0-360">html</span><span class="sxs-lookup"><span data-stu-id="d90a0-360">html</span></span>|
|<span data-ttu-id="d90a0-361">HTTP</span><span class="sxs-lookup"><span data-stu-id="d90a0-361">HTTP</span></span>|<span data-ttu-id="d90a0-362">http</span><span class="sxs-lookup"><span data-stu-id="d90a0-362">http</span></span>|
|<span data-ttu-id="d90a0-363">Java</span><span class="sxs-lookup"><span data-stu-id="d90a0-363">Java</span></span>|<span data-ttu-id="d90a0-364">java</span><span class="sxs-lookup"><span data-stu-id="d90a0-364">java</span></span>|
|<span data-ttu-id="d90a0-365">JavaScript</span><span class="sxs-lookup"><span data-stu-id="d90a0-365">JavaScript</span></span>|<span data-ttu-id="d90a0-366">javascript</span><span class="sxs-lookup"><span data-stu-id="d90a0-366">javascript</span></span>|
|<span data-ttu-id="d90a0-367">JSON</span><span class="sxs-lookup"><span data-stu-id="d90a0-367">JSON</span></span>|<span data-ttu-id="d90a0-368">json</span><span class="sxs-lookup"><span data-stu-id="d90a0-368">json</span></span>|
|<span data-ttu-id="d90a0-369">Kusto-Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d90a0-369">Kusto Query Language</span></span>|<span data-ttu-id="d90a0-370">kusto</span><span class="sxs-lookup"><span data-stu-id="d90a0-370">kusto</span></span>|
|<span data-ttu-id="d90a0-371">Markdown</span><span class="sxs-lookup"><span data-stu-id="d90a0-371">Markdown</span></span>|<span data-ttu-id="d90a0-372">md</span><span class="sxs-lookup"><span data-stu-id="d90a0-372">md</span></span>|
|<span data-ttu-id="d90a0-373">NodeJS</span><span class="sxs-lookup"><span data-stu-id="d90a0-373">NodeJS</span></span>|<span data-ttu-id="d90a0-374">nodejs</span><span class="sxs-lookup"><span data-stu-id="d90a0-374">nodejs</span></span>|
|<span data-ttu-id="d90a0-375">Objective-C</span><span class="sxs-lookup"><span data-stu-id="d90a0-375">Objective-C</span></span>|<span data-ttu-id="d90a0-376">objc</span><span class="sxs-lookup"><span data-stu-id="d90a0-376">objc</span></span>|
|<span data-ttu-id="d90a0-377">OData</span><span class="sxs-lookup"><span data-stu-id="d90a0-377">OData</span></span>|<span data-ttu-id="d90a0-378">odata</span><span class="sxs-lookup"><span data-stu-id="d90a0-378">odata</span></span>|
|<span data-ttu-id="d90a0-379">PHP</span><span class="sxs-lookup"><span data-stu-id="d90a0-379">PHP</span></span>|<span data-ttu-id="d90a0-380">php</span><span class="sxs-lookup"><span data-stu-id="d90a0-380">php</span></span>|
|<span data-ttu-id="d90a0-381">PowerApps (Dezimaltrennzeichen: Punkt)</span><span class="sxs-lookup"><span data-stu-id="d90a0-381">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="d90a0-382">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="d90a0-382">powerapps-dot</span></span>|
|<span data-ttu-id="d90a0-383">PowerApps (Dezimaltrennzeichen: Komma)</span><span class="sxs-lookup"><span data-stu-id="d90a0-383">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="d90a0-384">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="d90a0-384">powerapps-comma</span></span>|
|<span data-ttu-id="d90a0-385">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90a0-385">PowerShell</span></span>|<span data-ttu-id="d90a0-386">powershell</span><span class="sxs-lookup"><span data-stu-id="d90a0-386">powershell</span></span>|
|<span data-ttu-id="d90a0-387">Python</span><span class="sxs-lookup"><span data-stu-id="d90a0-387">Python</span></span>|<span data-ttu-id="d90a0-388">Python</span><span class="sxs-lookup"><span data-stu-id="d90a0-388">python</span></span>|
|<span data-ttu-id="d90a0-389">Q#</span><span class="sxs-lookup"><span data-stu-id="d90a0-389">Q#</span></span>|<span data-ttu-id="d90a0-390">qsharp</span><span class="sxs-lookup"><span data-stu-id="d90a0-390">qsharp</span></span>|
|<span data-ttu-id="d90a0-391">R</span><span class="sxs-lookup"><span data-stu-id="d90a0-391">R</span></span>|<span data-ttu-id="d90a0-392">r</span><span class="sxs-lookup"><span data-stu-id="d90a0-392">r</span></span>|
|<span data-ttu-id="d90a0-393">Ruby</span><span class="sxs-lookup"><span data-stu-id="d90a0-393">Ruby</span></span>|<span data-ttu-id="d90a0-394">ruby</span><span class="sxs-lookup"><span data-stu-id="d90a0-394">ruby</span></span>|
|<span data-ttu-id="d90a0-395">SQL</span><span class="sxs-lookup"><span data-stu-id="d90a0-395">SQL</span></span>|<span data-ttu-id="d90a0-396">sql</span><span class="sxs-lookup"><span data-stu-id="d90a0-396">sql</span></span>|
|<span data-ttu-id="d90a0-397">Swift</span><span class="sxs-lookup"><span data-stu-id="d90a0-397">Swift</span></span>|<span data-ttu-id="d90a0-398">swift</span><span class="sxs-lookup"><span data-stu-id="d90a0-398">swift</span></span>|
|<span data-ttu-id="d90a0-399">TypeScript</span><span class="sxs-lookup"><span data-stu-id="d90a0-399">TypeScript</span></span>|<span data-ttu-id="d90a0-400">typescript</span><span class="sxs-lookup"><span data-stu-id="d90a0-400">typescript</span></span>|
|<span data-ttu-id="d90a0-401">VB</span><span class="sxs-lookup"><span data-stu-id="d90a0-401">VB</span></span>|<span data-ttu-id="d90a0-402">vb</span><span class="sxs-lookup"><span data-stu-id="d90a0-402">vb</span></span>|
|<span data-ttu-id="d90a0-403">XAML</span><span class="sxs-lookup"><span data-stu-id="d90a0-403">XAML</span></span>|<span data-ttu-id="d90a0-404">xaml</span><span class="sxs-lookup"><span data-stu-id="d90a0-404">xaml</span></span>|
|<span data-ttu-id="d90a0-405">XML</span><span class="sxs-lookup"><span data-stu-id="d90a0-405">XML</span></span>|<span data-ttu-id="d90a0-406">Xml</span><span class="sxs-lookup"><span data-stu-id="d90a0-406">xml</span></span>|

<span data-ttu-id="d90a0-407">Der Name `csharp-interactive` gibt die C#-Programmiersprache und die Möglichkeit an, die Beispiele über den Browser auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-407">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="d90a0-408">Diese Codeausschnitte werden in einem Docker-Container kompiliert und ausgeführt, und die Ergebnisse dieser Programmausführung werden im Browserfenster des Benutzers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d90a0-408">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="d90a0-409">Im Folgenden finden Sie Beispiele für Codeblöcke mit den Sprach-IDs für C# (\`\`\`csharp), Python (\`\`\`python) und PowerShell (\`\`\`powershell).</span><span class="sxs-lookup"><span data-stu-id="d90a0-409">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c9839"></a><span data-ttu-id="d90a0-410">C&#9839;</span><span class="sxs-lookup"><span data-stu-id="d90a0-410">C&#9839;</span></span>

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a><span data-ttu-id="d90a0-411">Python</span><span class="sxs-lookup"><span data-stu-id="d90a0-411">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="d90a0-412">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d90a0-412">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="d90a0-413">Generischer Codeblock</span><span class="sxs-lookup"><span data-stu-id="d90a0-413">Generic code block</span></span>

<span data-ttu-id="d90a0-414">Verwenden Sie drei Graviszeichen (&#96;&#96;&#96;) für die Codierung mit generischem Codeblock.</span><span class="sxs-lookup"><span data-stu-id="d90a0-414">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="d90a0-415">Die empfohlene Vorgehensweise ist, Codeblöcke mit Sprachen-IDs wie im vorherigen Abschnitt beschrieben zu verwenden, um sicherzustellen, dass auf der Dokumentationsseite die richtige Syntax hervorgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="d90a0-415">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="d90a0-416">Verwenden Sie generische Codeblöcke nur bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="d90a0-416">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="d90a0-417">Blockquotes</span><span class="sxs-lookup"><span data-stu-id="d90a0-417">Blockquotes</span></span>

> <span data-ttu-id="d90a0-418">Die Dürre hatte schon zehn Millionen Jahre angehalten, und die Herrschaft der Schrecklichen Saurier war lange vorbei.</span><span class="sxs-lookup"><span data-stu-id="d90a0-418">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="d90a0-419">Hier am Äquator, auf dem Kontinent, der eines Tages Afrika heißen würde, hatte der Existenzkampf ein neues Stadium von Grausamkeit erreicht und ein Gewinner war noch nicht abzusehen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-419">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="d90a0-420">In diesem ausgetrockneten, ausgedörrten Land konnte nur der Kleinste oder der Schnellste oder der Zäheste gedeihen oder zu überleben hoffen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-420">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="d90a0-421">Bilder</span><span class="sxs-lookup"><span data-stu-id="d90a0-421">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="d90a0-422">Statisches Bild oder animiertes GIF</span><span class="sxs-lookup"><span data-stu-id="d90a0-422">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![Dies ist der Alternativtext](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="d90a0-424">Verlinktes Bild</span><span class="sxs-lookup"><span data-stu-id="d90a0-424">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="d90a0-425">[![Alternativtext für verlinktes Bild](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="d90a0-425">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="d90a0-426">Videos</span><span class="sxs-lookup"><span data-stu-id="d90a0-426">Videos</span></span>

<span data-ttu-id="d90a0-427">Derzeit können Sie sowohl Channel 9- als auch YouTube-Videos mit der folgenden Syntax einbetten:</span><span class="sxs-lookup"><span data-stu-id="d90a0-427">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="d90a0-428">Channel 9</span><span class="sxs-lookup"><span data-stu-id="d90a0-428">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="d90a0-429">Um die korrekte URL des Videos zu ermitteln, wählen Sie die Registerkarte **Einbetten** unterhalb des Videoframes aus, und kopieren Sie die URL aus dem `<iframe>`-Element.</span><span class="sxs-lookup"><span data-stu-id="d90a0-429">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="d90a0-430">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d90a0-430">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="d90a0-431">YouTube</span><span class="sxs-lookup"><span data-stu-id="d90a0-431">YouTube</span></span>

<span data-ttu-id="d90a0-432">Um die korrekte URL des Videos zu ermitteln, klicken Sie mit der rechten Maustaste auf das Video, wählen **Einbindungscode kopieren**  und kopieren die URL aus dem `<iframe>`-Element.</span><span class="sxs-lookup"><span data-stu-id="d90a0-432">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="d90a0-433">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d90a0-433">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="d90a0-434">docs.microsoft-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="d90a0-434">docs.microsoft extensions</span></span>

<span data-ttu-id="d90a0-435">docs.microsoft bietet einige zusätzliche Erweiterungen zu GitHub Flavored Markdown.</span><span class="sxs-lookup"><span data-stu-id="d90a0-435">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="d90a0-436">Alerts</span><span class="sxs-lookup"><span data-stu-id="d90a0-436">Alerts</span></span>

<span data-ttu-id="d90a0-437">Es ist wichtig, die folgenden Warnstile zu verwenden, damit diese im richtigen Stil auf der Dokumentationsseite gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-437">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="d90a0-438">Die Rendering-Engine auf GitHub unterscheidet diese jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="d90a0-438">However, the rendering engine on GitHub doesn't diferentiate them.</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="d90a0-439">Und sie werden wie folgt gerendert: ![Warnstile](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="d90a0-439">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="d90a0-440">Umfang</span><span class="sxs-lookup"><span data-stu-id="d90a0-440">Includes</span></span>

<span data-ttu-id="d90a0-441">Sie können den Markdownteil einer Datei über eine Includeanweisung in eine andere einbetten.</span><span class="sxs-lookup"><span data-stu-id="d90a0-441">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="d90a0-442">Häkchenlisten</span><span class="sxs-lookup"><span data-stu-id="d90a0-442">Checked lists</span></span>

<span data-ttu-id="d90a0-443">Für Listen ist eine benutzerdefinierte Formatvorlage vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d90a0-443">A custom style is available for lists.</span></span> <span data-ttu-id="d90a0-444">Sie können Listen mit grünen Häkchen darstellen.</span><span class="sxs-lookup"><span data-stu-id="d90a0-444">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="d90a0-445">Erstellen einer .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="d90a0-445">How to create a .NET Core app</span></span>
> - <span data-ttu-id="d90a0-446">Hinzufügen eines Verweises zum Microsoft.XmlSerializer.Generator-Paket</span><span class="sxs-lookup"><span data-stu-id="d90a0-446">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="d90a0-447">Bearbeiten Ihrer MyApp.csproj-Datei zum Hinzufügen von Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="d90a0-447">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="d90a0-448">Hinzufügen von „XmlSerializer“ und einer Klasse</span><span class="sxs-lookup"><span data-stu-id="d90a0-448">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="d90a0-449">Erstellen und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="d90a0-449">How to build and run the application</span></span>

<span data-ttu-id="d90a0-450">Ein Beispiel für eine Häkchenliste in Aktion finden Sie in diesem [.NET Core-Dokument](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="d90a0-450">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="d90a0-451">Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="d90a0-451">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="d90a0-452">Schaltflächenlinks</span><span class="sxs-lookup"><span data-stu-id="d90a0-452">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="d90a0-453">Ein Beispiel für Schaltflächen in Aktion finden Sie in der [Visual Studio-Dokumentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d90a0-453">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="d90a0-454">Selektoren</span><span class="sxs-lookup"><span data-stu-id="d90a0-454">Selectors</span></span>

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="d90a0-457">Ein Beispiel für Selektoren in Aktion finden Sie in der [Azure-Dokumentation](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="d90a0-457">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="d90a0-458">Schritt-für-Schritt-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d90a0-458">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d90a0-459">[Zurück](../docs/csharp/expression-trees-interpreting.md)
>[Weiter](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="d90a0-459">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="d90a0-460">Ein Beispiel für Schritt-für-Schritt-Funktionen in Aktion finden Sie in der [C#-Dokumentation](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="d90a0-460">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
