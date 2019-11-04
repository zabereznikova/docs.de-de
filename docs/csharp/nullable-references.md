---
title: Nullwerte zulassende Verweistypen
description: Dieser Artikel bietet eine Übersicht der Nullable-Verweistypen, die in C# 8.0 hinzugefügt wurden. Sie erfahren, wie das Feature bei neuen und vorhandenen Projekten vor Nullverweisausnahmen schützt.
ms.date: 02/19/2019
ms.openlocfilehash: 2c2148b3ae50ce6c00e523390ea02686d9106b8b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846757"
---
# <a name="nullable-reference-types"></a>Nullwerte zulassende Verweistypen

Mit den in C# 8.0 eingeführten **Nullable-Verweistypen** und **Nicht-Nullable-Verweistypen** können Sie wichtige Anweisungen zu den Eigenschaften für Verweistypvariablen erstellen:

- **Ein Verweis darf nicht NULL sein**. Wenn Variablen nicht NULL sein dürfen, erzwingt der Compiler Regeln, die sicherstellen, dass das Dereferenzieren dieser Variablen sicher ist, ohne zuerst zu überprüfen, dass sie nicht NULL sind:
  - Die Variable muss mit einem Wert ungleich NULL initialisiert werden.
  - Der Variablen kann nie der Wert `null` zugewiesen werden.
- **Ein Verweis darf NULL sein**. Wenn Variablen NULL sein dürfen, erzwingt der Compiler verschiedene Regeln, um sicherzustellen, dass Sie richtig auf einen Nullverweis überprüft haben:
  - Die Variable kann nur dereferenziert werden, wenn der Compiler garantieren kann, dass der Wert nicht NULL ist.
  - Diese Variablen können mit dem Standardwert `null` initialisiert und in anderem Code dem Wert `null` zugewiesen werden.

Dieses neue Feature bietet große Vorteile hinsichtlich der Verarbeitung von Verweisvariablen in früheren Versionen von C#, bei denen die Entwurfsabsicht nicht über die Variablendeklaration bestimmt werden konnte. Der Compiler bot keinen Schutz gegen Nullverweisausnahmen für Verweistypen:

- **Ein Verweis kann NULL sein**. Wenn ein Verweistyp mit NULL initialisiert oder später NULL zugewiesen wird, werden keine Warnungen ausgegeben.
- **Es wird angenommen, dass ein Verweis nicht NULL ist**. Der Compiler gibt keine Warnungen aus, wenn Verweistypen dereferenziert werden. (Bei Nullable-Verweisen gibt der Compiler Warnungen aus, sobald Sie eine Variable dereferenzieren, die möglicherweise NULL ist).

Durch das Hinzufügen von Nullable-Verweistypen können Sie Ihre Absicht klarer deklarieren. Der `null`-Wert ist die richtige Wahl, um darzustellen, dass eine Variable auf keinen Wert verweist. Verwenden Sie dieses Feature nicht dazu, alle `null`-Werte aus Ihrem Code zu entfernen. Stattdessen sollten Sie Ihre Absicht gegenüber dem Compiler und anderen Entwicklern deklarieren, die Ihren Code lesen. Indem Sie Ihre Absicht deklarieren, werden Sie vom Compiler informiert, sobald Sie Code schreiben, der dieser Absicht widerspricht.

Ein **Nullable-Verweistyp** wird mithilfe der gleichen Syntax wie [Nullable-Werttypen](programming-guide/nullable-types/index.md) aufgeführt: Ein `?` wird an den Variablentyp angefügt. Beispielsweise stellt die folgende Variablendeklaration eine Nullable-Zeichenfolgenvariable, `name`, dar:

```csharp
string? name;
```

Bei jeder Variable, bei der `?` nicht an den Typnamen angefügt ist, handelt es sich um einen **Nicht-Nullable-Verweistyp**. Dies umfasst alle Verweistypvariablen in vorhandenem Code, wenn Sie dieses Feature aktiviert haben.

Der Compiler verwendet die statische Analyse, um zu bestimmen, ob ein Nullable-Verweis nicht NULL ist. Der Compiler warnt Sie, falls Sie einen Nullable-Verweis dereferenzieren, wenn dieser möglicherweise NULL ist. Sie können dieses Verhalten überschreiben, indem Sie den [NULL-toleranten Operator](language-reference/operators/null-forgiving.md) (`!`) gefolgt von einem Variablennamen verwenden. Wenn Sie beispielsweise wissen, dass die Variable `name` nicht NULL ist, der Compiler aber eine Warnung ausgibt, können Sie folgenden Code schreiben, um die Compileranalyse zu überschreiben:

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a>NULL-Zulässigkeit von Typen

Jeder beliebige Verweistyp kann über eine von vier *NULL-Zulässigkeiten* verfügen, die beschreibt, wann Warnungen ausgegeben werden:

- *Nonnullable* (Nicht-Nullable): Variablen dieses Typs kann NULL nicht zugewiesen werden. Variablen dieses Typs müssen vor der Dereferenzierung nicht auf NULL überprüft werden.
- *Nullable*: Variablen dieses Typs kann NULL zugewiesen werden. Wenn Variablen dieses Typs dereferenziert werden, ohne dass zuvor auf `null` überprüft wurde, wird eine Warnung ausgegeben.
- *Oblivious* (Nichtbeachtend): Dies ist der Zustand vor C# 8.0. Variablen dieses Typs können ohne Warnungen dereferenziert oder zugewiesen werden.
- *Unknown* (Unbekannt): Diese NULL-Zulässigkeit ist im Allgemeinen für Typparameter gedacht, bei denen der Compiler von Einschränkungen nicht erfährt, dass der Typ *nullable* oder *nicht-nullable* sein muss.

Die NULL-Zulässigkeit eines Typs in einer Variablendeklaration wird durch den *Nullable-Kontext* gesteuert, in der die Variable deklariert wird.

## <a name="nullable-contexts"></a>Nullable-Kontexte

Nullable-Kontexte ermöglichen eine differenzierte Steuerung der Interpretation von Verweistypvariablen durch den Compiler. Der **Nullable-Anmerkungskontext** jeder beliebigen Quellzeile ist aktiviert oder deaktiviert. Der Compiler vor C# 8.0 hat Ihren gesamten Code in einem deaktivierten Nullable-Kontext kompiliert: Jeder Verweistyp kann NULL sein. Der **Kontext „nullable warnings“** (Nullable-Warnungen) kann ebenfalls aktiviert oder deaktiviert sein. Der Nullable-Warnungskontext gibt die vom Compiler generierten Warnungen mithilfe der Flussanalyse an.

Der Nullable-Anmerkungskontext und der Nullable-Warnungskontext können für ein Projekt festgelegt werden, indem Sie das `Nullable`-Element in Ihrer *CSPROJ*-Datei verwenden. Dieses Element konfiguriert, wie der Compiler die NULL-Zulässigkeit von Typen interpretiert und welche Warnungen generiert werden. Gültige Einstellungen sind folgende:

- `enable`: Der Nullable-Anmerkungskontext ist **enabled** (aktiviert). Der Nullable-Warnungskontext ist **enabled** (aktiviert).
  - Variablen eines Verweistyps wie `string` sind „non-nullable“ (nicht-nullable).  Alle NULL-Zulässigkeitswarnungen sind „enabled“ (aktiviert).
- `warnings`: Der Nullable-Anmerkungskontext ist **disabled** (deaktiviert). Der Nullable-Warnungskontext ist **enabled** (aktiviert).
  - Variablen eines Verweistyps sind „oblivious“ (nichtbeachtend). Alle NULL-Zulässigkeitswarnungen sind „enabled“ (aktiviert).
- `annotations`: Der Nullable-Anmerkungskontext ist **enabled** (aktiviert). Der Nullable-Warnungskontext ist **disabled** (deaktiviert).
  - Variablen eines Verweistyps wie „string“ sind „non-nullable“ (nicht-nullable). Alle NULL-Zulässigkeitswarnungen sind „disabled“ (deaktiviert).
- `disable`: Der Nullable-Anmerkungskontext ist **disabled** (deaktiviert). Der Nullable-Warnungskontext ist **disabled** (deaktiviert).
  - Variablen eines Verweistyps sind „oblivious“ (nichtbeachtend), wie in früheren Versionen von C#. Alle NULL-Zulässigkeitswarnungen sind „disabled“ (deaktiviert).

Sie können auch Anweisungen verwenden, um diese Kontexte überall in Ihrem Projekt festzulegen:

- `#nullable enable`: Legt den Nullable-Anmerkungskontext und den Nullable-Warnungskontext auf **enabled** (aktiviert) fest.
- `#nullable disable`: Legt den Nullable-Anmerkungskontext und den Nullable-Warnungskontext auf **disabled** (deaktiviert) fest.
- `#nullable restore`: Stellt die Projekteinstellungen für den Nullable-Anmerkungskontext und den Nullable-Warnungskontext wieder her.
- `#nullable disable warnings`: Legt den Nullable-Warnungskontext auf **disabled** (deaktiviert) fest.
- `#nullable enable warnings`: Legt den Nullable-Warnungskontext auf **enabled** (aktiviert) fest.
- `#nullable restore warnings`: Stellt die Projekteinstellungen für den Nullable-Warnungskontext wieder her.
- `#nullable disable annotations`: Legt den Nullable-Anmerkungskontext auf **disabled** (deaktiviert) fest.
- `#nullable enable annotations`: Legt den Nullable-Anmerkungskontext auf **enabled** (aktiviert) fest.
- `#nullable restore annotations`: Stellt die Projekteinstellungen für den Anmerkungswarnungskontext wieder her.

Standardmäßig sind die Nullable-Anmerkungs- und -Warnungskontexte **deaktiviert**. Dies bedeutet, dass Ihr vorhandener Code ohne Änderungen und ohne Warnungen kompiliert wird.

## <a name="nullable-annotation-context"></a>Nullable-Anmerkungskontext

Der Compiler verwendet die folgenden Regeln in einem „disabled“-Nullable-Anmerkungskontext:

- Sie können keine Nullable-Verweise in einem „disabled“-Kontext deklarieren.
- Alle Verweisvariablen können NULL zugewiesen werden.
- Wenn eine Variable eines Verweistyps dereferenziert wird, werden keine Warnungen generiert.
- Der NULL-tolerante Operator kann in einem „disabled“-Kontext nicht verwendet werden.

Das Verhalten ist wie bei früheren Versionen von C#.

Der Compiler verwendet die folgenden Regeln in einem „enabled“-Nullable-Anmerkungskontext:

- Jede Variable eines Verweistyps ist ein **Nicht-Nullable-Verweis**.
- Jeder Nicht-Nullable-Verweis kann sicher dereferenziert werden.
- Jeder Nullable-Verweistyp (aufgeführt durch `?` nach dem Typ in der Variablendeklaration) kann NULL sein. Durch die statische Analyse wird bestimmt, ob der Wert ungleich NULL ist, wenn er dereferenziert wird. Ist dies nicht der Fall, werden Sie vom Compiler gewarnt.
- Sie können den NULL-toleranten Operator verwenden, um zu deklarieren, dass ein Nullable-Verweis nicht NULL ist.

In einem „enabled“-Nullable-Anmerkungskontext deklariert das an einen Verweistyp angefügte Zeichen `?` einen **Nullable-Verweistyp**. Der **NULL-tolerante Operator** (`!`) kann an einen Ausdruck angefügt werden, um zu deklarieren, dass der Ausdruck nicht NULL ist.

## <a name="nullable-warning-context"></a>Nullable-Warnungskontext

Der Nullable-Warnungskontext unterscheidet sich vom Nullable-Anmerkungskontext. Warnungen können selbst dann aktiviert sein, wenn die neuen Anmerkungen deaktiviert sind. Der Compiler bestimmt mithilfe der statischen Flussanalyse den **NULL-Zustand** eines Verweises. Der NULL-Zustand ist entweder **not null** (nicht NULL) oder **maybe null** (vielleicht NULL), wenn der *Nullable-Warnungskontext* nicht **disabled** (deaktiviert) ist. Wenn Sie einen Verweis dereferenzieren, wenn der Compiler bestimmt hat, dass dessen Zustand **maybe null** (vielleicht NULL) lautet, löst der Compiler eine Warnung aus. Der Status eines Verweises ist **maybe null** (vielleicht NULL), sofern der Compiler nicht eine der folgenden beiden Bedingungen bestimmen kann:

1. Die Variable wurde definitiv einem Wert ungleich NULL zugewiesen.
1. Die Variable oder der Ausdruck wurde vor der Dereferenzierung auf NULL überprüft.

Der Compiler generiert Warnungen, wenn Sie eine Variable oder einen Ausdruck im Zustand **maybe null** (vielleicht NULL) dereferenzieren und der Nullable-Warnungskontext aktiviert ist. Darüber hinaus werden Warnungen generiert, wenn eine Variable oder ein Ausdruck im Zustand **maybe null** (vielleicht NULL) einem Nicht-Nullable-Verweistyp zugewiesen wird und der Nullable-Anmerkungskontext aktiviert ist.

## <a name="see-also"></a>Siehe auch

- [Entwurf der Spezifikation für Nullable-Verweistypen](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md)
- [Tutorial: Besseres Ausdrücken Ihrer Entwurfsabsicht mit Verweistypen, die NULL-Werte zulassen und nicht zulassen](tutorials/nullable-reference-types.md)
- [Tutorial: Migrieren vorhandenen Codes mit Verweistypen, die NULL-Werte zulassen](tutorials/upgrade-to-nullable-references.md)
