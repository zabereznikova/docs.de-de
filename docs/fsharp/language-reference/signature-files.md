---
title: Signaturdateien (f#)
description: Erfahren Sie, wie Sie mit F#-Signaturdateien, zum Speichern von Informationen zu den öffentlichen Signaturen einer Reihe von F#-Programmelementen, z. B. Typen, Namespaces und Modulen.
ms.date: 06/15/2018
ms.openlocfilehash: f0836aa7f638dc9e2b066b0f46bbb6c086347615
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45991232"
---
# <a name="signatures"></a>Signaturen

Eine Signaturdatei enthält Informationen zu den öffentlichen Signaturen einer Reihe von F#-Programmelementen wie Typen, Namespaces und Modulen. Mit ihr kann der Zugriff auf diese Programmelemente angegeben werden.

## <a name="remarks"></a>Hinweise

Für jede F#-Codedatei kann eine *Signaturdatei*vorhanden sein. Diese hat den gleichen Namen wie die Codedatei, aber die Erweiterung FSI statt FS. Signaturdateien können auch der Kompilierungsbefehlszeile hinzugefügt werden, wenn Sie die Befehlszeile direkt verwenden. Für die Unterscheidung zwischen Codedateien und Signaturdateien werden Codedateien manchmal als *Implementierungsdateien*bezeichnet. In einem Projekt sollte die Signaturdatei der zugeordneten Codedatei vorausgehen.

Eine Signaturdatei beschreibt die Namespaces, Module, Typen und Member in der entsprechenden Implementierungsdatei. Mithilfe der Informationen in einer Signaturdatei geben Sie an, auf welche Teile des Codes in der entsprechenden Implementierungsdatei von Code außerhalb der Implementierungsdatei zugegriffen werden kann und welche Teile interner Code der Implementierungsdatei sind. Die Namespaces, Module und Typen in der Signaturdatei müssen eine Teilmenge der Namespaces, Module und Typen in der Implementierungsdatei sein. Abgesehen von einigen weiter unten in diesem Thema genannten Ausnahmen werden die Sprachelemente, die nicht in der Signaturdatei aufgeführt sind, als private Elemente der Implementierungsdatei betrachtet. Wenn im Projekt oder der Befehlszeile keine Signaturdatei gefunden wird, wird Standardzugriff verwendet.

Weitere Informationen zum Standardzugriff finden Sie unter [Zugriffssteuerung](access-control.md).

In einer Signaturdatei werden die Definition der Typen und die Implementierungen der einzelnen Methoden oder Funktionen nicht wiederholt. Stattdessen verwenden Sie die Signatur für die jeweilige Methode bzw. Funktion, die als vollständige Spezifikation der von einem Modul- oder Namespacefragment implementierten Funktionalität fungiert. Die Syntax für eine Typsignatur ist mit der in abstrakten Methodendeklarationen in Schnittstellen und abstrakten Klassen verwendeten Syntax identisch. Sie wird auch von IntelliSense und dem F#-Interpreter "fsi.exe" dargestellt, wenn dieser eine ordnungsgemäß kompilierte Eingabe anzeigt.

Wenn die Informationen in der Typsignatur nicht ausreichen, um anzugeben, ob ein Typ versiegelt oder ein Schnittstellentyp ist, müssen Sie ein Attribut hinzufügen, das für den Compiler die Art des Typs angibt. Zu diesem Zweck verwendete Attribute werden in der folgenden Tabelle beschrieben.

|Attribut|Beschreibung|
|---------|-----------|
|`[<Sealed>]`|Für einen Typ, der über keine abstrakten Member verfügt oder nicht erweitert werden darf.|
|`[<Interface>]`|Für einen Typ, der eine Schnittstelle ist.|
Der Compiler erzeugt einen Fehler, wenn die Attribute in der Signatur und der Deklaration in der Implementierungsdatei nicht konsistent sind.

Erstellen Sie mithilfe des Schlüsselworts `val` eine Signatur für einen Wert oder einen Funktionswert. Mit dem Schlüsselwort `type` wird eine Typsignatur eingeführt.

Sie können mit der `--sig` -Compileroption eine Signaturdatei generieren. Im Allgemeinen werden FSI-Dateien nicht manuell geschrieben. Stattdessen generieren Sie FSI-Dateien mit dem Compiler, fügen sie ggf. dem Projekt hinzu und bearbeiten sie, indem Sie Methoden und Funktionen entfernen, auf die kein Zugriff möglich sein soll.

Für Typsignaturen gelten mehrere Regeln:

- Typabkürzungen in einer Implementierungsdatei dürfen keinem Typ ohne Abkürzung in einer Signaturdatei entsprechen.

- Datensätze und Unterscheidungs-Unions müssen entweder alle oder keine der zugehörigen Felder und Konstruktoren verfügbar machen, und die Reihenfolge in der Signatur muss mit der Reihenfolge in der Implementierungsdatei übereinstimmen. Klassen können einige, alle oder keine ihrer Felder und Methoden in der Signatur offenlegen.

- Klassen und Strukturen, die über Konstruktoren verfügen, müssen die Deklarationen ihrer Basisklassen (die `inherits` -Deklaration) verfügbar machen. Klassen und Strukturen, die über Konstruktoren verfügen, müssen außerdem alle ihre abstrakten Methoden und Schnittstellendeklarationen verfügbar machen.

- Schnittstellentypen müssen alle ihre Methoden und Schnittstellen offenlegen.

Für Wertsignaturen gelten folgende Regeln:

- Zugriffsmodifizierer (`public`, `internal`usw.) sowie der `inline` -Modifizierer und der `mutable` -Modifizierer in der Signatur müssen mit den entsprechenden Modifizierern in der Implementierung übereinstimmen.

- Die Anzahl der generischen Typparameter (implizit abgeleitet oder explizit deklariert) muss übereinstimmen, und die Typen und Typeinschränkungen in generischen Typparametern müssen übereinstimmen.

- Wenn das `Literal` -Attribut verwendet wird, muss es sowohl in der Signatur als auch in der Implementierung erscheinen, und für beide muss der gleiche Literalwert verwendet werden.

- Das Muster der Parameter (auch *Stelligkeit*) von Signaturen und Implementierungen muss konsistent sein.

- Wenn Parameternamen in einer Signaturdatei von der entsprechenden Implementierungsdatei unterscheiden zu können, wird der Name in der Signaturdatei stattdessen Dies verursacht möglicherweise Probleme beim Debuggen oder die profilerstellung verwendet werden. Wenn Sie über solche Nichtübereinstimmungen, Enable 3218 in Ihrer Projektdatei Warnung benachrichtigt werden möchten, oder beim Aufrufen des Compilers (finden Sie unter `--warnon` unter [Compileroptionen](compiler-options.md)).

Das folgende Codebeispiel veranschaulicht eine Signaturdatei, die Namespace-, Modul-, Funktionswert- und Typsignaturen sowie die entsprechenden Attribute enthält. Im Beispiel wird außerdem die entsprechende Implementierungsdatei gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9002.fs)]

Im folgenden Code wird die Implementierungsdatei veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9001.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Zugriffssteuerung](access-control.md)
- [Compileroptionen](compiler-options.md)
