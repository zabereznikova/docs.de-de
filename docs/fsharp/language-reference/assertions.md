---
title: Assertionen (F#)
description: "Erfahren Sie, wie den Ausdruck \"assert\" als eine Debugfunktion für das Testen von Ausdrücken in der Programmiersprache f# verwendet."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="assertions"></a>Assertionen

Die `assert` Ausdruck ist eine Debugfunktion, die Sie verwenden können, um einen Ausdruck zu testen. Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.

## <a name="syntax"></a>Syntax

```fsharp
assert condition
```

## <a name="remarks"></a>Hinweise

Die `assert` Ausdruck weist den Typ `bool -> unit`.

In der vorherigen Syntax *Bedingung* stellt einen booleschen Ausdruck, der getestet werden soll. Wenn der ausgewertete Ausdruck `true`, Ausführung wird fortgeführt, hat keine Auswirkung. Ergibt die Auswertung `false`, wird ein Systemfehlerdialogfeld generiert. Das Dialogfeld "Fehler" hat einer Beschriftung, die die Zeichenfolge enthält **"Assertionsfehler"**. Das Dialogfeld enthält eine stapelüberwachung, die angibt, in der Assertionsfehler aufgetreten ist.

Assertionsüberprüfung ist nur aktiviert, wenn Sie im Debugmodus kompiliert; d. h., wenn die Konstante `DEBUG` definiert ist. Im Projektsystem wird standardmäßig die `DEBUG` Konstante ist, aber nicht in der Releasekonfiguration in der Debugkonfiguration automatisch definiert.

Der Assertionsfehler kann nicht mit der f#-Ausnahmebehandlung abgefangen werden.

>[!NOTE]
Die `assert` Funktion löst in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht die Verwendung von der `assert` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a>Siehe auch

[F#-Sprachreferenz](index.md)
