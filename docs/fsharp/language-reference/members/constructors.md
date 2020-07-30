---
title: Konstruktoren
description: 'Erfahren Sie, wie Sie Konstruktoren in F # definieren und verwenden, um Klassen-und Struktur Objekte zu erstellen und zu initialisieren.'
ms.date: 05/16/2016
ms.openlocfilehash: be8fc3f1d82a9a7c778a6d094139f14150a28813
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303438"
---
# <a name="constructors"></a>Konstruktoren

In diesem Artikel wird beschrieben, wie Konstruktoren definiert und verwendet werden, um Klassen-und Struktur Objekte zu erstellen und zu initialisieren.

## <a name="construction-of-class-objects"></a>Konstruktion von Klassen Objekten

Objekte von Klassentypen verfügen über Konstruktoren. Es gibt zwei Arten von Konstruktoren. Eine ist der primäre Konstruktor, dessen Parameter in Klammern direkt nach dem Typnamen angezeigt werden. Mithilfe des-Schlüssel Worts geben Sie weitere optionale zusätzliche Konstruktoren an `new` . Alle diese zusätzlichen Konstruktoren müssen den primären Konstruktor aufzurufen.

Der primäre Konstruktor enthält `let` -und- `do` Bindungen, die am Anfang der Klassendefinition angezeigt werden. Eine `let` Bindung deklariert private Felder und Methoden der-Klasse. eine `do` Bindung führt Code aus. Weitere Informationen zu `let` Bindungen in Klassenkonstruktoren finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md). Weitere Informationen zu `do` Bindungen in Konstruktoren finden Sie unter [ `do` Bindungen in Klassen](do-bindings-in-classes.md).

Unabhängig davon, ob der Konstruktor, den Sie aufzurufen, ein primärer Konstruktor oder ein zusätzlicher Konstruktor ist, können Sie-Objekte erstellen, indem Sie einen- `new` Ausdruck mit oder ohne das optionale- `new` Schlüsselwort verwenden. Sie initialisieren die Objekte mit Konstruktorargumenten, indem Sie entweder die Argumente in der Reihenfolge auflisten und durch Kommas getrennt und in Klammern eingeschlossen sind, oder indem Sie benannte Argumente und Werte in Klammern verwenden. Sie können auch Eigenschaften für ein Objekt während der Erstellung des Objekts festlegen, indem Sie die Eigenschaftsnamen verwenden und Werte zuweisen, genauso wie Sie benannte Konstruktorargumente verwenden.

Der folgende Code veranschaulicht eine-Klasse, die über einen Konstruktor und verschiedene Methoden zum Erstellen von-Objekten verfügt:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

Die Ausgabe lautet wie folgt:

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>Konstruktion von Strukturen

Strukturen befolgen alle Regeln der Klassen. Daher können Sie über einen primären Konstruktor verfügen, und Sie können zusätzliche Konstruktoren mithilfe von bereitstellen `new` . Es gibt jedoch einen wichtigen Unterschied zwischen Strukturen und Klassen: Strukturen können über einen Parameter losen Konstruktor (d. h. einen ohne Argumente) verfügen, auch wenn kein primärer Konstruktor definiert ist. Der Parameter lose Konstruktor initialisiert alle Felder mit dem Standardwert für diesen Typ, normalerweise 0 (null) oder dessen Entsprechung. Alle Konstruktoren, die Sie für Strukturen definieren, müssen mindestens ein Argument aufweisen, damit Sie nicht mit dem Parameter losen Konstruktor in Konflikt stehen.

Außerdem verfügen Strukturen häufig über Felder, die mithilfe des `val` Schlüssel Worts erstellt werden. Klassen können auch über diese Felder verfügen. Strukturen und Klassen, die mithilfe des-Schlüssel Worts definierte Felder haben `val` , können auch in zusätzlichen Konstruktoren mithilfe von Daten Satz Ausdrücken initialisiert werden, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

Weitere Informationen finden Sie unter [Explizite Felder: das- `val` Schlüsselwort](explicit-fields-the-val-keyword.md).

## <a name="executing-side-effects-in-constructors"></a>Ausführen von Nebeneffekten in Konstruktoren

Ein primärer Konstruktor in einer Klasse kann Code in einer `do` Bindung ausführen. Was geschieht jedoch, wenn Sie Code in einem zusätzlichen Konstruktor ohne Bindung ausführen müssen `do` ? Verwenden Sie hierzu das- `then` Schlüsselwort.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

Die Nebeneffekte des primären Konstruktors werden weiterhin ausgeführt. Aus diesem Grund lautet die Ausgabe wie folgt:

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

Der Grund `then` , warum anstelle eines anderen erforderlich ist `do` , besteht darin, dass das `do` -Schlüsselwort die Standardbedeutung eines `unit` -Rückgabe Ausdrucks begrenzt, wenn er im Text eines zusätzlichen Konstruktors vorhanden ist. Dies hat nur eine besondere Bedeutung im Kontext von primären Konstruktoren.

## <a name="self-identifiers-in-constructors"></a>Self-IDs in Konstruktoren

In anderen Membern geben Sie einen Namen für das aktuelle Objekt in der Definition der einzelnen Member an. Sie können auch den selbst Bezeichner in die erste Zeile der Klassendefinition einfügen, indem Sie das `as` Schlüsselwort direkt nach den Konstruktorparametern verwenden. Diese Syntax wird im folgenden Beispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

In zusätzlichen Konstruktoren können Sie auch einen selbst Bezeichner definieren, indem Sie die- `as` Klausel direkt nach den Konstruktorparametern platzieren. Das folgende Beispiel veranschaulicht diese Syntax:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

Probleme können auftreten, wenn Sie versuchen, ein Objekt zu verwenden, bevor es vollständig definiert ist. Daher kann die Verwendung des Self-Bezeichners bewirken, dass der Compiler eine Warnung ausgibt und zusätzliche Überprüfungen einfügt, um sicherzustellen, dass auf die Member eines Objekts nicht zugegriffen wird, bevor das Objekt initialisiert wird. Sie sollten den Self-Identifier nur in den `do` Bindungen des primären Konstruktors oder nach dem- `then` Schlüsselwort in zusätzlichen Konstruktoren verwenden.

Der Name des selbst Bezeichners muss nicht sein `this` . Dies kann ein beliebiger gültiger Bezeichner sein.

## <a name="assigning-values-to-properties-at-initialization"></a>Zuweisen von Werten zu Eigenschaften bei der Initialisierung

Sie können den Eigenschaften eines Klassen Objekts im Initialisierungs Code Werte zuweisen, indem Sie eine Liste der Zuweisungen des Formulars `property = value` an die Argumentliste für einen Konstruktor anhängen. Dies wird im folgenden Codebeispiel veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

In der folgenden Version des vorherigen Codes wird die Kombination aus normalen Argumenten, optionalen Argumenten und Eigenschafts Einstellungen in einem konstruktorbefehl veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a>Konstruktoren in der geerbten Klasse

Beim Erben von einer Basisklasse, die über einen Konstruktor verfügt, müssen Sie die Argumente in der Vererbungs Klausel angeben. Weitere Informationen finden Sie unter [Konstruktoren und Vererbung](../inheritance.md#constructors-and-inheritance).

## <a name="static-constructors-or-type-constructors"></a>Statische Konstruktoren oder Typkonstruktoren

Neben dem Angeben von Code zum Erstellen von Objekten `let` können statische-und- `do` Bindungen in Klassentypen erstellt werden, die ausgeführt werden, bevor der-Typ zum ersten Mal für die Initialisierung auf Typebene verwendet wird. Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md) und [ `do` Bindungen in Klassen](do-bindings-in-classes.md).

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
