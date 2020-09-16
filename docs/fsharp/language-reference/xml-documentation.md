---
title: XML-Dokumentation
description: 'Erfahren Sie mehr über die Unterstützung in F # zum Erstellen von Dokumentationen aus Kommentaren.'
ms.date: 05/16/2016
ms.openlocfilehash: 03d14cef910d149f0c7a2f3a49c8cf4606ac5305
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556576"
---
# <a name="xml-documentation"></a>XML-Dokumentation

Sie können in F # Dokumentation aus Code Kommentaren mit drei Schrägstrichen (///) entwickeln. XML-Kommentare können Deklarationen in Code Dateien (. FS) oder Signatur Dateien (. FSI) vorangestellt werden.

## <a name="generating-documentation-from-comments"></a>Erstellen einer Dokumentation aus Kommentaren

Die Unterstützung in F # zum Erstellen von Dokumentationen aus Kommentaren ist mit der Unterstützung in anderen .NET Framework Sprachen identisch. Wie in anderen .NET Framework Sprachen ermöglicht die [-doc-Compileroption](./compiler-options.md) das Entwickeln einer XML-Datei, die Informationen enthält, die Sie mithilfe eines Tools wie [docfx](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB)in die Dokumentation konvertieren können. Die mithilfe von Tools generierte Dokumentation, die für Assemblys entworfen wurde, die in anderen .NET Framework Sprachen geschrieben wurden, erzeugen im Allgemeinen eine Ansicht der APIs, die auf der kompilierten Form von F #-Konstrukten basieren. Die von diesen Tools generierte Dokumentation stimmt nicht mit der f #-Ansicht einer API identisch, es sei denn, die Tools unterstützen f #.

Weitere Informationen zum Generieren von Dokumentationen aus XML finden Sie unter [XML-Dokumentations Kommentare &#40;C&#35;-Programmier Handbuch&#41;](../../csharp/programming-guide/xmldoc/index.md).

## <a name="recommended-tags"></a>Empfohlene Tags

Es gibt zwei Möglichkeiten zum Schreiben von XML-Dokumentations Kommentaren. Eine besteht darin, die Dokumentation einfach direkt in einem Kommentar mit drei Schrägstrichen zu schreiben, ohne XML-Tags zu verwenden. Wenn Sie dies tun, wird der gesamte Kommentartext als Zusammenfassungs Dokumentation für das direkt nachfolgende Code Konstrukt entnommen. Verwenden Sie diese Methode, wenn Sie nur eine kurze Zusammenfassung für jedes Konstrukt schreiben möchten. Die andere Methode ist die Verwendung von XML-Tags, um eine strukturiertere Dokumentation bereitzustellen. Die zweite Methode ermöglicht es Ihnen, separate Hinweise für eine kurze Zusammenfassung, zusätzliche Hinweise, eine Dokumentation für jeden Parameter und Typparameter und die ausgelösten Ausnahmen sowie eine Beschreibung des Rückgabewerts anzugeben. In der folgenden Tabelle werden XML-Tags beschrieben, die in F #-XML-Code Kommentaren erkannt werden.

|Tagsyntax|BESCHREIBUNG|
|----------|-----------|
|**\<c\>**_Text_**\</c\>**|Gibt an, dass der *Text* Code ist. Dieses Tag kann von Dokumentations Generatoren zum Anzeigen von Text in einer Schriftart verwendet werden, die für Code geeignet ist.|
|**\<summary\>**_Text_**\</summary\>**|Gibt an, dass der *Text* eine kurze Beschreibung des Programm Elements ist. Die Beschreibung ist in der Regel ein oder zwei Sätze.|
|**\<remarks\>**_Text_**\</remarks\>**|Gibt an, dass der *Text* zusätzliche Informationen zum Programmelement enthält.|
|**\<param name="**_name_**"\>**_Beschreibung_**\</param\>**|Gibt den Namen und die Beschreibung für einen Funktions-oder Methoden Parameter an.|
|**\<typeparam name="**_name_**"\>**_Beschreibung_**\</typeparam\>**|Gibt den Namen und die Beschreibung für einen Typparameter an.|
|**\<returns\>**_Text_**\</returns\>**|Gibt an, dass *Text* den Rückgabewert einer Funktion oder Methode beschreibt.|
|**\<exception cref="**_type_**"\>**_Beschreibung_**\</exception\>**|Gibt den Typ der Ausnahme an, die generiert werden kann, sowie die Umstände, unter denen Sie ausgelöst wird.|
|**\<see cref="**_reference_**"\>**_Text_**\</see\>**|Gibt einen Inline Link zu einem anderen Programmelement an. Der *Verweis* ist der Name, wie er in der XML-Dokumentations Datei angezeigt wird. Der *Text* ist der Text, der im Link angezeigt wird.|
|**\<seealso cref="**_reference_**"/\>**|Gibt einen Link zum Anzeigen von Links zur Dokumentation für einen anderen Typ an. Der *Verweis* ist der Name, wie er in der XML-Dokumentations Datei angezeigt wird. Siehe auch Links unten auf einer Dokumentationsseite.|
|**\<para\>**_Text_**\</para\>**|Gibt einen Absatz von Text an. Hiermit **wird der Text** innerhalb des Kommentartags getrennt.|

## <a name="example"></a>Beispiel

### <a name="description"></a>BESCHREIBUNG

Im folgenden finden Sie einen typischen XML-Dokumentations Kommentar in einer Signatur Datei.

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>Beispiel

### <a name="description"></a>BESCHREIBUNG

Das folgende Beispiel zeigt die alternative Methode ohne XML-Tags. In diesem Beispiel wird der gesamte Text im Kommentar als Zusammenfassung angesehen. Beachten Sie Folgendes: Wenn Sie kein Zusammenfassungs-Tag explizit angeben, sollten Sie keine anderen Tags angeben, z. b. " **param** " oder " **Returns** Tags".

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Compileroptionen](compiler-options.md)
