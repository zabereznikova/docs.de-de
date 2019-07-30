---
title: Compileranweisungen
description: Erfahren Sie F# mehr über sprach Präprozessordirektiven, bedingte Kompilierungs Direktiven, Zeilen Anweisungen und Compilerdirektiven.
ms.date: 12/10/2018
ms.openlocfilehash: 16db2efb2fee2c2c5e94aa98eb0a13183a4e0e0b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630400"
---
# <a name="compiler-directives"></a>Compileranweisungen

In diesem Thema werden Prozessor- und Compileranweisungen beschrieben.

## <a name="preprocessor-directives"></a>Präprozessordirektiven

Einer Präprozessordirektive wird das #-Symbol vorangestellt und wird für sich genommen in einer Zeile angezeigt. Sie wird durch den Präprozessor interpretiert, der vom Compiler ausgeführt wird.

In der folgenden Tabelle werden die Präprozessordirektiven aufgelistet, die in F# verfügbar sind.

|Direktive|Beschreibung|
|---------|-----------|
|`#if`*Symbol*|Unterstützt die bedingte Kompilierung. Code im-Abschnitt, nachdem `#if` der eingefügt wurde, wenn das *Symbol* definiert ist. Das Symbol kann auch mit `!`negiert werden.|
|`#else`|Unterstützt die bedingte Kompilierung. Markiert einen einzubeziehenden Codeabschnitt, wenn das mit dem vorherigen verwendeten `#if` nicht definiert ist.|
|`#endif`|Unterstützt die bedingte Kompilierung. Markiert das Ende eines bedingten Codeabschnitts.|
|`#`Stimmen *int*,<br/>`#`Stimmen *int* *Zeichenfolge*,<br/>`#`Stimmen *int* *wörtliche Zeichenfolge*|Gibt die ursprüngliche Quellcodezeile und den Dateinamen für das Debuggen an. Diese Funktion wird für Tools bereitgestellt, die F#-Quellcode generieren.|
|`#nowarn`*warningCode*|Deaktiviert eine Compilerwarnung oder Warnungen. Suchen Sie zum Deaktivieren einer Warnung nach ihrer Nummer in der Compilerausgabe, und setzen Sie sie in Anführungszeichen. Lassen Sie das Präfix „FS“ weg. Zum Deaktivieren von mehreren Warnnummern in derselben Zeile müssen Sie jede Nummer in Anführungszeichen setzen und jede Zeichenfolge durch ein Leerzeichen abtrennen. Zum Beispiel:

`#nowarn "9" "40"`

Die Auswirkung der Deaktivierung einer Warnung gilt für die gesamte Datei, einschließlich der Teile der Datei, die der Direktive vorangestellt sind.

## <a name="conditional-compilation-directives"></a>Anweisungen für die bedingte Kompilierung

Code, der von einer dieser Direktiven deaktiviert wird, wird im Visual Studio Code-Editor abgeblendet angezeigt.

> [!NOTE]
> Das Verhalten der Anweisungen für die bedingte Kompilierung entspricht nicht dem in anderen Sprachen. Beispielsweise können Sie keine booleschen Ausdrücke mit Symbolen verwenden, zudem verfügen `true` und `false` über keine besondere Bedeutung. In der `if`-Direktive von Ihnen verwendete Symbole müssen über die Befehlszeile oder in den Projekteinstellungen definiert werden. Es steht keine `define`-Präprozessordirektive zur Verfügung.

Im folgenden Code wird die Verwendung der Direktiven `#if`, `#else` und `#endif` veranschaulicht. In diesem Beispiel enthält der Code zwei Versionen der Definition von `function1`. Wenn `VERSION1` mithilfe der [-define-Compileroption](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04)definiert wird, wird der Code `#if` zwischen der- `#else` Direktive und der-Direktive aktiviert. Andernfalls wird der Code zwischen `#else` und `#endif` aktiviert.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7301.fs)]

Es gibt keine `#define`-Präprozessoranweisung in F#. Sie müssen die Compileroption oder Projekteinstellungen verwenden, um die durch die `#if`-Direktive verwendeten Symbole zu definieren.

Direktiven für die bedingte Kompilierung können geschachtelt werden. Der Einzug ist für Präprozessordirektiven nicht entscheidend.

Sie können ein Symbol auch mit `!`negieren. In diesem Beispiel ist der Wert einer Zeichenfolge _nur beim_ Debuggen etwas:

```fsharp
#if !DEBUG
let str = "Not debugging!"
#else
let str = "Debugging!"
#endif
```

## <a name="line-directives"></a>Line-Direktiven

Beim Erstellen meldet der Compiler Fehler im F#-Code durch das Referenzieren von Zeilennummern, in denen die jeweiligen Fehler auftreten. Diese Zeilennummern beginnen bei 1 für die erste Zeile in einer Datei. Wenn Sie jedoch F#-Quellcode aus einem anderen Tool generieren, sind die Zeilennummern im generierten Code im Allgemeinen nicht relevant, da die Fehler im generierten F#-Code höchstwahrscheinlich auf eine andere Quelle zurückgehen. Mit der `#line`-Direktive können Autoren von Tools, die F#-Quellcode generieren, Informationen über die ursprünglichen Zeilennummern und Quelldateien an den generierten F#-Code weitergeben.

Beim Verwenden der `#line`-Direktive müssen Dateinamen in Anführungszeichen gesetzt werden. Sofern das verbatim-Token (`@`) nicht am Anfang der Zeichenfolge angezeigt wird, müssen Sie umgekehrte Schrägstriche durch die Verwendung von zwei (und nicht nur einem) umgekehrten Schrägstrichen escapen, um sie im Pfad zu verwenden. Im Folgenden finden Sie gültige Zeilentoken. In diesen Beispielen wird davon ausgegangen, dass die ursprüngliche `Script1`-Datei in einer automatisch generierten F#-Codedatei resultiert, wenn er über ein Tool ausgeführt wird, und dass der Code am Speicherort dieser Anweisungen aus einigen Token in Zeile 25 in der Datei `Script1` generiert wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7303.fs)]

Diese Token geben an, dass der an diesem Speicherort generierte F#-Code aus einigen Konstrukten in oder in der Nähe der Zeile `25` in `Script1` abgeleitet ist.

## <a name="compiler-directives"></a>Compileranweisungen

Compilerdirektiven ähneln Präprozessordirektiven, da ihnen ein #-Zeichen vorangestellt ist. Anstelle jedoch durch den Präprozessor interpretiert zu werden, werden sie durch den Compiler interpretiert und verarbeitet.

Die folgende Tabelle enthält die Compilerdirektive, die in F# verfügbar ist.

|Direktive|Beschreibung|
|---------|-----------|
|`#light` ["on"&#124;"off"]|Aktiviert oder deaktiviert die einfache Syntax für die Kompatibilität mit anderen MK-Versionen. Standardmäßig ist die einfache Syntax aktiviert. Die ausführliche Syntax ist immer aktiviert. Daher können Sie die einfache und ausführliche Syntax verwenden. Die Direktive `#light` an sich entspricht `#light "on"`. Beim Angeben von `#light "off"` müssen Sie die ausführliche Syntax für alle Sprachkonstrukte verwenden. Bei der in der Dokumentation für F# gezeigten Syntax wird davon ausgegangen, dass Sie die einfache Syntax verwenden. Weitere Informationen finden Sie unter ausführliche [Syntax](verbose-syntax.md).|

Interpreter (fsi.exe)-Anweisungen finden Sie unter [Interaktive Programmierung mit F#](../tutorials/fsharp-interactive/index.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Compileroptionen](compiler-options.md)
