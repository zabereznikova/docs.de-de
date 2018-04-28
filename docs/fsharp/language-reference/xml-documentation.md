---
title: XML-Dokumentation (F#)
description: Erfahren Sie mehr über Unterstützung in F# erläutert werden, zum Generieren von Dokumentation aus Kommentaren.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: c9514532904f81030752bf7a4044f70a18222cab
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="xml-documentation"></a>XML-Dokumentation

Können Sie Dokumentation vom Triple-Schrägstrich (/ / /) erzeugt code in f#. XML-Kommentare können Deklarationen in Codedateien (sein) oder Signaturdateien (".FSI") voranstellen.


## <a name="generating-documentation-from-comments"></a>Generieren von Dokumentation aus Kommentaren
Die Unterstützung in f# zum Generieren von Dokumentation aus Kommentaren ist dieselbe wie in anderen .NET Framework-Sprachen. Wie in anderen .NET Framework-Sprachen die [-Doc-Compileroption](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) ermöglicht es Ihnen, eine XML-Datei zu erzeugen, die Informationen enthält, die Sie in der Dokumentation mit einem Tool wie z. B. Sandburg konvertieren können. Die Dokumentation mithilfe der Tools, die entwickelt wurden für die Verwendung mit Assemblys, die in anderen .NET Framework-Sprachen, in der Regel geschrieben sind generiert erzeugen einen Überblick über die APIs, die auf der kompilierten Form von F#-Konstrukten basiert. Sofern nicht ausdrücklich F#-Supporttools, entspricht Dokumentation, die von diesen Tools generierten f#-Ansicht einer API nicht.

Weitere Informationen zum Generieren von Dokumentation aus XML finden Sie unter [XML-Dokumentationskommentare &#40;C&#35; Programmierhandbuch&#41;](https://msdn.microsoft.com/library/b2s063f7).


## <a name="recommended-tags"></a>Empfohlene Tags
Es gibt zwei Möglichkeiten zum Schreiben von XML-Dokumentationskommentare. Eine besteht darin, nur die Dokumentation direkt in einen Kommentar Triple-Schrägstrich schreiben, ohne Verwendung von XML-Tags. Wenn Sie so vorgehen, wird der gesamte Kommentartext als die Zusammenfassung Dokumentation für das Codekonstrukt aufgefasst, die unmittelbar folgt. Verwenden Sie diese Methode, wenn Sie nur eine kurze Zusammenfassung für jedes Konstrukt schreiben möchten. Die andere Methode ist, mit der XML-Tags mehr strukturierte Dokumentation zur Verfügung. Die zweite Methode können Sie separate Hinweise für eine kurze Zusammenfassung, zusätzliche Hinweise, Dokumentation für jeden Parameter und die Typparameter und die ausgelösten Ausnahmen und eine Beschreibung des Rückgabewerts angeben. Die folgende Tabelle beschreibt die XML-Tags, die in F#-XML-Codekommentaren erkannt werden.



|Tagsyntax|Beschreibung|
|----------|-----------|
|**&lt;c&gt;***Text*** &lt; /c&gt;**|Gibt an, dass *Text* Code ist. Dieses Tag kann durch Dokumentationsgeneratoren verwendet werden, um Text in einer Schriftart anzuzeigen, die für Code geeignet ist.|
|**&lt;Zusammenfassung&gt;***Text*** &lt; /summary&gt;**|Gibt an, dass *Text* ist eine kurze Beschreibung der das Programmelement. Die Beschreibung ist in der Regel ein oder zwei Sätze.|
|**&lt;"Hinweise"&gt;***Text*** &lt; /remarks&gt;**|Gibt an, dass *Text* enthält zusätzliche Informationen über das Programmelement.|
|**&lt;Param Name = "***Namen***"&gt;***Beschreibung***&lt;/param&gt;**|Gibt den Namen und eine Beschreibung für eine Funktion oder Methode Parameter.|
|**&lt;Typeparam Name = "***Namen***"&gt;***Beschreibung***&lt;/typeparam&gt;**|Gibt den Namen und eine Beschreibung für einen Typparameter darstellt.|
|**&lt;Gibt&gt;***Text*** &lt; /returns&gt;**|Gibt an, dass *Text* beschreibt den Rückgabewert einer Funktion oder Methode.|
|**&lt;Ausnahme Cref = "***Typ***"&gt;***Beschreibung***&lt;/exception&gt;**|Gibt den Typ der Ausnahme, die generiert werden kann und die Umstände, unter denen sie ausgelöst wird.|
|**&lt;Siehe Cref = "***Verweis***"&gt;***Text*** &lt; /finden Sie unter&gt;**|Gibt einen Inlinelink auf ein anderes Programmelement. Die *Verweis* ist der Name, wie er in der XML-Dokumentationsdatei angezeigt wird. Die *Text* ist der Text im Link dargestellt.|
|**&lt;Seealso Cref = "***Verweis***" /&gt;**|Gibt einen Link Siehe auch in der Dokumentation für einen anderen Typ. Die *Verweis* ist der Name, wie er in der XML-Dokumentationsdatei angezeigt wird. Siehe auch Links, die in der Regel am unteren Rand einer Dokumentationsseite angezeigt werden.|
|**&lt;Para&gt;***Text***&lt;/para&gt;**|Gibt einen Textabsatz an. Dies dient zum Trennen von Text in der **"Hinweise"** Tag.|

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung
Im folgenden Code wird eine typische XML-Dokumentationskommentar in einer Signaturdatei.


### <a name="code"></a>Code
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]
    
## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung
Das folgende Beispiel zeigt die alternative Methode verwenden, ohne XML-Tags. In diesem Beispiel wird der gesamte Text im Kommentar eine Zusammenfassung betrachtet. Beachten Sie, dass wenn Sie eine Zusammenfassung Tag nicht explizit angeben, Sie keine anderen Tags wie z. B. angeben sollten **Param** oder **gibt** Tags.


### <a name="code"></a>Code
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]
    
## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Compileroptionen](compiler-options.md)
