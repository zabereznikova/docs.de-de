---
title: XML-Dokumentation (F#)
description: Erfahren Sie mehr über Unterstützung für in F#, zum Generieren von Dokumentation aus Kommentaren.
ms.date: 05/16/2016
ms.openlocfilehash: b89ab4117f4dd71126f8e203f4a5271ab3c30021
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630820"
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
|**ZusammenfassungsText\>/Summary \<** **\<\>**|Gibt an, dass der *Text* eine kurze Beschreibung des Programm Elements ist. Die Beschreibung ist in der Regel ein oder zwei Sätze.|
|**HinweiseText\>/Remarks \<** **\<\>**|Gibt an, dass der *Text* zusätzliche Informationen zum Programmelement enthält.|
|**\>** **param\> Name=\<** "Name" Description/param Returns  **\<**|Gibt den Namen und die Beschreibung für einen Funktions-oder Methoden Parameter an.|
|**\>** **\<typeparamName\>**  = "Name" Description/typeparam  **\<**|Gibt den Namen und die Beschreibung für einen Typparameter an.|
|**\<returns\>** _text_ **\</returns\>**|Gibt an, dass *Text* den Rückgabewert einer Funktion oder Methode beschreibt.|
|**\>** **Exceptionkref\> = "Type" Description/Exception\<**  **\<**|Gibt den Typ der Ausnahme an, die generiert werden kann, sowie die Umstände, unter denen Sie ausgelöst wird.|
|**\>** **\<siehe kref=\>**  "Reference"-Text/See  **\<**|Gibt einen Inline Link zu einem anderen Programmelement an. Der *Verweis* ist der Name, wie er in der XML-Dokumentations Datei angezeigt wird. Der *Text* ist der Text, der im Link angezeigt wird.|
|**\>**   **\<seeauch kref = "** Verweis"/|Gibt einen Link zum Anzeigen von Links zur Dokumentation für einen anderen Typ an. Der *Verweis* ist der Name, wie er in der XML-Dokumentations Datei angezeigt wird. Siehe auch Links unten auf einer Dokumentationsseite.|
|**paraText\>/para \<** **\<\>**|Gibt einen Absatz von Text an. Hiermit **wird der Text** innerhalb des Kommentartags getrennt.|

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
