---
title: XML-Dokumentation (F#)
description: Erfahren Sie mehr über Unterstützung für in F#, zum Generieren von Dokumentation aus Kommentaren.
ms.date: 05/16/2016
ms.openlocfilehash: c5305dea8832112644710b2863269ef00feddd10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902173"
---
# <a name="xml-documentation"></a>XML-Dokumentation

Sie können die Dokumentation von drei Schrägstrichen (/ / /) erstellen code in F#. XML-Kommentaren können Deklarationen in Codedateien (sein) oder Signaturdateien (".FSI") vorangestellt sein.

## <a name="generating-documentation-from-comments"></a>Generieren von Dokumentation aus Kommentaren

Die Unterstützung in F# für das Generieren von Dokumentation aus Kommentaren ist identisch, die in anderen .NET Framework-Sprachen. Wie in anderen .NET Framework-Sprachen die [-Doc-Compileroption](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) ermöglicht es Ihnen, eine XML-Datei zu erzeugen, die Informationen, die Sie in der Dokumentation konvertieren können enthält, mithilfe eines Tools wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [ Sandcastle](https://github.com/EWSoftware/SHFB). Die Dokumentation mithilfe von Tools, sind für die Verwendung mit Assemblys, die in anderen .NET Framework-Sprachen, in der Regel geschrieben wurden generiert erzeugen einen Überblick über die APIs, die basierend auf der kompilierten Form eines F#-Konstrukte. Es sei denn, insbesondere toolunterstützung F#, Dokumentation, die mit diesen Tools generierte stimmt nicht überein. die F# Ansicht einer API.

Weitere Informationen zum Generieren von Dokumentation aus XML finden Sie unter [XML-Dokumentationskommentare &#40;C&#35; Programming Guide&#41;](https://msdn.microsoft.com/library/b2s063f7).

## <a name="recommended-tags"></a>Empfohlene Tags

Es gibt zwei Möglichkeiten zum Schreiben von XML-Dokumentationskommentare. Eine ist die Dokumentation direkt in einen Kommentar mit drei Schrägstrichen, einfach zu schreiben, ohne Verwendung von XML-Tags. Wenn Sie dies tun, stammen die gesamte Kommentartext mit der Zusammenfassung Dokumentation für das Codekonstrukt, die unmittelbar folgt. Verwenden Sie diese Methode aus, wenn Sie nur eine kurze Zusammenfassung für jedes Konstrukt schreiben möchten. Die andere Methode werden XML-Tags verwenden, um strukturiertere Dokumentation bereitzustellen. Die zweite Methode ermöglicht Ihnen die Angabe separate Notizen für eine kurze Zusammenfassung, zusätzliche Hinweise, die Dokumentation für jeden Parameter und Typparameter und ausgelösten Ausnahmen und eine Beschreibung des Rückgabewerts. Die folgende Tabelle beschreibt die XML-Tags, die im erkannt werden F# XML-Codekommentaren.

|Tagsyntax|Beschreibung|
|----------|-----------|
|**\<c\>**_text_**\</c\>**|Gibt an, dass *Text* Code. Dieses Tag kann von Dokumentationsgeneratoren verwendet werden, zum Anzeigen von Text in einer Schriftart an, die für Code geeignet ist.|
|**\<summary\>**_text_**\</summary\>**|Gibt an, dass *Text* ist eine kurze Beschreibung des Programms-Elements. Die Beschreibung ist in der Regel ein oder zwei Sätze an.|
|**\<remarks\>**_text_**\</remarks\>**|Gibt an, dass *Text* enthält zusätzliche Informationen über das Programmelement.|
|**\<param name="**_name_**"\>**_description_**\</param\>**|Gibt den Namen und eine Beschreibung für einen Parameter-Funktion oder Methode.|
|**\<typeparam name="**_name_**"\>**_description_**\</typeparam\>**|Gibt den Namen und eine Beschreibung für einen Typparameter an.|
|**\<returns\>**_text_**\</returns\>**|Gibt an, dass *Text* beschreibt den Rückgabewert einer Funktion oder Methode.|
|**\<exception cref="**_type_**"\>**_description_**\</exception\>**|Gibt den Typ der Ausnahme, die generiert werden kann und die Umstände, unter denen sie ausgelöst wird.|
|**\<see cref="**_reference_**"\>**_text_**\</see\>**|Gibt einen Inlinelink auf ein anderes Programmelement. Die *Verweis* ist der Name, wie er in die XML-Dokumentationsdatei angezeigt wird. Die *Text* ist der Text im Link angezeigt.|
|**\<seealso cref="**_reference_**"/\>**|Gibt einen Link "Siehe auch" in der Dokumentation für einen anderen Typ. Die *Verweis* ist der Name, wie er in die XML-Dokumentationsdatei angezeigt wird. Siehe auch Links in der Regel am unteren Rand eine Dokumentationsseite angezeigt werden.|
|**\<para\>**_text_**\</para\>**|Gibt einen Textabsatz an. Dient zum Trennen von Text in die **"Hinweise"** Tag.|

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
