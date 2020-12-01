---
title: Compileranweisungen
description: 'Erfahren Sie mehr über F #-sprach Präprozessordirektiven, bedingte Kompilierungs Direktiven, Zeilen Anweisungen und Compilerdirektiven.'
ms.date: 12/10/2018
f1_keywords:
- '#endif_FS'
ms.openlocfilehash: ff106339478c3413dc6458b12f12e1d3f9cd1fe5
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96438169"
---
# <a name="compiler-directives"></a>Compileranweisungen

In diesem Thema werden Prozessor- und Compileranweisungen beschrieben.

## <a name="preprocessor-directives"></a>Präprozessoranweisungen

Einer Präprozessordirektive wird das #-Symbol vorangestellt und wird für sich genommen in einer Zeile angezeigt. Sie wird durch den Präprozessor interpretiert, der vom Compiler ausgeführt wird.

In der folgenden Tabelle werden die Präprozessoranweisungen aufgelistet, die in F# verfügbar sind.

|Anweisung|Beschreibung|
|---------|-----------|
|`#if`*Symbol*|Unterstützt die bedingte Kompilierung. Code im-Abschnitt, nachdem der eingefügt wurde, `#if` Wenn das *Symbol* definiert ist. Das Symbol kann auch mit negiert werden `!` .|
|`#else`|Unterstützt die bedingte Kompilierung. Markiert einen einzubeziehenden Codeabschnitt, wenn das mit dem vorherigen verwendeten `#if` nicht definiert ist.|
|`#endif`|Unterstützt die bedingte Kompilierung. Markiert das Ende eines bedingten Codeabschnitts.|
|`#`Stimmen *int*,<br/>`#`Stimmen *int* - *Zeichenfolge*<br/>`#`Stimmen *int* *-wörtliche Zeichenfolge*|Gibt die ursprüngliche Quellcodezeile und den Dateinamen für das Debuggen an. Diese Funktion wird für Tools bereitgestellt, die F#-Quellcode generieren.|
|`#nowarn`*warningCode*|Deaktiviert eine Compilerwarnung oder Warnungen. Suchen Sie zum Deaktivieren einer Warnung nach ihrer Nummer in der Compilerausgabe, und setzen Sie sie in Anführungszeichen. Lassen Sie das Präfix „FS“ weg. Zum Deaktivieren von mehreren Warnnummern in derselben Zeile müssen Sie jede Nummer in Anführungszeichen setzen und jede Zeichenfolge durch ein Leerzeichen abtrennen. Beispiel:

`#nowarn "9" "40"`

Die Auswirkung der Deaktivierung einer Warnung gilt für die gesamte Datei, einschließlich der Teile der Datei, die der Direktive vorangestellt sind.

## <a name="conditional-compilation-directives"></a>Anweisungen für die bedingte Kompilierung

Code, der von einer dieser Direktiven deaktiviert wird, wird im Visual Studio Code-Editor abgeblendet angezeigt.

> [!NOTE]
> Das Verhalten der Anweisungen für die bedingte Kompilierung entspricht nicht dem in anderen Sprachen. Beispielsweise können Sie keine booleschen Ausdrücke mit Symbolen verwenden, zudem verfügen `true` und `false` über keine besondere Bedeutung. In der `if`-Anweisung von Ihnen verwendete Symbole müssen über die Befehlszeile oder in den Projekteinstellungen definiert werden. Es steht keine `define`-Präprozessoranweisung zur Verfügung.

Im folgenden Code wird die Verwendung der Anweisungen `#if`, `#else` und `#endif` veranschaulicht. In diesem Beispiel enthält der Code zwei Versionen der Definition von `function1`. Wenn `VERSION1` mithilfe der [-define-Compileroption](./compiler-options.md)definiert wird, wird der Code zwischen der- `#if` Direktive und der- `#else` Direktive aktiviert. Andernfalls wird der Code zwischen `#else` und `#endif` aktiviert.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7301.fs)]

Es gibt keine `#define`-Präprozessordirektive in F#. Sie müssen die Compileroption oder Projekteinstellungen verwenden, um die durch die `#if`-Direktive verwendeten Symbole zu definieren.

Direktiven für die bedingte Kompilierung können geschachtelt werden. Der Einzug ist für Präprozessordirektiven nicht entscheidend.

Sie können ein Symbol auch mit negieren `!` . In diesem Beispiel ist der Wert einer Zeichenfolge _nur beim_ Debuggen etwas:

```fsharp
#if !DEBUG
let str = "Not debugging!"
#else
let str = "Debugging!"
#endif
```

## <a name="line-directives"></a>Line-Anweisungen

Beim Erstellen meldet der Compiler Fehler im F#-Code durch das Referenzieren von Zeilennummern, in denen die jeweiligen Fehler auftreten. Diese Zeilennummern beginnen bei 1 für die erste Zeile in einer Datei. Wenn Sie jedoch F#-Quellcode aus einem anderen Tool generieren, sind die Zeilennummern im generierten Code im Allgemeinen nicht relevant, da die Fehler im generierten F#-Code höchstwahrscheinlich auf eine andere Quelle zurückgehen. Mit der `#line`-Direktive können Autoren von Tools, die F#-Quellcode generieren, Informationen über die ursprünglichen Zeilennummern und Quelldateien an den generierten F#-Code weitergeben.

Beim Verwenden der `#line`-Anweisung müssen Dateinamen in Anführungszeichen gesetzt werden. Sofern das verbatim-Token (`@`) nicht am Anfang der Zeichenfolge angezeigt wird, müssen Sie umgekehrte Schrägstriche durch die Verwendung von zwei (und nicht nur einem) umgekehrten Schrägstrichen escapen, um sie im Pfad zu verwenden. Im Folgenden finden Sie gültige Zeilentoken. In diesen Beispielen wird davon ausgegangen, dass die ursprüngliche `Script1`-Datei in einer automatisch generierten F#-Codedatei resultiert, wenn er über ein Tool ausgeführt wird, und dass der Code am Speicherort dieser Direktiven aus einigen Token in Zeile 25 in der Datei `Script1` generiert wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7303.fs)]

Diese Token geben an, dass der an diesem Speicherort generierte F#-Code aus einigen Konstrukten in oder in der Nähe der Zeile `25` in `Script1` abgeleitet ist.

## <a name="compiler-directives"></a>Compileranweisungen

Compileranweisungen ähneln Präprozessoranweisungen, da ihnen ein #-Zeichen vorangestellt ist. Anstelle jedoch durch den Präprozessor interpretiert zu werden, werden sie durch den Compiler interpretiert und verarbeitet.

Die folgende Tabelle enthält die Compilerdirektive, die in F# verfügbar ist.

|Anweisung|Beschreibung|
|---------|-----------|
|`#light` ["on" &#124; "Off"]|Aktiviert oder deaktiviert die einfache Syntax für die Kompatibilität mit anderen MK-Versionen. Standardmäßig ist die einfache Syntax aktiviert. Die ausführliche Syntax ist immer aktiviert. Daher können Sie die einfache und ausführliche Syntax verwenden. Die Anweisung `#light` an sich entspricht `#light "on"`. Beim Angeben von `#light "off"` müssen Sie die ausführliche Syntax für alle Sprachkonstrukte verwenden. Bei der in der Dokumentation für F# gezeigten Syntax wird davon ausgegangen, dass Sie die einfache Syntax verwenden. Weitere Informationen finden Sie unter ausführliche [Syntax](verbose-syntax.md).|

Informationen zu interpreterdirektiven (fsi.exe) finden Sie unter [interaktive Programmierung mit F #](../tools/fsharp-interactive/index.md).

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Compileroptionen](compiler-options.md)
