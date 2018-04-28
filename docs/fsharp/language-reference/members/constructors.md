---
title: Konstruktoren (F#)
description: Informationen Sie zum Definieren und Verwenden von Konstruktoren in f# erstellen und Initialisieren der Klasse und Struktur-Objekte.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: d9062ae747c37bdc14104658ad0ec7d11f5545f0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="constructors"></a>Konstruktoren

In diesem Thema wird beschrieben, wie zum Definieren und Verwenden von Konstruktoren zum Erstellen und Initialisieren von Objekten von Klasse und Struktur wird.


## <a name="construction-of-class-objects"></a>Konstruktion von Klassenobjekten
Objekte von Klassentypen verfügen über Konstruktoren. Es gibt zwei Arten von Konstruktoren. Eine ist der primäre Konstruktor, dessen Parameter in Klammern hinter dem Typnamen angezeigt werden. Geben Sie andere, optionale zusätzliche Konstruktoren, mit dem `new` Schlüsselwort. Alle diese zusätzlichen Konstruktoren müssen den primären Konstruktor aufrufen.

Enthält die primäre Konstruktor `let` und `do` Bindungen, die zu Beginn der Definition der Klasse angezeigt werden. Ein `let` Bindung deklariert, private Felder und Methoden der Klasse; eine `do` Bindung führt Code aus. Weitere Informationen zu `let` Bindungen in der Klasse, Konstruktoren, finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md). Weitere Informationen zu `do` Bindungen in Konstruktoren finden Sie unter [ `do` Bindungen in Klassen](do-bindings-in-classes.md).

Unabhängig davon, ob der Konstruktor aufgerufen werden soll, einen primären Konstruktor oder einem zusätzlichen Konstruktor ist, können Sie Objekte erstellen, indem Sie mit einem `new` Ausdruck, mit oder ohne das optionale `new` Schlüsselwort. Sie initialisieren die Objekte zusammen mit Konstruktorargumenten, entweder durch die Argumente in der Reihenfolge aufgelistet und durch Kommas getrennt und in Klammern oder mithilfe von benannten Argumenten und Werte in Klammern eingeschlossen. Sie können Eigenschaften auch für ein Objekt während der Erstellung des Objekts festlegen, mit dem Eigenschaftennamen und Zuweisen von Werten, genauso wie Sie mit dem Namen Konstruktorargumente.

Das folgende Codebeispiel veranschaulicht eine Klasse, die einen Konstruktor und verschiedene Methoden zum Erstellen von Objekten hat.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

Die Ausgabe lautet wie folgt.

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>Zur Erstellung von Strukturen
Strukturen, gelten alle Regeln von Klassen. Aus diesem Grund können Sie einen primären Konstruktor verfügen, und Sie können mit Weitere Konstruktoren bereitstellen `new`. Es ist jedoch ein wichtiger Unterschied zwischen Strukturen und Klassen: Strukturen können über einen Standardkonstruktor (d. h. eine ohne Argumente) verfügen, auch wenn kein primärer Konstruktor definiert ist. Der Standardkonstruktor initialisiert alle Felder auf den Standardwert für diesen Typ, in der Regel 0 (null) oder dessen Entsprechung. Konstruktoren, die für Strukturen definiert, benötigen mindestens ein Argument, damit sie nicht mit dem Standardkonstruktor in Konflikt stehen.

Strukturen müssen außerdem oft Felder, die mithilfe von erstellt werden die `val` Schlüsselwort Klassen können auch diese Felder haben. Strukturen und Klassen, die mit definierten Felder verfügen über die `val` -Schlüsselwort kann auch in Konstruktoren initialisiert werden zusätzliche mithilfe von Datensatz Ausdrücken wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

Weitere Informationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](explicit-fields-the-val-keyword.md).


## <a name="executing-side-effects-in-constructors"></a>Ausführen von Nebeneffekten in Konstruktoren
Führen Sie ein primärer Konstruktor in einer Klasse kann Code in eine `do` Bindung. Was geschieht, wenn Sie haben jedoch zum Ausführen von Code in einem zusätzlichen Konstruktor ohne eine `do` Bindung? Zu diesem Zweck verwenden Sie die `then` Schlüsselwort.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

Die Nebeneffekte des primären Konstruktor weiterhin ausgeführt werden. Daher ist die Ausgabe wie folgt.

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a>Selbstbezeichner in Konstruktoren
In anderen Mitgliedern geben Sie einen Namen für das aktuelle Objekt in der Definition jedes Elements. Sie können auch den Selbstbezeichner in der ersten Zeile der Klassendefinition platziert, mithilfe der `as` -Schlüsselwort direkt hinter die Konstruktorparametern. Das folgende Beispiel veranschaulicht diese Syntax.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

In weiteren Konstruktoren können Sie auch einen Selbstbezeichner verlegen definieren die `as` Klausel direkt hinter den Konstruktorparametern. Das folgende Beispiel veranschaulicht diese Syntax.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

Wenn Sie versuchen, ein Objekt zu verwenden, bevor sie vollständig definiert ist, können Probleme auftreten. Aus diesem Grund können Verwendungen von der Selbstbezeichner dazu führen, dass den Compiler eine Warnung ausgeben, und fügen Sie zusätzliche Überprüfungen durchgeführt, um sicherzustellen, dass der Member eines Objekts nicht zugegriffen werden, bevor das Objekt initialisiert wird. Verwenden Sie ausschließlich den Selbstbezeichner in die `do` Bindungen von den primären Konstruktor oder nach der `then` -Schlüsselwort in weiteren Konstruktoren.

Der Name des der Selbstbezeichner muss keine werden `this`. Es kann ein gültiger Bezeichner sein.


## <a name="assigning-values-to-properties-at-initialization"></a>Zuweisen von Werten zu Eigenschaften bei der Initialisierung
Sie können die Eigenschaften eines Klassenobjekts in Initialisierungscode Werte zuweisen, durch Anfügen einer Liste von Zuweisungen der Form `property = value` an die Argumentliste für einen Konstruktor. Dies wird im folgenden Codebeispiel gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Die folgende Version der obige Code veranschaulicht die Kombination der normalen Argumente, optionale Argumente und eigenschafteneinstellungen in einen Konstruktoraufruf enthalten.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a>Konstruktoren in einer geerbten Klasse
Wenn von einer Basisklasse erben, die über einen Konstruktor verfügt, müssen Sie die Argumente in der erben-Klausel angeben. Weitere Informationen finden Sie unter [Konstruktoren und Vererbung](../inheritance.md#constructors-and-inheritance).

## <a name="static-constructors-or-type-constructors"></a>Statische Konstruktoren oder Typkonstruktoren
Zusätzlich zum Angeben von Code zum Erstellen von Objekten, statische `let` und `do` Bindungen können in Klassentypen, die ausgeführt werden, bevor der Typ zuerst verwendet wird, für die Initialisierung auf Typebene erstellt werden. Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md) und [ `do` Bindungen in Klassen](do-bindings-in-classes.md).

## <a name="see-also"></a>Siehe auch
[Mitglieder](index.md)
