---
title: XML-Dokumentation
description: Erfahren Sie mehr über Unterstützung für in F#, zum Generieren von Dokumentation aus Kommentaren.
ms.date: 05/16/2016
ms.openlocfilehash: 0a87915c361fc88f0c05264e1c17278fd656a167
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344689"
---
# <a name="xml-documentation"></a>XML-Dokumentation

Sie können die Dokumentation von drei Schrägstrichen (/ / /) erstellen code in F#. XML-Kommentare können Deklarationen in Code Dateien (. FS) oder Signatur Dateien (. FSI) vorangestellt werden.

## <a name="generating-documentation-from-comments"></a>Erstellen einer Dokumentation aus Kommentaren

Die Unterstützung in F# für das Generieren von Dokumentation aus Kommentaren ist identisch, die in anderen .NET Framework-Sprachen. Wie in anderen .NET Framework Sprachen ermöglicht die [-doc-Compileroption](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) das Entwickeln einer XML-Datei, die Informationen enthält, die Sie mithilfe eines Tools wie [docfx](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB)in die Dokumentation konvertieren können. Die Dokumentation mithilfe von Tools, sind für die Verwendung mit Assemblys, die in anderen .NET Framework-Sprachen, in der Regel geschrieben wurden generiert erzeugen einen Überblick über die APIs, die basierend auf der kompilierten Form eines F#-Konstrukte. Wenn die Tools nicht F#speziell unterstützen, entspricht die von diesen Tools generierte F# Dokumentation nicht der Ansicht einer API.

Weitere Informationen zum Generieren von Dokumentationen aus XML finden Sie unter [XML-Dokumentations Kommentare &#40;C&#35; -Programmier&#41;Handbuch](https://msdn.microsoft.com/library/b2s063f7).

## <a name="recommended-tags"></a>Empfohlene Tags

Es gibt zwei Möglichkeiten zum Schreiben von XML-Dokumentations Kommentaren. Eine besteht darin, die Dokumentation einfach direkt in einem Kommentar mit drei Schrägstrichen zu schreiben, ohne XML-Tags zu verwenden. Wenn Sie dies tun, wird der gesamte Kommentartext als Zusammenfassungs Dokumentation für das direkt nachfolgende Code Konstrukt entnommen. Verwenden Sie diese Methode, wenn Sie nur eine kurze Zusammenfassung für jedes Konstrukt schreiben möchten. Die andere Methode ist die Verwendung von XML-Tags, um eine strukturiertere Dokumentation bereitzustellen. Die zweite Methode ermöglicht es Ihnen, separate Hinweise für eine kurze Zusammenfassung, zusätzliche Hinweise, eine Dokumentation für jeden Parameter und Typparameter und die ausgelösten Ausnahmen sowie eine Beschreibung des Rückgabewerts anzugeben. In der folgenden Tabelle werden XML-Tags beschrieben, F# die in XML-Code Kommentaren erkannt werden.

|Tagsyntax|Beschreibung|
|----------|-----------|
|**\<c\>** _text_ **\</c\>**|Gibt an, dass der *Text* Code ist. Dieses Tag kann von Dokumentations Generatoren zum Anzeigen von Text in einer Schriftart verwendet werden, die für Code geeignet ist.|
|**\<Zusammenfassung\>** _Text_ **\</Summary\>**|Gibt an, dass der *Text* eine kurze Beschreibung des Programm Elements ist. Die Beschreibung ist in der Regel ein oder zwei Sätze.|
|**\<Hinweise\>** _Text_ **\</Remarks\>**|Gibt an, dass der *Text* zusätzliche Informationen zum Programmelement enthält.|
|**\<Param Name = "** _Name_ **"\>** _Description_ **\</param Returns\>**|Gibt den Namen und die Beschreibung für einen Funktions-oder Methoden Parameter an.|
|**\<typeparam Name = "** _Name_ **"\>** _Description_ **\</typeparam\>**|Gibt den Namen und die Beschreibung für einen Typparameter an.|
|**\<returns\>** _text_ **\</returns\>**|Gibt an, dass *Text* den Rückgabewert einer Funktion oder Methode beschreibt.|
|**\<Exception kref = "** _Type_ **"\>** _Description_ **\</Exception\>**|Gibt den Typ der Ausnahme an, die generiert werden kann, sowie die Umstände, unter denen Sie ausgelöst wird.|
|**\<siehe "** **\>/See\<** **\>** " auf der|Gibt einen Inline Link zu einem anderen Programmelement an. Der *Verweis* ist der Name, wie er in der XML-Dokumentations Datei angezeigt wird. Der *Text* ist der Text, der im Link angezeigt wird.|
|**\<seeauch kref = "** _Verweis_ **"/\>**|Gibt einen Link zum Anzeigen von Links zur Dokumentation für einen anderen Typ an. Der *Verweis* ist der Name, wie er in der XML-Dokumentations Datei angezeigt wird. Siehe auch Links unten auf einer Dokumentationsseite.|
|**\<para\>** _Text_ **\</para\>**|Gibt einen Absatz von Text an. Hiermit **wird der Text** innerhalb des Kommentartags getrennt.|

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgenden finden Sie einen typischen XML-Dokumentations Kommentar in einer Signatur Datei.

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel zeigt die alternative Methode ohne XML-Tags. In diesem Beispiel wird der gesamte Text im Kommentar als Zusammenfassung angesehen. Beachten Sie Folgendes: Wenn Sie kein Zusammenfassungs-Tag explizit angeben, sollten Sie keine anderen Tags angeben, z. b. " **param** " oder " **Returns** Tags".

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Compileroptionen](compiler-options.md)
