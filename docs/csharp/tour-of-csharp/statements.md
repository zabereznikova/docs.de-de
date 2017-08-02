---
title: "C#-Anweisungen – Überblick über C#"
description: Sie erstellen die Aktionen eines C#-Programms mit Anweisungen.
keywords: .NET, Csharp, Anweisungen, Syntax
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 99ec2489daf89926da9b8c4e148965412826a8a6
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="statements"></a>Anweisungen

Die Aktionen eines Programms werden mit *Anweisungen* ausgedrückt. C# unterstützt verschiedene Arten von Anweisungen, von denen ein Teil als eingebettete Anweisungen definiert ist.

Ein *Block* ermöglicht, mehrere Anweisungen in Kontexten zu schreiben, in denen eine einzelne Anweisung zulässig ist. Ein Block besteht aus einer Liste von Anweisungen, die zwischen den Trennzeichen `{` und `}` geschrieben sind.

*Deklarationsanweisungen* werden verwendet, um lokale Variablen und Konstanten deklarieren.

*Ausdrucksanweisungen* werden zum Auswerten von Ausdrücken verwendet. Ausdrücke, die als Anweisungen verwendet werden können, enthalten Methodenaufrufe, Objektzuordnungen mit dem `new`-Operator, Zuweisungen mit `=` und den Verbundzuweisungsoperatoren, Inkrementier- und Dekrementiervorgänge unter Verwendung des `++`- und `--`-Operators und `await`-Ausdrücke.

*Auswahlanweisungen* werden verwendet, um eine Anzahl von möglichen Anweisungen für die Ausführung anhand des Werts eines Ausdrucks auszuwählen. Zu dieser Gruppe gehören die `if`- und `switch`-Anweisungen.

*Iterationsanweisungen* werden verwendet, um eine eingebettete Anweisung wiederholt auszuführen. Zu dieser Gruppe gehören die `while`-, `do`-, `for`- und `foreach`-Anweisungen.

*Sprunganweisungen* werden verwendet, um die Steuerung zu übertragen. Zu dieser Gruppe gehören die `break`-, `continue`-, `goto`-, `throw`-, `return`- und `yield`-Anweisungen.

Mit der `try`... `catch`-Anweisung werden Ausnahmen abgefangen, die während der Ausführung eines Blocks auftreten, und mit der `try`... `finally`-Anweisung wird Finalisierungscode angegeben, der immer ausgeführt wird, unabhängig davon, ob eine Ausnahme aufgetreten ist oder nicht.

Mit den Anweisungen `checked` und `unchecked` wird der Überlaufüberprüfungs-Kontext für arithmetische Operationen für Ganzzahltypen und Konvertierungen gesteuert.

Die `lock`-Anweisung wird verwendet, um die Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt abzurufen, eine Anweisung auszuführen und die Sperre aufzuheben.

Die `using`-Anweisung wird verwendet, um eine Ressource abzurufen, eine Anweisung auszuführen und dann diese Ressource zu verwerfen.

Im Folgenden werden die Arten von Anweisungen aufgelistet, die verwendet werden können, und für jede ein Beispiel aufgeführt.

* Deklaration lokaler Variablen:

 [!code-csharp[Deklarationen](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]

* Deklaration lokaler Konstanten:

 [!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]

* Ausdrucksanweisung:

 [!code-csharp[Ausdrücke](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]

* `if`-Anweisung:

 [!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]

* `switch`-Anweisung:

 [!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]

* `while`-Anweisung:

 [!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]

* `do`-Anweisung:

 [!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]

* `for`-Anweisung:

 [!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]

* `foreach`-Anweisung:

 [!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]

* `break`-Anweisung:

 [!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]

* `continue`-Anweisung:

 [!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]

* `goto`-Anweisung:

 [!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]

* `return`-Anweisung:

 [!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]

* `yield`-Anweisung:

 [!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]

* `throw`-Anweisungen und `try`-Anweisungen:

 [!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]

* `checked`- und `unchecked`-Anweisungen:

 [!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]

* `lock`-Anweisung:

 [!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]

* `using`-Anweisung:

 [!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]

>[!div class="step-by-step"]
[Zurück](expressions.md)
[Weiter](classes-and-objects.md)

