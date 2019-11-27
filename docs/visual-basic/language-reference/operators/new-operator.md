---
title: New-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 27b5b4516ef729045036c36fedc24b6c576a4f61
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348319"
---
# <a name="new-operator-visual-basic"></a>Operator New (Visual Basic)

Führt eine `New`-Klausel ein, um eine neue Objektinstanz zu erstellen, gibt eine Konstruktoreinschränkung für einen Typparameter an oder identifiziert eine `Sub` Prozedur als Klassenkonstruktor.

## <a name="remarks"></a>Hinweise

In einer Deklaration oder Zuweisungsanweisung muss eine `New`-Klausel eine definierte Klasse angeben, aus der die Instanz erstellt werden kann. Dies bedeutet, dass die Klasse einen oder mehrere Konstruktoren verfügbar machen muss, auf die der aufrufenden Code zugreifen kann.

Sie können eine `New`-Klausel in einer Deklarations Anweisung oder einer Zuweisungsanweisung verwenden. Wenn die Anweisung ausgeführt wird, wird der entsprechende Konstruktor der angegebenen Klasse aufgerufen, wobei alle von Ihnen bereitgestellten Argumente übergeben werden. Dies wird im folgenden Beispiel veranschaulicht, indem Instanzen einer `Customer`-Klasse erstellt werden, die zwei Konstruktoren hat, eine ohne Parameter und eine, die einen Zeichen folgen Parameter annimmt:

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

Da Arrays Klassen sind, können `New` eine neue Array Instanz erstellen, wie im folgenden Beispiel gezeigt:

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

Der Common Language Runtime (CLR) löst einen <xref:System.OutOfMemoryException> Fehler aus, wenn nicht genügend Arbeitsspeicher vorhanden ist, um die neue Instanz zu erstellen.

> [!NOTE]
> Das `New`-Schlüsselwort wird auch in Typparameter Listen verwendet, um anzugeben, dass der angegebene Typ einen zugänglichen Parameter losen Konstruktor verfügbar machen muss. Weitere Informationen zu Typparametern und Einschränkungen finden Sie unter [Type List](../statements/type-list.md).

Wenn Sie eine konstruktorprozedur für eine Klasse erstellen möchten, legen Sie den Namen einer `Sub` Prozedur auf das `New`-Schlüsselwort fest. Weitere Informationen finden Sie unter [Objekt Lebensdauer: Erstellen und zerstören von Objekten](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:

- [Dim-Anweisung](../statements/dim-statement.md)
- [Of](../statements/of-clause.md)
- [Sub-Anweisung](../statements/sub-statement.md)

## <a name="see-also"></a>Siehe auch

- <xref:System.OutOfMemoryException>
- [Schlüsselwörter](../keywords/index.md)
- [Typliste](../statements/type-list.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
