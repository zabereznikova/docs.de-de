---
title: XML-Dokumentation (F#)
description: Erfahren Sie mehr über Unterstützung für in F#, zum Generieren von Dokumentation aus Kommentaren.
ms.date: 05/16/2016
ms.openlocfilehash: 1a4cb132e65b630821e5eb2b39276c1de99aff80
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45641624"
---
# <a name="xml-documentation"></a>XML-Dokumentation

Sie können die Dokumentation von drei Schrägstrichen (/ / /) erstellen code in F#. XML-Kommentaren können Deklarationen in Codedateien (sein) oder Signaturdateien (".FSI") vorangestellt sein.

## <a name="generating-documentation-from-comments"></a>Generieren von Dokumentation aus Kommentaren

Die Unterstützung in F# für das Generieren von Dokumentation aus Kommentaren ist identisch, die in anderen .NET Framework-Sprachen. Wie in anderen .NET Framework-Sprachen die [-Doc-Compileroption](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) ermöglicht es Ihnen, eine XML-Datei zu erzeugen, die Informationen enthält, die Sie zur Dokumentation mithilfe eines Tools wie Sandcastle konvertieren können. Die Dokumentation mithilfe von Tools, sind für die Verwendung mit Assemblys, die in anderen .NET Framework-Sprachen, in der Regel geschrieben wurden generiert erzeugen einen Überblick über die APIs, die basierend auf der kompilierten Form eines F#-Konstrukte. Wenn Tools speziell F#-Unterstützung entspricht Dokumentation, die von diesen Tools generiert die F#-Ansicht einer API nicht.

Weitere Informationen zum Generieren von Dokumentation aus XML finden Sie unter [XML-Dokumentationskommentare &#40;C&#35; Programming Guide&#41;](https://msdn.microsoft.com/library/b2s063f7).

## <a name="recommended-tags"></a>Empfohlene Tags

Es gibt zwei Möglichkeiten zum Schreiben von XML-Dokumentationskommentare. Eine ist die Dokumentation direkt in einen Kommentar mit drei Schrägstrichen, einfach zu schreiben, ohne Verwendung von XML-Tags. Wenn Sie dies tun, stammen die gesamte Kommentartext mit der Zusammenfassung Dokumentation für das Codekonstrukt, die unmittelbar folgt. Verwenden Sie diese Methode aus, wenn Sie nur eine kurze Zusammenfassung für jedes Konstrukt schreiben möchten. Die andere Methode werden XML-Tags verwenden, um strukturiertere Dokumentation bereitzustellen. Die zweite Methode ermöglicht Ihnen die Angabe separate Notizen für eine kurze Zusammenfassung, zusätzliche Hinweise, die Dokumentation für jeden Parameter und Typparameter und ausgelösten Ausnahmen und eine Beschreibung des Rückgabewerts. Die folgende Tabelle beschreibt die XML-Tags, die in F#-XML-Codekommentaren erkannt werden.

|Tagsyntax|Beschreibung|
|----------|-----------|
|**&lt;c&gt;***Text*** &lt; /c&gt;**|Gibt an, dass *Text* Code. Dieses Tag kann von Dokumentationsgeneratoren verwendet werden, zum Anzeigen von Text in einer Schriftart an, die für Code geeignet ist.|
|**&lt;Zusammenfassung&gt;***Text*** &lt; /summary&gt;**|Gibt an, dass *Text* ist eine kurze Beschreibung des Programms-Elements. Die Beschreibung ist in der Regel ein oder zwei Sätze an.|
|**&lt;"Hinweise"&gt;***Text*** &lt; /Hinweise&gt;**|Gibt an, dass *Text* enthält zusätzliche Informationen über das Programmelement.|
|**&lt;Param Name = "***Namen***"&gt;***Beschreibung***&lt;/param&gt;**|Gibt den Namen und eine Beschreibung für einen Parameter-Funktion oder Methode.|
|**&lt;Typeparam Name = "***Namen***"&gt;***Beschreibung***&lt;/typeparam&gt;**|Gibt den Namen und eine Beschreibung für einen Typparameter an.|
|**&lt;Gibt&gt;***Text*** &lt; /returns&gt;**|Gibt an, dass *Text* beschreibt den Rückgabewert einer Funktion oder Methode.|
|**&lt;Ausnahme Cref = "***Typ***"&gt;***Beschreibung***&lt;/exception&gt;**|Gibt den Typ der Ausnahme, die generiert werden kann und die Umstände, unter denen sie ausgelöst wird.|
|**&lt;Siehe Cref = "***Verweis***"&gt;***Text*** &lt; /finden Sie unter&gt;**|Gibt einen Inlinelink auf ein anderes Programmelement. Die *Verweis* ist der Name, wie er in die XML-Dokumentationsdatei angezeigt wird. Die *Text* ist der Text im Link angezeigt.|
|**&lt;Seealso Cref = "***Verweis***" /&gt;**|Gibt einen Link "Siehe auch" in der Dokumentation für einen anderen Typ. Die *Verweis* ist der Name, wie er in die XML-Dokumentationsdatei angezeigt wird. Siehe auch Links in der Regel am unteren Rand eine Dokumentationsseite angezeigt werden.|
|**&lt;Para&gt;***Text***&lt;/para&gt;**|Gibt einen Textabsatz an. Dient zum Trennen von Text in die **"Hinweise"** Tag.|

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgenden finden eine typische XML-Dokumentationskommentar in einer Signaturdatei.

### <a name="code"></a>Code

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel zeigt die alternative Methode verwenden, ohne XML-Tags. In diesem Beispiel wird der gesamte Text im Kommentar als Zusammenfassung betrachtet. Beachten Sie, dass wenn Sie ein summary-Tag nicht explizit angeben, Sie nicht andere Tags, wie z. B. angeben sollten **Param** oder **gibt** Tags.

### <a name="code"></a>Code

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Compileroptionen](compiler-options.md)
