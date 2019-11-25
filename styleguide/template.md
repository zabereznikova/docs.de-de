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
ms.openlocfilehash: ed9fd55fd84606d2083e0576581391331769a1e6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089281"
---
# <a name="metadata-and-markdown-template"></a>Metadaten und Markdownvorlage

Diese dotnet/docs-Vorlage enthält Beispiele der Markdownsyntax sowie einen Leitfaden zum Festlegen der Metadaten. Sie müssen sowohl das [unformatierte Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) als auch die [gerenderte Ansicht](https://github.com/dotnet/docs/blob/master/styleguide/template.md) anzeigen, um die Vorlage bestmöglich zu nutzen.

Beim Erstellen einer Markdowndatei sollten Sie diese Vorlage in eine neue Datei kopieren, die Metadaten wie nachstehend angegeben ausfüllen, den H1-Header oben als Titel des Artikels festlegen und den Inhalt löschen.

## <a name="metadata"></a>Metadaten

Der vollständige Metadatenblock befindet sich oben (im [unformatierten Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), unterteilt in erforderliche Felder und optionale Felder. Wichtige Hinweise:

- Bei einem Metadatenelement **muss** ein Leerzeichen zwischen dem Doppelpunkt (:) und dem Wert stehen.
- Wenn ein optionales Metadatenelement keinen Wert hat, kommentieren Sie das Element mit einem #-Zeichen aus, oder entfernen Sie es. (Lassen Sie es nicht leer und verwenden Sie kein „k.A.“.) Wenn Sie einen Wert zu einem auskommentierten Element hinzufügen, müssen Sie das #-Zeichen entfernen.
- Doppelpunkte in einem Wert (z.B. einem Titel) unterbrechen den Metadatenparser. In diesem Fall setzen Sie den Titel in doppelte Anführungszeichen (z.B. `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **title**: Wird in Suchmaschinenergebnissen angezeigt. Der Titel darf nicht mit dem Titel in Ihrem H1-Header übereinstimmen, und er sollte höchstens 60 Zeichen umfassen.
- **description**: Bietet eine Zusammenfassung des Artikelinhalts. Diese wird normalerweise auf der Seite mit den Suchergebnissen angezeigt, hat auf den Rang in den Suchergebnissen jedoch keine Auswirkungen. Die Länge sollte 115-145 Zeichen (einschließlich Leerzeichen) betragen.
- **author** und **ms.author**: Das Feld „author“ sollte den **GitHub-Benutzernamen** des Autors enthalten, nicht dessen Alias.  Das Feld **ms.author** hingegen sollte einen Microsoft-Alias enthalten und die für die Verwaltung des Artikels verantwortliche Person angeben.
- **ms.topic**: Der Thementyp. Der häufigste Wert ist `conceptual` und wird auf globaler Ebene festgelegt. Andere gängige Werte sind `tutorial`, `overview` und `reference`.
- **dev_langs** definiert den für das Thema angezeigten Sprachfilter. Eine Liste der unterstützten Werte finden Sie im Abschnitt [Unterstützte Sprachen](#supported-languages). Dieser Wert muss nur festgelegt werden, wenn mehr als eine Programmiersprache im Thema abgedeckt wird. In der Regel verwenden wir in unserem Inhalt nur `csharp`, `vb`, `fsharp` und `cpp` für diesen Wert.
- **ms.prod**: Die für BI-Zwecke verwendete Produktidentifizierung. Sie werden normalerweise auf globaler Ebene festgelegt und daher für gewöhnlich nicht im Metadatenblock jedes Artikels angezeigt.
- **ms.technology**: Zusätzliche BI-Klassifizierung. Dies sind einige der unterstützten Werte: `devlang-csharp` für C#-Themen, `devlang-fsharp` für F#-Themen und `devlang-visual-basic` für VB-Themen. Da bei anderen Leitfäden die Werte variieren, wenden Sie sich bitte an ein Teammitglied.
- **ms.date**: Ein Datum im Format MM/TT/JJJJ. Wird auf der veröffentlichten Seite angezeigt und gibt das Datum der letzten wesentlichen Bearbeitung des Artikels an bzw. garantiert dessen Aktualität (d.h. der Artikel wurde überprüft und als aktuell eingestuft).
- **helpviewer_keywords**: Einträge werden für den Index der Offlinebücher verwendet (Funktionalität in Visual Studio).
- **f1_keywords**: Verbindet den Artikel mit der F1-Taste (Funktionalität in Visual Studio).

## <a name="basic-markdown-gfm-and-special-characters"></a>Grundlegendes Markdown, GFM und Sonderzeichen

Alles grundlegende Markdown sowie GitHub Flavored Markdown (GFM) wird unterstützt. Weitere Informationen dazu finden Sie auf den folgenden Seiten:

- [Grundlegende Markdownsyntax](https://daringfireball.net/projects/markdown/syntax)
- [GFM-Dokumentation](https://guides.github.com/features/mastering-markdown)

Markdown verwendet Sonderzeichen wie z.B. \*, \`, und \# für die Formatierung. Wenn Sie eines dieser Zeichen in Ihren Inhalt einschließen möchten, müssen Sie einen der folgenden Schritte ausführen:

- Setzen Sie einen umgekehrten Schrägstrich vor das Sonderzeichen, um es mit einem Escapezeichen zu versehen (z. B. `\*` für \*)
- Verwenden Sie den [HTML-Entitätscode](https://www.ascii.cl/htmlcodes.htm) für das Zeichen (z. B. `&#42;` für ein &#42;).

## <a name="file-name"></a>Dateiname

Dateinamen verwenden die folgenden Regeln:

- Es sollten nur Kleinbuchstaben, Zahlen und Bindestriche enthalten sein.
- Keine Leer- oder Interpunktionszeichen. Verwenden Sie die Bindestriche zum Trennen von Wörtern und Zahlen im Dateinamen.
- Verwenden Sie genaue Aktionsverben wie „entwickeln“, „kaufen“, „erstellen“ oder „beheben“. Keine auf „-ing“ endenden Worte dürfen verwendet werden.
- Keine kurzen Worte wie a, and, the, in, or usw. sind erlaubt.
- Muss in Markdown geschrieben werden und die Dateierweiterung .md verwenden.
- Halten Sie Dateinamen einigermaßen kurz. Sie sind Teil der URL für Ihre Artikel.

## <a name="headings"></a>Kopfzeilen

Verwenden Sie die übliche Groß-/Kleinschreibung. Schreiben Sie den ersten Buchstaben des ersten Worts einer Überschrift, Eigennamen und den ersten Buchstaben nach einem Doppelpunkt groß (z. B. „Tutorial: Vorhersagen von Preisen per Regression mit ML.NET“).

Verwenden Sie bei der Beschreibung von Vorgehensweisen keinen Doppelpunkt (z. B. „Sortieren eines Arrays“ und nicht „Vorgehensweise: Sortieren eines Arrays“).

Überschriften sollten mithilfe des atx-Stils erstellt werden, d.h. es sollten 1-6 Hash-Zeichen (#) am Anfang der Zeile verwendet werden, um eine Überschrift anzugeben, entsprechend der HTML-Überschriftenebenen H1 bis H6. Beispiele für Header der ersten und zweiten Ebene werden oben verwendet.

In Ihrem Thema **darf** nur eine Überschrift der ersten Ebene (H1) enthalten sein, die als Titel auf der Seite angezeigt wird.

Wenn die Überschrift mit einem `#`-Zeichen endet, müssen Sie sie mit Escapezeichen versehen, damit der Titel richtig dargestellt wird. Beispielsweise `# Async programming in F\#`.

Überschriften der zweiten Ebene generieren das Inhaltsverzeichnis auf der Seite, das im Abschnitt „In diesem Artikel“ unterhalb des Titels auf der Seite angezeigt wird.

### <a name="third-level-heading"></a>Überschrift der dritten Ebene
#### <a name="fourth-level-heading"></a>Überschrift der vierten Ebene
##### <a name="fifth-level-heading"></a>Überschrift der fünften Ebene
###### <a name="sixth-level-heading"></a>Überschrift der sechsten Ebene

## <a name="text-styling"></a>Textstil

*Kursiv*: wird für Dateien, Ordner, Pfade (lange Pfade sollten in einer eigenen Zeile stehen), neue Begriffe verwendet.

**Fett** wird für Benutzeroberflächenelemente verwendet.

`Code`: wird für Inline-Code, Sprachschlüsselwörter, NuGet-Paketnamen, Befehlszeilenbefehle, Datenbanktabellen und Spaltennamen sowie URLs verwendet, die nicht klickbar sein müssen.

## <a name="links"></a>Links

### <a name="internal-links"></a>Interne Links

Um auf einen Header in der gleichen Markdowndatei zu verlinken (auch als Ankerlinks bekannt), müssen Sie die ID des Headers ermitteln, auf den Sie verlinken möchten. Um die ID zu bestätigen, zeigen Sie die Quelle des gerenderten Artikels an, suchen Sie nach der ID des Headers (z.B. `id="blockquote"`), und erstellen Sie den Link mithilfe von # + ID (z.B. `#blockquote`).
Die ID wird basierend auf dem Headertext automatisch generiert. Wenn also beispielsweise ein eindeutiger Abschnitt `## Step 2` genannt wird, sieht die ID folgendermaßen aus: `id="step-2"`.

- Beispiel: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` erzeugt [Deklarieren von Inlineblöcken mit einem Sprachbezeichner](#inline-code-blocks-with-language-identifier).

Um auf eine Markdowndatei im gleichen Repository zu verlinken, verwenden Sie [relative Links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), einschließlich „.md“ am Ende des Dateinamens.

- Beispiel: `[Readme file](../README.md)` erzeugt [Infodatei](../README.md). (Beachten Sie, dass bei Links die Groß-/Kleinschreibung beachtet wird.)
- Beispiel: `[Welcome to .NET](../docs/welcome.md)` erzeugt [Willkommen bei .NET](../docs/welcome.md).

Um auf einen Header in einer Markdowndatei im gleichen Repository zu verlinken, verwenden Sie die relative Verlinkung + die Hashtag-Verlinkung.

- Beispiel: `[.NET Community](../docs/welcome.md#open-source)` erzeugt [.NET-Community](../docs/welcome.md#open-source).

In den meisten Fällen verwenden wir die relativen Links und raten von der Verwendung von `~/` in Links ab, da sich relative Links in der Quelle auf GitHub auflösen. Wenn wir jedoch auf eine Datei in einem abhängigen Repository verweisen, verwenden wir das Zeichen `~/`, um den Pfad anzugeben. Da sich die Dateien im abhängigen Repository an einem anderen Ort in GitHub befinden, werden die Links nicht ordnungsgemäß mit relativen Links aufgelöst, unabhängig davon, wie sie geschrieben wurden.

Die C#-Sprachspezifikation und die Visual Basic-Sprachspezifikation sind in den .NET-Dokumenten enthalten, da die Quelle aus den Sprachrepositorys einbezogen wird. Die Markdownquellen werden in den Repositorys [csharplang](https://github.com/dotnet/csharplang) und [visual basic](https://github.com/dotnet/vblang) verwaltet.

Links zur Spezifikation müssen auf die Quellverzeichnisse verweisen, in denen diese Spezifikationen enthalten sind. Für C# ist dies **~/_csharplang/spec** und für VB ist dies **~/_vblang/spec**.

- Beispiel: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` erzeugt [C#-Abfrageausdrücke](~/_csharplang/spec/expressions.md#query-expressions).

### <a name="external-links"></a>Externe Links

Um auf eine externe Datei zu verlinken, verwenden Sie als Link die vollständige URL.

- Beispiel: `[GitHub](https://www.github.com)` erzeugt [GitHub](https://www.github.com).

Wenn in einer Markdowndatei eine URL erscheint, wird diese in einen klickbaren Link verwandelt.

- Beispiel: `<https://www.github.com>` erzeugt <https://www.github.com>.

Bevorzugen Sie für externe Links das `https`-Protokoll. Verwenden Sie `http`-Links nur für Websites, die `https` nicht unterstützen.

### <a name="links-to-apis"></a>Links zu APIs

Das Buildsystem verfügt über einige Erweiterungen, die es ermöglichen, auf .NET-APIs zu verlinken, ohne externe Links verwenden zu müssen.
Wenn auf eine API verlinkt wird, können Sie deren eindeutigen Bezeichner (UID) verwenden, der automatisch aus dem Quellcode generiert wird.

Die UID entspricht dem vollqualifizierten Typ und Membernamen.

Wenn Sie ein \* (oder %2A) nach der UID hinzufügen, stellt der Link dann die Überladungsseite und nicht eine bestimmte API dar. Dies können Sie beispielsweise verwenden, wenn Sie generisch auf die Seite [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) anstelle einer bestimmten Überladung wie [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_) verweisen möchten. Sie können auch \* verwenden, um einen Link zu einer Memberseite zu erstellen, wenn das Member nicht überladen ist; so müssen Sie die Parameterliste nicht in die UID einschließen.

Wenn Sie einen Link zu einer bestimmten Methodenüberladung erstellen möchten, müssen Sie den vollqualifizierten Typnamen jedes einzelnen Parameters der Methode angeben. \<xref:System.DateTime.ToString> ist beispielsweise mit der parameterlosen Methode [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) verknüpft, während \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> mit der Methode  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) verknüpft ist. Sie können die UIDs eines bestimmten überladenen Members auf <https://xref.docs.microsoft.com/autocomplete> finden. Die Abfragezeichenfolge „?text= *\<Typmembername>* “ identifiziert den Typ oder das Member, dessen UIDs angezeigt werden sollen. Beispielsweise ruft <https://xref.docs.microsoft.com/autocomplete?text=string.format> die [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format)-Überladungen ab.

Zum Erstellen eines Links zu einem generischen Typ wie [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1) verwenden Sie das Zeichen \` (%60) gefolgt von der Anzahl von generischen Typparametern. \<xref:System.Nullable%601> erstellt einen Link zum Typ [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), während \<xref:System.Func%602> einen Link zum Delegaten [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) erstellt.

Sie können eine der folgenden Syntaxen verwenden:

1. Automatischer Link: `<xref:UID>` oder `<xref:UID?displayProperty=nameWithType>`

   Der `displayProperty`-Abfrageparameter erzeugt einen vollqualifizierten Linktext. Im Linktext wird standardmäßig nur der Member- oder Typname angezeigt.

2. Markdownlink: `[link text](xref:UID)`

   Verwenden Sie diesen, wenn Sie den angezeigten Linktext anpassen möchten.

Beispiele:

- `<xref:System.String>` wird als [String](https://docs.microsoft.com/dotnet/api/system.string) gerendert
- `<xref:System.String?displayProperty=nameWithType>` wird als [System.String](https://docs.microsoft.com/dotnet/api/system.string) gerendert
- `[String class](xref:System.String)` wird als [String Class](https://docs.microsoft.com/dotnet/api/system.string) gerendert

Weitere Informationen zur Verwendung dieser Notation finden Sie unter [Using cross reference (Verwenden von Querverweisen)](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).

Es gibt zwei Möglichkeiten, die UID zu bestimmen:

- Sehen Sie sich die Quelle für die API-Seite an, die Sie verknüpfen möchten, und finden Sie den Wert „ms.assetid“. Beachten Sie, dass einzelne Überladungswerte in der Quelle nicht angezeigt werden.
- Verwenden Sie für die Suche nach UIDs folgendes Tool: <https://xref.docs.microsoft.com/autocomplete?text=tostring> (Ersetzen Sie „tostring“ durch Teile des API-Namens, nach dem Sie suchen). Das Tool sucht nach dem angegebenen `text`-Abfrageparameter in jedem Teil der UID. Sie können zum Beispiel nach dem Membernamen (ToString), einem Teil des Membernamens (ToStri) oder dem Typ- und Membernamen (Double.ToString) suchen.

Wenn die UID die Sonderzeichen \`, \# und \* enthält, muss der UID-Wert als `%60`, `%23` bzw. `%2A` HTML-codiert werden. In manchen Fällen werden Sie codierte Klammern sehen, dies ist jedoch nicht zwingend erforderlich.

Beispiele:

- System.Threading.Tasks.Task\`1 wird `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor wird `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) wird  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

## <a name="lists"></a>Listen

### <a name="ordered-lists"></a>Geordnete Liste

1. Dies
1. Ist
1. Eine
1. Geordnete
1. Liste

#### <a name="ordered-list-with-an-embedded-list"></a>Geordnete Liste mit einer eingebetteten Liste

1. Hier
1. kommt
1. eine
1. eingebettete
    1. Frau Gloria
    1. Professor Bloom
1. geordnete
1. Liste

### <a name="unordered-lists"></a>Ungeordnete Listen

- Dies
- ist
- eine
- Aufzählungs-
- Liste

#### <a name="unordered-list-with-an-embedded-list"></a>Ungeordnete Liste mit einer eingebetteten Liste

- Diese
- Aufzählungs-
- Liste
  - Baronin von Porz
  - Reverend Grün
- enthält
- andere
  1. Oberst von Gatow
  1. Frau Weiß
- Listen

## <a name="horizontal-rule"></a>Horizontale Regel

---

## <a name="tables"></a>Tabellen

| Tabellen        | Sind           | Toll  |
| ------------- |:-------------:| -----:|
| col 3 ist      | rechtsbündig | $1600 |
| col 2 ist      | zentriert      |   $12 |
| col 1 ist der Standard | linksbündig     |    $1 |

Sie können ein [Markdowntool zum Generieren von Tabellen](https://www.tablesgenerator.com/markdown_tables) verwenden, um diese einfacher zu erstellen.

## <a name="code"></a>Code

Die beste Methode zum Einschließen von Code ist, Codeausschnitte aus einem funktionierenden Beispiel einzuschließen. Erstellen Sie Ihr Beispiel, indem Sie die Anweisungen im [Leitfaden für Mitwirkende](../CONTRIBUTING.md#contributing-to-samples) befolgen.

Sie können den Code mithilfe folgender Syntax einschließen:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- `-<language>` (*optional*, aber *empfohlen*)
  - Programmiersprache des Codeausschnitts, auf den verwiesen wird. Eine Liste mit unterstützten Werten finden Sie unter [Unterstützte Sprachen](#supported-languages).

- `<name>` (*optional*)
  - Name für den Codeausschnitt. Dieser hat keinen Einfluss auf die HTML-Ausgabe, aber er ermöglicht eine bessere Lesbarkeit Ihrer Markdownquelle.

- `<pathToFile>` (*erforderlich*)
  - Der relative Pfad im Dateisystem, der die Codeausschnittdatei angibt, auf die verwiesen werden soll.

- `<queryoption>` und `<queryoptionvalue>` (*optional*)
  - Zusammen verwendet, um festzulegen, wie der Code aus der Datei abgerufen werden soll:
    - `#`:  `#L{startlinenumber}-L{endlinenumber}` (Zeilenbereich) *oder* `#{tagname}` (Tagname).
    Von der Verwendung von Zeilennummern wird abgeraten, da diese sehr anfällig sind. Der Tagname ist die bevorzugte Methode zum Verweisen auf Codeausschnitte.
    - `range`: `?range=1,3-5` Ein Bereich von Zeilen. Dieses Beispiel umfasst die Zeilen 1, 3, 4 und 5.
    - `dedent`: `?dedent=8` Rückt die Zeilen um eine Anzahl von Leerzeichen ein – in diesem Fall 8. Diese Methode kann mit `range` und anderen Abfrageoptionen kombiniert werden, die eine Teilmenge der Zeilen einer Datei auswählen.
    - `outdent`: `?outdent=8` Kehrt den Einzug der Zeilen um eine Anzahl von Leerzeichen um – in diesem Fall 8. Diese Methode kann mit `range` und anderen Abfrageoptionen kombiniert werden, die eine Teilmenge der Zeilen einer Datei auswählen.

Es wird empfohlen, nach Möglichkeit die Option „Tagname“ zu verwenden. Der Tagname ist der Name eines Bereichs oder eines Codekommentars im Format von `Snippettagname`, der im Quellcode vorhanden ist. Im folgenden Beispiel wird gezeigt, wie auf den Tagnamen `1` verwiesen wird:

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

Außerdem können Sie sehen, wie die Codeausschnitttags in [dieser Quelldatei](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs) strukturiert sind. Weitere Informationen zur Darstellung von Tagnamen in Codeausschnitten von Quelldateien nach Programmiersprache finden Sie in den [DocFX-Richtlinien](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).

Durch das Einschließen von Ausschnitten aus vollen Programmen wird sichergestellt, dass der gesamte Code durch unser Continuous Integration-System (CI) läuft. Wenn Sie jedoch etwas zeigen müssen, das Kompilierzeit- oder Laufzeitfehler verursacht, können Sie Inlinecodeblöcke verwenden.

### <a name="inline-code-blocks-with-language-identifier"></a>Inlinecodeblöcke mit Sprachen-ID

Verwenden Sie drei Graviszeichen (\`\`\`) + eine Sprachen-ID, um die sprachenspezifische Farbcodierung für einen Codeblock anzuwenden. Im Folgenden finden Sie eine Liste der unterstützten Programmiersprachen, die die Markdownbezeichnung für jede Sprachen-ID anzeigt.

#### <a name="supported-languages"></a>Unterstützte Sprachen

|name|Markdownbezeichnung|
|-----|-------|
|.NET-Konsole|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|Azure-Befehlszeilenschnittstelle|azurecli|
|AzCopy|azcopy|
|Azure PowerShell|azurepowershell|
|Bash|Bash|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|C# im Browser|csharp-interactive|
|Konsole|Konsole|
|CSHTML|cshtml|
|DAX|dax|
|Docker-Datei|dockerfile|
|F#|fsharp|
|Gehe zu|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Kusto-Abfragesprache|kusto|
|Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|protobuf|protobuf|
|PowerApps (Dezimaltrennzeichen: Punkt)|powerapps-dot|
|PowerApps (Dezimaltrennzeichen: Komma)|powerapps-comma|
|PowerShell|powershell|
|Python|Python|
|Q#|qsharp|
|R|b|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|Visual Basic|vb|
|VBScript|vbscript|
|XAML|xaml|
|XML|xml|
|yml|yml|

Der Name `csharp-interactive` gibt die C#-Programmiersprache und die Möglichkeit an, die Beispiele über den Browser auszuführen. Diese Codeausschnitte werden in einem Docker-Container kompiliert und ausgeführt, und die Ergebnisse dieser Programmausführung werden im Browserfenster des Benutzers angezeigt.

Im Folgenden finden Sie Beispiele für Codeblöcke mit den Sprach-IDs für C# (\`\`\`csharp), Python (\`\`\`python) und PowerShell (\`\`\`powershell).

##### <a name="c"></a>C\#

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

#### <a name="python"></a>Python

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a>PowerShell

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a>Generischer Codeblock

Verwenden Sie drei Graviszeichen (&#96;&#96;&#96;) für die Codierung mit generischem Codeblock.

> Die empfohlene Vorgehensweise ist, Codeblöcke mit Sprachen-IDs wie im vorherigen Abschnitt beschrieben zu verwenden, um sicherzustellen, dass auf der Dokumentationsseite die richtige Syntax hervorgehoben wird. Verwenden Sie generische Codeblöcke nur bei Bedarf.

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a>Blockquotes

> Die Dürre hatte schon zehn Millionen Jahre angehalten, und die Herrschaft der Schrecklichen Saurier war lange vorbei. Hier am Äquator, auf dem Kontinent, der eines Tages Afrika heißen würde, hatte der Existenzkampf ein neues Stadium von Grausamkeit erreicht und ein Gewinner war noch nicht abzusehen. In diesem ausgetrockneten, ausgedörrten Land konnte nur der Kleinste oder der Schnellste oder der Zäheste gedeihen oder zu überleben hoffen.

## <a name="images"></a>Bilder

### <a name="static-image-or-animated-gif"></a>Statisches Bild oder animiertes GIF

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![Dies ist der Alternativtext](../images/Logo_DotNet.png)

### <a name="linked-image"></a>Verlinktes Bild

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

[![Alternativtext für verlinktes Bild](../images/Logo_DotNet.png)](https://dot.net)

## <a name="videos"></a>Videos

Derzeit können Sie sowohl Channel 9- als auch YouTube-Videos mit der folgenden Syntax einbetten:

### <a name="channel-9"></a>Channel 9

```markdown
> [!VIDEO <channel9_video_link>]
```

Um die korrekte URL des Videos zu ermitteln, wählen Sie die Registerkarte **Einbetten** unterhalb des Videoframes aus, und kopieren Sie die URL aus dem `<iframe>`-Element. Beispiel:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

Um die korrekte URL des Videos zu ermitteln, klicken Sie mit der rechten Maustaste auf das Video, wählen **Einbindungscode kopieren**  und kopieren die URL aus dem `<iframe>`-Element.

```markdown
> [!VIDEO <youtube_video_link>]
```

Beispiel:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>docs.microsoft-Erweiterungen

docs.microsoft bietet einige zusätzliche Erweiterungen zu GitHub Flavored Markdown.

### <a name="alerts"></a>Benachrichtigungen

Es ist wichtig, die folgenden Warnstile zu verwenden, damit diese im richtigen Stil auf der Dokumentationsseite gerendert werden. Die Rendering-Engine auf GitHub unterscheidet diese jedoch nicht.

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

Und sie werden wie folgt gerendert: ![Warnstile](../images/alerts.png)

### <a name="includes"></a>Enthält

Sie können den Markdownteil einer Datei über eine Includeanweisung in eine andere einbetten.

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a>Häkchenlisten

Für Listen ist eine benutzerdefinierte Formatvorlage vorhanden. Sie können Listen mit grünen Häkchen darstellen.

> [!div class="checklist"]
>
> - Erstellen einer .NET Core-App
> - Hinzufügen eines Verweises zum Microsoft.XmlSerializer.Generator-Paket
> - Bearbeiten Ihrer MyApp.csproj-Datei zum Hinzufügen von Abhängigkeiten
> - Hinzufügen von „XmlSerializer“ und einer Klasse
> - Erstellen und Ausführen der Anwendung

Ein Beispiel für eine Häkchenliste in Aktion finden Sie in diesem [.NET Core-Dokument](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).

### <a name="buttons"></a>Schaltflächen

> [!div class="button"]
> [Schaltflächenlinks](../docs/core/index.md)

Ein Beispiel für Schaltflächen in Aktion finden Sie in der [Visual Studio-Dokumentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).

### <a name="selectors"></a>Selektoren

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

Ein Beispiel für Selektoren in Aktion finden Sie in der [Azure-Dokumentation](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).

### <a name="step-by-steps"></a>Schritt-für-Schritt-Funktionen

>[!div class="step-by-step"]
>[Zurück](../docs/csharp/expression-trees-interpreting.md)
>[Weiter](../docs/csharp/expression-trees-translating.md)

Ein Beispiel für Schritt-für-Schritt-Funktionen in Aktion finden Sie in der [C#-Dokumentation](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).
