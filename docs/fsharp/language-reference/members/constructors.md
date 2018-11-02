---
title: Konstruktoren (F#)
description: Informationen Sie zum Definieren und Verwenden von Konstruktoren in f# zu erstellen und initialisieren die Klasse und Struktur von Objekten.
ms.date: 05/16/2016
ms.openlocfilehash: ff2463f890034cce0bbaa85d9a5c93e50427cd03
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45743916"
---
# <a name="constructors"></a>Konstruktoren

Dieses Thema beschreibt das Definieren und Verwenden von Konstruktoren zum Erstellen und Initialisieren von Objekten für Klasse und Struktur.

## <a name="construction-of-class-objects"></a>Erstellung von Klassenobjekten

Objekte von Klassentypen verfügen über Konstruktoren. Es gibt zwei Arten von Konstruktoren. Eine ist der primäre Konstruktor, dessen Parameter in Klammern direkt nach dem Typnamen angezeigt werden. Sie andere, optionale zusätzliche Konstruktoren angeben, indem die `new` Schlüsselwort. Alle diese zusätzlichen Konstruktoren müssen den primären Konstruktor aufrufen.

Der primäre Konstruktor enthält `let` und `do` Bindungen, die zu Beginn der Definition der Klasse angezeigt werden. Ein `let` Bindung deklariert die privaten Felder und Methoden der Klasse; eine `do` Bindung führt Code aus. Weitere Informationen zu `let` Bindungen in der Klasse, Konstruktoren, finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md). Weitere Informationen zu `do` Bindungen in Konstruktoren finden Sie unter [ `do` Bindungen in Klassen](do-bindings-in-classes.md).

Unabhängig davon, ob der Konstruktor aufgerufen werden soll, einen primären Konstruktor oder einen zusätzlichen Konstruktor ist, können Sie Objekte erstellen, mit einem `new` Ausdruck, mit oder ohne die optionale `new` Schlüsselwort. Sie initialisieren Ihre Objekte zusammen mit Konstruktorargumente, entweder durch Auflisten der Argumente in der Reihenfolge und durch Kommas getrennt und eingeschlossen in Klammern oder mithilfe von benannten Argumente und Werte in Klammern angegeben. Sie können Eigenschaften auch für ein Objekt während der Erstellung des Objekts festlegen, mit die Eigenschaftennamen und Zuweisen von Werten, genauso wie Sie mit dem Namen Konstruktorargumente.

Der folgende Code veranschaulicht eine Klasse mit einem Konstruktor und die verschiedenen Möglichkeiten zum Erstellen von Objekten.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

Die Ausgabe lautet wie folgt.

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>Erstellung von Strukturen

Strukturen führen Sie alle Regeln der Klassen. Aus diesem Grund können Sie einen primären Konstruktor verfügen, und Sie können zusätzliche Konstruktoren angeben, mit `new`. Es ist jedoch ein wichtiger Unterschied zwischen Strukturen und Klassen: Strukturen können über einen Standardkonstruktor (d. h. eine ohne Argumente) verfügen, auch wenn keine primärer Konstruktor definiert ist. Der Standardkonstruktor initialisiert alle Felder auf den Standardwert für diesen Typ, in der Regel 0 (null) oder dessen Entsprechung. Keine Konstruktoren, die Sie für die Strukturen zu definieren, müssen mindestens ein Argument, damit sie nicht mit dem Standardkonstruktor in Konflikt stehen.

Strukturen enthalten darüber hinaus oft Felder, die mit der `val` Schlüsselwort Klassen können auch über diese Felder verfügen. Strukturen und Klassen, die mithilfe von definierten Felder den `val` Schlüsselwort kann auch in Konstruktoren initialisiert werden zusätzliche Datensatzausdrücken, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

Weitere Informationen finden Sie unter [explizite Felder: das `val` Schlüsselwort](explicit-fields-the-val-keyword.md).

## <a name="executing-side-effects-in-constructors"></a>Ausführen von Nebeneffekten in Konstruktoren

Führen Sie ein primärer Konstruktor in einer Klasse kann Code in einem `do` Bindung. Was geschieht, wenn Sie müssen jedoch ohne Ausführung von Code in einem zusätzlichen Konstruktor eine `do` Bindung? Zu diesem Zweck verwenden Sie die `then` Schlüsselwort.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

Die Nebeneffekte des primären Konstruktors ist immer noch ausgeführt. Aus diesem Grund ist die Ausgabe wie folgt ein.

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a>Selbstbezeichner in Konstruktoren

In anderen Mitgliedern geben Sie einen Namen für das aktuelle Objekt in der Definition der einzelnen Member. Sie können auch den Selbstbezeichner in der ersten Zeile der Definition der Klasse einfügen, mit der `as` -Schlüsselwort direkt hinter der Parameter des Konstruktors. Das folgende Beispiel veranschaulicht diese Syntax.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

In zusätzlichen Konstruktoren können Sie auch einen Selbstbezeichner definieren, durch Einfügen der `as` Klausel direkt nach dem Parameter des Konstruktors. Das folgende Beispiel veranschaulicht diese Syntax.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

Es können Probleme auftreten, wenn Sie versuchen, ein Objekt zu verwenden, bevor sie vollständig definiert ist. Aus diesem Grund kann der Selbstbezeichner verwendet den Compiler eine Warnung ausgeben, und fügen Sie zusätzliche Überprüfungen, um sicherzustellen, dass der Member eines Objekts nicht zugegriffen werden, bevor das Objekt initialisiert wird. Verwenden Sie nur den Selbstbezeichner in die `do` Bindungen des primären Konstruktors oder nach der `then` -Schlüsselwort in zusätzliche Konstruktoren.

Der Name des der Selbstbezeichner muss keine werden `this`. Es kann jeder gültige Bezeichner sein.

## <a name="assigning-values-to-properties-at-initialization"></a>Zuweisen von Werten zu Eigenschaften, die bei der Initialisierung

Sie können die Eigenschaften eines Klassenobjekts im Initialisierungscode Werte zuweisen, durch eine Liste der Zuweisungen der Form Anfügen `property = value` an die Argumentliste für einen Konstruktor. Dies wird im folgenden Codebeispiel gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Die folgende Version des obigen Codes zeigt die Kombination der normale Argumente und optionale Argumente eigenschafteneinstellungen in einen Konstruktoraufruf enthalten.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a>Konstruktoren in der geerbten Klasse

Wenn von einer Basisklasse zu erben, die über einen Konstruktor verfügt, müssen Sie die Argumente in der Klausel erben angeben. Weitere Informationen finden Sie unter [Konstruktoren und Vererbung](../inheritance.md#constructors-and-inheritance).

## <a name="static-constructors-or-type-constructors"></a>Statische Konstruktoren oder Konstruktoren Typen

Zusätzlich zur Angabe von Code zum Erstellen von Objekten, statische `let` und `do` Bindungen in Klassentypen, die ausgeführt werden, bevor der Typ zuerst verwendet wird, für die Initialisierung auf Typebene erstellt werden können. Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](let-bindings-in-classes.md) und [ `do` Bindungen in Klassen](do-bindings-in-classes.md).

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
