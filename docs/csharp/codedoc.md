---
title: Dokumentieren von Code mit XML-Kommentaren
description: Informationen zum Dokumentieren Ihres Codes mit XML-Dokumentationskommentaren und zum Erstellen einer XML-Dokumentationsdatei zum Zeitpunkt der Kompilierung.
ms.date: 02/14/2017
ms.technology: csharp-fundamentals
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.openlocfilehash: a9142b36586de4d08dec6c4b72bfd1725b4830ac
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037651"
---
# <a name="documenting-your-code-with-xml-comments"></a>Dokumentieren von Code mit XML-Kommentaren

XML-Dokumentationskommentare sind eine besondere Art von Kommentaren, die über der Definition von benutzerdefinierten Typen oder Membern hinzugefügt werden.
Sie sind besonders, da sie vom Compiler verarbeitet werden können, um eine XML-Dokumentationsdatei zur Kompilierzeit zu generieren.
Die vom Compiler generierte XML-Datei kann zusammen mit Ihrer .NET-Assembly verteilt werden, damit Visual Studio und andere IDEs mit IntelliSense QuickInfos über Typen oder Member anzeigen können. Darüber hinaus kann die XML-Datei mithilfe von Tools wie [DocFX](https://dotnet.github.io/docfx/) und [Sandcastle](https://github.com/EWSoftware/SHFB) ausgeführt werden, um API-Verweiswebsites zu generieren.

XML-Dokumentationskommentare werden wie alle anderen Kommentare vom Compiler ignoriert.

Sie können die XML-Datei zur Kompilierzeit generieren, indem Sie eine der folgenden Aktionen durchführen:

- Wenn Sie eine Anwendung mit .NET Core über die Befehlszeile entwickeln, können Sie im Abschnitt `<PropertyGroup>` der CSPROJ-Projektdatei ein [DocumentationFile-Element](/visualstudio/msbuild/common-msbuild-project-properties) hinzufügen. Im folgenden Beispiel wird eine XML-Datei im Projektverzeichnis mit dem gleichen Stammdateinamen wie die Assembly generiert:

   ```xml
   <DocumentationFile>bin\$(Configuration)\$(TargetFramework)\$(AssemblyName).xml</DocumentationFile>
   ```

   Sie können auch den genauen absoluten oder relativen Pfad und den Namen der XML-Datei angeben. Im folgenden Beispiel wird die XML-Datei in demselben Verzeichnis wie die Debugversion einer Anwendung generiert:

   ```xml
   <DocumentationFile>bin\Debug\netcoreapp2.1\App.xml</DocumentationFile>
   ```

- Wenn Sie eine Anwendung mit Visual Studio entwickeln, klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus. Wählen Sie im Eigenschaftendialogfeld die Registerkarte **Erstellen** aus, und aktivieren Sie das Kontrollkästchen bei **XML-Dokumentationsdatei**. Sie können auch den Speicherort ändern, an den der Compiler die Datei schreibt.

- Wenn Sie eine .NET Framework-Anwendung über die Befehlszeile kompilieren, fügen Sie beim Kompilieren die [-doc-Compileroption](language-reference/compiler-options/doc-compiler-option.md) hinzu.  

XML-Dokumentationskommentare verwenden dreifache Schrägstriche (`///`) und einen Kommentartext im XML-Format. Beispiel:

[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]

## <a name="walkthrough"></a>Exemplarische Vorgehensweise

Betrachten wir das Dokumentieren einer sehr einfachen math-Bibliothek, um neuen Entwicklern das Verstehen/Beitragen und Entwicklern von Drittanbietern das Verwenden zu erleichtern.

Hier der Code für die einfache math-Bibliothek:

[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]

Die Beispielbibliothek unterstützt die vier wichtigen arithmetischen Operationen `add`, `subtract`, `multiply` und `divide` auf den Datentypen `int` und `double`.

Nun möchten Sie in der Lage sein, ein API-Referenzdokument aus dem Code für Entwickler von Drittanbietern zu erstellen, die Ihre Bibliothek verwenden, aber keinen Zugriff auf den Quellcode haben.
Wie bereits in der vorhandenen Dokumentation zu XML zu lesen ist, können Tags verwendet werden, um dies zu erreichen. Im Folgenden stellen wir Ihnen die XML-Standardtags vor, die vom C#-Compiler unterstützt werden.

## <a name="summary"></a>\<summary>

Das `<summary>`-Tag fügt kurze Informationen über einen Typ oder Member hinzu.
Die Verwendung wird veranschaulicht, indem es zur `Math`-Klassendefinition und zur ersten `Add`-Methode hinzugefügt wird. Sie können es gerne auf den Rest Ihres Codes anwenden.

[!code-csharp[Summary Tag](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]

Das `<summary>`-Tag ist sehr wichtig, und es wird empfohlen, dass Sie es einfügen, da sein Inhalt die primäre Quelle für Informationen über Typ oder Member in IntelliSense oder in einem API-Referenzdokument ist.

## <a name="remarks"></a>\<remarks>

Das `<remarks>`-Tag ergänzt die Informationen über Typen oder Member, die das `<summary>`-Tag enthält. In diesem Beispiel fügen Sie es einfach der Klasse hinzu.

[!code-csharp[Remarks Tag](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]

## <a name="returns"></a>\<returns>

Das `<returns>`-Tag beschreibt den Rückgabewert der Deklaration einer Methode.
Wie zuvor veranschaulicht das folgende Beispiel das `<returns>`-Tag bei der ersten `Add`-Methode. Sie können dasselbe bei anderen Methoden vornehmen.

[!code-csharp[Returns Tag](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]

## <a name="value"></a>\<Wert>

Das `<value>`-Tag ist mit dem `<returns>`-Tag vergleichbar, wird aber für Eigenschaften verwendet.
Falls Ihre `Math`-Bibliothek über eine statische Eigenschaft namens `PI` verfügt, können Sie dieses Tag wie folgt verwenden:

[!code-csharp[Value Tag](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]

## <a name="example"></a>\<example>

Das `<example>`-Tag wird verwendet, um ein Beispiel in die XML-Dokumentation aufzunehmen.
Dies beinhaltet die Verwendung des untergeordneten `<code>`-Tags.

[!code-csharp[Example Tag](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]

Das `code`-Tag behält Zeilenumbrüche und Einzug für längere Beispiele bei.

## <a name="para"></a>\<para>

Das `<para>`-Tag wird verwendet, um den Inhalt innerhalb seines übergeordneten Tags zu formatieren. `<para>` wird in der Regel innerhalb eines Tags wie `<remarks>` oder `<returns>` verwendet, um Text in Absätze zu unterteilen.
Sie können die Inhalte des `<remarks>`-Tags für Ihre Klassendefinition formatieren.

[!code-csharp[Para Tag](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]

## <a name="c"></a>\<c>

Bei der Formatierung wird außerdem das `<c>`-Tag verwendet, um einen Teil des Texts als Code zu markieren.
Es ist wie das `<code>`-Tag, aber inline. Es ist nützlich, wenn Sie ein schnelles Codebeispiel als Teil des Taginhalts anzeigen möchten.
Aktualisieren wir die Dokumentation für die `Math`-Klasse.

[!code-csharp[C Tag](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]

## <a name="exception"></a>\<exception>

Mithilfe des `<exception>`-Tags können Sie Ihre Entwickler wissen lassen, dass eine Methode bestimmte Ausnahmen auslösen kann.
In Ihrer `Math`-Bibliothek sehen Sie, dass beide `Add`-Methoden eine Ausnahme auslösen, wenn eine bestimmte Bedingung erfüllt ist. Nicht so offensichtlich ist jedoch, dass die ganzzahlige `Divide`-Methode auch auslöst, wenn der `b`-Parameter null ist. Fügen Sie nun eine Ausnahmendokumentation zu dieser Methode hinzu.

[!code-csharp[Exception Tag](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]

Das `cref`-Attribut stellt einen Verweis auf eine Ausnahme dar, die von der aktuellen Kompilierungsumgebung verfügbar ist.
Dies kann jeder Typ sein, der im Projekt definiert ist, oder eine Assembly, auf die verwiesen wird. Der Compiler wird eine Warnung ausgeben, wenn sein Wert nicht aufgelöst werden kann.

## <a name="see"></a>\<see>

Das `<see>`-Tag ermöglicht die Erstellung eines klickbaren Links zu einer Dokumentationsseite für ein anderes Codeelement. Im nächsten Beispiel wird ein klickbarer Link zwischen den beiden `Add`-Methoden erstellt.

[!code-csharp[See Tag](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]

Das `cref`-Attribut ist ein **erforderliches** Attribut, das einen Verweis auf einen Typ oder auf dessen Member darstellt, der von der aktuellen Kompilierungsumgebung verfügbar ist.
Dies kann jeder Typ sein, der im Projekt definiert ist, oder eine Assembly, auf die verwiesen wird.

## <a name="seealso"></a>\<seealso>

Das `<seealso>`-Tag wird auf die gleiche Weise verwendet wie das `<see>`-Tag. Der einzige Unterschied ist, dass dessen Inhalt in der Regel in einem „See Also“-Abschnitt („Siehe auch“) platziert wird. Hier fügen wir ein `seealso`-Tag auf die ganzzahlige `Add`-Methode hinzu, um auf andere Methoden in der Klasse zu verweisen, die ganzzahlige Parameter akzeptieren:

[!code-csharp[Seealso Tag](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]

Das `cref`-Attribut stellt einen Verweis auf einen Typ oder auf dessen Member dar, der von der aktuellen Kompilierungsumgebung verfügbar ist.
Dies kann jeder Typ sein, der im Projekt definiert ist, oder eine Assembly, auf die verwiesen wird.

## <a name="param"></a>\<param>

Das `<param>`-Tag wird verwendet, um die Parameter einer Methode zu beschreiben. Hier sehen Sie ein Beispiel für die doppelte `Add`-Methode: Der Parameter, den der Tag beschreibt, ist im **erforderlichen** `name`-Attribut angegeben.

[!code-csharp[Param Tag](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]

## <a name="typeparam"></a>\<typeparam>

Das `<typeparam>`-Tag wird genau wie das `<param>`-Tag verwendet, aber für den generischen Typ oder Methodendeklarationen, um einen generischen Parameter zu beschreiben.
Fügen Sie der `Math`-Klasse eine schnelle generische Methode hinzu, um zu überprüfen, ob eine Menge größer als die andere ist.

[!code-csharp[Typeparam Tag](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]

## <a name="paramref"></a>\<paramref>

Manchmal beschreiben Sie möglicherweise gerade die Funktionsweise einer Methode in einem möglichen `<summary>`-Tag und wollen dann auf einen Parameter verweisen. Der `<paramref>`-Tag eignet sich hervorragend dafür. Aktualisieren wir die Zusammenfassung der doppelt basierten `Add`-Methode. Wie beim `<param>`-Tag wird der Name des Parameters im **erforderlichen** `name`-Attribut angegeben.

[!code-csharp[Paramref Tag](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]

## <a name="typeparamref"></a>\<typeparamref>

Das `<typeparamref>`-Tag wird genau wie das `<paramref>`-Tag verwendet, aber für den generischen Typ oder Methodendeklarationen, um einen generischen Parameter zu beschreiben.
Sie können die gleiche generische Methode verwenden, die Sie zuvor erstellt haben.

[!code-csharp[Typeparamref Tag](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]

## <a name="list"></a>\<list>

Das `<list>`-Tag wird verwendet, um Dokumentationsinformationen als sortierte Liste, unsortierte Liste oder Tabelle zu formatieren.
Erstellen Sie eine unsortierte Liste aller mathematischen Operationen, die Ihre `Math`-Bibliothek unterstützt.

[!code-csharp[List Tag](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]

Sie können eine sortierte Liste oder eine Tabelle erstellen, indem Sie das Attribut `type` auf `number` bzw. `table` ändern.

### <a name="putting-it-all-together"></a>Zusammenfassung

Wenn Sie diesem Tutorial gefolgt sind und die Tags soweit erforderlich für Ihren Code übernommen haben, sollte Ihr Code nun ähnlich wie der folgende aussehen:

[!code-csharp[Tagged Library](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]

Aus Ihrem Code können Sie eine detaillierte Dokumentationswebsite mit klickbaren Querverweisen generieren. Sie sehen sich jedoch mit einem anderen Problem konfrontiert: Ihr Code ist schwer zu lesen.
Dies ist ein Albtraum für jeden Entwickler, der zu diesem Code beitragen möchte, da er so viele Informationen durchsuchen muss.
Zum Glück gibt es ein XML-Tag, das Ihnen dabei helfen kann:

## <a name="include"></a>\<include>

Mit dem `<include>`-Tag kann auf Kommentare in einer separaten XML-Datei verwiesen werden, die die Typen und Member im Quellcode beschreibt, anstatt Dokumentationskommentare direkt in der Quellcodedatei zu platzieren.

Nun verschieben Sie alle XML-Tags in eine separate XML-Datei mit dem Namen `docs.xml`. Sie können die Datei beliebig benennen.

[!code-xml[Sample XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]

Im obigen XML werden die Dokumentationskommentare jedes Members direkt innerhalb eines Tags angezeigt, das nach der Funktion benannt ist. Sie können Ihre eigene Strategie auswählen.
Ihre XML-Kommentare befinden sich nun in einer separaten Datei. Sehen wir uns an, wie der Code mit dem `<include>`-Tag besser lesbar gemacht werden kann:

[!code-csharp[Include Tag](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]

Nun ist der Code wieder gut lesbar, und es sind keine Dokumentationsinformationen verloren gegangen.

Das `file`-Attribut stellt den Namen der XML-Datei dar, die die Dokumentation enthält.

Das `path`-Attribut stellt eine [XPath](../standard/data/xml/xpath-queries-and-namespaces.md)-Abfrage an den vorhandenen `tag name` im angegebenen `file` dar.

Das `name`-Attribut stellt den Namensbezeichner in dem Tag dar, das sich vor den Kommentaren befindet.

Das `id`-Attribut, das anstelle von `name` verwendet werden kann, stellt die ID für das Tag dar, das sich vor den Kommentaren befindet.

### <a name="user-defined-tags"></a>Benutzerdefinierte Tags

Alle oben genannten Tags werden vom C#-Compiler erkannt. Ein Benutzer kann jedoch auch eigene Tags definieren.
Tools wie Sandcastle bieten Unterstützung für zusätzliche Tags wie [`<event>`](https://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm) oder [`<note>`](https://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) und unterstützen sogar [documenting namespaces (Dokumentieren von Namespaces)](https://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).
Benutzerdefinierte oder interne Dokumentationsgenerierungstools können auch mit den Standardtags verwendet werden, und mehrere Ausgabeformate von HTML in PDF können unterstützt werden.

## <a name="recommendations"></a>Empfehlungen

Das Dokumentieren von Code wird aus vielen Gründen empfohlen. Es folgen einige bewährte Methoden, allgemeine Anwendungsfallszenarios und Dinge, die Sie wissen sollten, wenn Sie XML-Dokumentationstags in Ihrem C#-Code verwenden.

- Aus Gründen der Konsistenz sollten alle öffentlich sichtbaren Typen und deren Member dokumentiert werden. Tun Sie dies wenn nötig vollständig.
- Private Member können auch mithilfe von XML-Kommentaren dokumentiert werden. Dadurch wird jedoch das (potenziell vertrauliche) Innenleben Ihrer Bibliothek verfügbar gemacht.
- Als absolutes Minimum sollten Typen und deren Member über ein `<summary>`-Tag verfügen, da dessen Inhalt für IntelliSense erforderlich ist.
- Dokumentationstext sollte in vollständigen Sätze geschrieben werden, die mit Punkten enden.
- Partielle Klassen werden vollständig unterstützt, und Dokumentationsinformationen werden zu einem einzigen Eintrag für diesen Typ verkettet.
- Der Compiler überprüft die Syntax der Tags `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` und `<typeparam>`.
- Der Compiler überprüft die Parameter, die Dateipfade und Verweise auf andere Teile des Codes enthalten.

## <a name="see-also"></a>Siehe auch

- [XML-Dokumentationskommentare (C#-Programmierhandbuch)](programming-guide/xmldoc/index.md)
- [Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
