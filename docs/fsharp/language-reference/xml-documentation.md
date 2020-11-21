---
title: XML-Dokumentation
description: 'Erfahren Sie mehr über die Unterstützung in F # zum Erstellen von Dokumentationen aus Kommentaren.'
ms.date: 09/15/2020
ms.openlocfilehash: 24d9dbfb5e28d39e224ef9428f025298464fc7f4
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099008"
---
# <a name="document-your-code-with-xml-comments"></a>Dokumentieren von Code mit XML-Kommentaren

Sie können in F # Dokumentation aus Code Kommentaren mit drei Schrägstrichen (///) entwickeln. XML-Kommentare können Deklarationen in Code Dateien (. FS) oder Signatur Dateien (. FSI) vorangestellt werden.

XML-Dokumentationskommentare sind eine besondere Art von Kommentaren, die über der Definition von benutzerdefinierten Typen oder Membern hinzugefügt werden.
Sie sind besonders, da sie vom Compiler verarbeitet werden können, um eine XML-Dokumentationsdatei zur Kompilierzeit zu generieren.
Die vom Compiler generierte XML-Datei kann zusammen mit Ihrer .NET-Assembly verteilt werden, damit IDES Quick Infos zum Anzeigen von Informationen über Typen oder Member verwenden kann. Außerdem kann die XML-Datei mithilfe von Tools wie [fsdocs](http://fsprojects.github.io/FSharp.Formatting/) ausgeführt werden, um API-Referenz Websites zu generieren.

XML-Dokumentations Kommentare, wie alle anderen Kommentare, werden vom Compiler ignoriert, es sei denn, die unten beschriebenen Optionen sind aktiviert, um die Gültigkeit und Vollständigkeit von Kommentaren zum Zeitpunkt der Kompilierung zu überprüfen.

Sie können die XML-Datei zur Kompilierzeit generieren, indem Sie eine der folgenden Aktionen durchführen:

- Sie können dem- `GenerateDocumentationFile` Abschnitt Ihrer Projektdatei ein-Element hinzufügen `<PropertyGroup>` `.fsproj` , das eine XML-Datei im Projektverzeichnis mit dem gleichen Stamm Dateinamen wie die Assembly generiert. Beispiel:

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```

- Wenn Sie eine Anwendung mit Visual Studio entwickeln, klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus. Wählen Sie im Eigenschaftendialogfeld die Registerkarte **Erstellen** aus, und aktivieren Sie das Kontrollkästchen bei **XML-Dokumentationsdatei**. Sie können auch den Speicherort ändern, an den der Compiler die Datei schreibt.

Es gibt zwei Möglichkeiten, XML-Dokumentations Kommentare zu schreiben: mit und ohne XML-Tags. Beide verwenden Kommentare mit drei Schrägstrichen.

## <a name="comments-without-xml-tags"></a>Kommentare ohne XML-Tags

Wenn ein `///` Kommentar nicht mit einem beginnt `<` , wird der gesamte Kommentartext als Zusammenfassungs Dokumentation für das direkt nachfolgende Code Konstrukt entnommen. Verwenden Sie diese Methode, wenn Sie nur eine kurze Zusammenfassung für jedes Konstrukt schreiben möchten.

Der Kommentar wird während der Vorbereitung der Dokumentation in XML codiert, sodass Zeichen wie,, und nicht mit Escapezeichen versehen `<` `>` `&` werden müssen. Wenn Sie ein Zusammenfassungs Kennzeichen nicht explizit angeben, sollten Sie keine anderen Tags angeben, z. b. " **param** " oder " **Returns** Tags".

Das folgende Beispiel zeigt die alternative Methode ohne XML-Tags. In diesem Beispiel wird der gesamte Text im Kommentar als Zusammenfassung angesehen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="comments-with-xml-tags"></a>Kommentare mit XML-Tags

Wenn ein Kommentartext mit `<` (normalerweise `<summary>` ) beginnt, wird er mithilfe von XML-Tags als XML-formatierter Kommentartext behandelt. In dieser Sekunde können Sie separate Hinweise für eine kurze Zusammenfassung, zusätzliche Hinweise, eine Dokumentation für die einzelnen Parameter und Typparameter und ausgelöste Ausnahmen sowie eine Beschreibung des Rückgabewerts angeben.

Im folgenden finden Sie einen typischen XML-Dokumentations Kommentar in einer Signatur Datei:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="recommended-tags"></a>Empfohlene Tags

Wenn Sie XML-Tags verwenden, werden in der folgenden Tabelle die äußeren Tags beschrieben, die in F #-XML-Code Kommentaren erkannt werden.

| Tagsyntax                                  | BESCHREIBUNG |
|---------------------------------------------|-----------|
| `<summary>`**_Text_**`</summary>`           | Gibt an, dass der *Text* eine kurze Beschreibung des Programm Elements ist. Die Beschreibung ist in der Regel ein oder zwei Sätze.|
| `<remarks>`**_Text_**`</remarks>`           | Gibt an, dass der *Text* zusätzliche Informationen zum Programmelement enthält.|
| `<param name="`**_Name_** `">` **_Beschreibung_**`</param>` | Gibt den Namen und die Beschreibung für einen Funktions-oder Methoden Parameter an.|
| `<typeparam name="`**_Name_** `">` **_Beschreibung_**`</typeparam>` | Gibt den Namen und die Beschreibung für einen Typparameter an.|
| `<returns>`**_Text_**`</returns>`           | Gibt an, dass *Text* den Rückgabewert einer Funktion oder Methode beschreibt.|
| `<exception cref="`**_Typ_** `">` **_Beschreibung_**`</exception>` |Gibt den Typ der Ausnahme an, die generiert werden kann, sowie die Umstände, unter denen Sie ausgelöst wird.|
| `<seealso cref="`**_Angabe_**`"/>`      | Gibt einen Link zum Anzeigen von Links zur Dokumentation für einen anderen Typ an. Der *Verweis* ist der Name, wie er in der XML-Dokumentations Datei angezeigt wird. Siehe auch Links unten auf einer Dokumentationsseite.|

In der folgenden Tabelle werden die Tags für die Verwendung in Beschreibungs Abschnitten beschrieben:

| Tagsyntax                                | BESCHREIBUNG |
|-------------------------------------------|-------------|
| `<para>`**_Text_**`</para>`               | Gibt einen Absatz von Text an. Hiermit **wird der Text** innerhalb des Kommentartags getrennt.|
| `<code>`**_Text_**`</code>`               | Gibt an, dass der *Text* mehrere Codezeilen enthält. Dieses Tag kann von Dokumentations Generatoren zum Anzeigen von Text in einer Schriftart verwendet werden, die für Code geeignet ist.|
| `<paramref name="`**_Benennen_**`"/>`         | Gibt einen Verweis auf einen Parameter im gleichen Dokumentations Kommentar an.|
| `<typeparamref name="`**_Benennen_**`"/>`     | Gibt einen Verweis auf einen Typparameter im gleichen Dokumentations Kommentar an.|
| `<c>`**_Text_**`</c>`                     | Gibt an, dass der *Text* Inline Code ist. Dieses Tag kann von Dokumentations Generatoren zum Anzeigen von Text in einer Schriftart verwendet werden, die für Code geeignet ist.|
| `<see cref="`**_Verweis_** `">` **_Text_**`</see>` | Gibt einen Inline Link zu einem anderen Programmelement an. Der *Verweis* ist der Name, wie er in der XML-Dokumentations Datei angezeigt wird. Der *Text* ist der Text, der im Link angezeigt wird.|

### <a name="user-defined-tags"></a>Benutzerdefinierter Tags

Die vorherigen Tags stellen diejenigen dar, die vom f #-Compiler und typischen F #-Editor-Tools erkannt werden. Ein Benutzer kann jedoch auch eigene Tags definieren.
Tools wie fsdocs bieten Unterstützung für zusätzliche Tags wie [\<namespacedoc>](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1031-xmldoc-extensions.md) .
Benutzerdefinierte oder interne Dokumentationsgenerierungstools können auch mit den Standardtags verwendet werden, und mehrere Ausgabeformate von HTML in PDF können unterstützt werden.

## <a name="compile-time-checking"></a>Überprüfung der Kompilierzeit

Wenn `--warnon:3390` aktiviert ist, überprüft der Compiler die Syntax des XML-Codes und der Parameter, auf die in `<param>` -und-Tags verwiesen wird `<paramref>` .

## <a name="documenting-f-constructs"></a>Dokumentieren von F #-Konstrukten

F #-Konstrukte, wie z. b. Module, Elemente, Union-Fälle und Daten Satz Felder, werden durch einen `///` Kommentar unmittelbar vor ihrer Deklaration dokumentiert.
Bei Bedarf werden implizite Konstruktoren von Klassen dokumentiert, indem ein `///` Kommentar vor der Argumentliste gegeben wird. Beispiel:

```fsharp
/// This is the type
type SomeType
      /// This is the implicit constructor
      (a: int, b: int) =

    /// This is the member
    member _.Sum() = a + b
```

## <a name="limitations"></a>Einschränkungen

Einige Features der XML-Dokumentation in c# und anderen .NET-Sprachen werden in c# nicht unterstützt.

- In F # müssen Querverweise die vollständige XML-Signatur des entsprechenden Symbols verwenden, z. b `cref="T:System.Console"` ..
  Einfache Kreuz Verweise im c#-Format, z `cref="Console"` . b., werden nicht vollständig in vollständige XML-Signaturen erläutert, und diese Elemente werden vom F #-Compiler nicht geprüft. Einige Dokumentations Tools können die Verwendung dieser Querverweise durch nachfolgende Verarbeitung zulassen, aber die vollständigen Signaturen sollten verwendet werden.

- Die Tags `<include>` `<inheritdoc>` werden vom F #-Compiler nicht unterstützt. Wenn Sie verwendet werden, wird kein Fehler ausgegeben, aber Sie werden einfach in die generierte Dokumentations Datei kopiert, ohne dass sich dies auf die generierte Dokumentation auswirkt.

- Querverweise werden vom F #-Compiler nicht geprüft, auch wenn `-warnon:3390` verwendet wird.

- Die in den Tags verwendeten Namen `<typeparam>` und `<typeparamref>` werden nicht vom F #-Compiler geprüft, auch wenn `--warnon:3390` verwendet wird.

- Wenn die Dokumentation fehlt, werden keine Warnungen ausgegeben, auch wenn `--warnon:3390` verwendet wird.

## <a name="recommendations"></a>Empfehlungen

Das Dokumentieren von Code wird aus vielen Gründen empfohlen. Im folgenden finden Sie einige bewährte Methoden, allgemeine Anwendungsszenarien und Dinge, die Sie kennen sollten, wenn Sie XML-Dokumentations Tags in Ihrem F #-Code verwenden.

- Aktivieren Sie die-Option `--warnon:3390` im Code, um sicherzustellen, dass Ihre XML-Dokumentation gültige XML-Daten ist.

- Fügen Sie Signatur Dateien hinzu, um lange XML-Dokumentations Kommentare von ihrer Implementierung zu trennen.

- Aus Gründen der Konsistenz sollten alle öffentlich sichtbaren Typen und deren Member dokumentiert werden. Tun Sie dies wenn nötig vollständig.

- Die minimale Anzahl von Modulen, Typen und deren Membern sollte einen einfachen `///` Kommentar oder ein `<summary>` Tag aufweisen. Dies wird in einem QuickInfo-Fenster für die automatische Vervollständigung in F #-Bearbeitungs Tools angezeigt.

- Dokumentationstext sollte in vollständigen Sätze geschrieben werden, die mit Punkten enden.

## <a name="see-also"></a>Weitere Informationen

- [C#-XML-Dokumentations Kommentare &#40;C-&#35; Programmier Handbuch&#41;](../../csharp/programming-guide/xmldoc/index.md).
- [F#-Sprachreferenz](index.md)
- [Compileroptionen](compiler-options.md)
