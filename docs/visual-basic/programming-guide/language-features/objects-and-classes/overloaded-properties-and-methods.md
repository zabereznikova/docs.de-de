---
title: Überladene Eigenschaften und Methoden (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: 8d7341370d9770d2e57f786ac7c68277e66a9bbd
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677395"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Überladene Eigenschaften und Methoden (Visual Basic)

Überladen ist die Erstellung von mehr als eine Prozedur, Instanzenkonstruktor oder Eigenschaft in einer Klasse mit dem gleichen Namen, aber unterschiedliche Argumenttypen.

## <a name="overloading-usage"></a>Verwenden der Überladung

Überladen ist besonders nützlich, wenn Ihr Objektmodell vorgegeben, die Verwendung identischer Namen für Prozeduren, die für unterschiedliche Datentypen verwendet werden. Z. B. eine Klasse, die mehrere unterschiedliche Datentypen anzeigen, können möglicherweise `Display` Prozeduren, die wie folgt aussehen:

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

Ohne überladen zulässt müssten Sie unterschiedliche Namen für jede Prozedur zu erstellen, auch wenn sie das tun. wie im folgenden gezeigt:

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

Überladen von erleichtert es, Eigenschaften oder Methoden zu verwenden, da sie eine Auswahl von Datentypen enthält, die verwendet werden kann. Z. B. die überladene `Display` Methode erläutert zuvor kann aufgerufen werden mit den folgenden Codezeilen:

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

Zur Laufzeit ruft die Visual Basic die richtige Prozedur, die auf Grundlage der Datentypen der Parameter, die Sie angeben.

## <a name="overloading-rules"></a>Überladen von Regeln

 Sie erstellen einen überladenen Member für eine Klasse, durch das Hinzufügen von zwei oder mehr Eigenschaften oder Methoden mit demselben Namen. Mit Ausnahme von überladenen Membern abgeleiteten jeder überladene Member müssen die unterschiedlichen Parameterlisten, und die folgenden Elemente können nicht als unterscheidende Merkmal verwendet werden, wenn eine Eigenschaft oder Prozedur zu überladen:

- Modifizierer, z. B. `ByVal` oder `ByRef`, gilt für einen Member oder Parameter des Members.

- Namen von Parametern

- Rückgabetypen von Prozeduren

Die `Overloads` Schlüsselwort ist optional, beim Überladen, aber ggf. überladene Member verwendet die `Overloads` -Schlüsselwort, und klicken Sie dann auf alle anderen überladene Member mit demselben Namen müssen auch dieses Schlüsselwort angeben.

Abgeleitete Klassen können geerbte Member mit Member mit identischen Parametern und die Parametertypen, eines Prozesses Namens überladen *shadowing nach Namen und derselben Signatur*. Wenn die `Overloads` -Schlüsselwort wird verwendet, wenn shadowing nach Name und Signatur, Implementierung des Members der abgeleiteten Klasse anstelle der Implementierung in der Basisklasse verwendet werden aus, und alle anderen Überladungen für dieses Element Instanzen von werden der abgeleitete Klasse.

Wenn die `Overloads` -Schlüsselwort ausgelassen wird, beim Überladen von eines geerbten Members mit einem Member, die über identische Parameter und die Parametertypen verfügt, und klicken Sie dann die Überladung wird aufgerufen, *nach Namen shadowing*. Nach dem Namen Shadowing die geerbte Implementierung eines Elements ersetzt, und es allen anderen Überladungen für Instanzen von der abgeleiteten Klasse und die Decedents nicht verfügbar ist.

Die `Overloads` und `Shadows` -Modifizierer können nicht zusammen mit der gleichen Eigenschaft oder Methode verwendet werden.

### <a name="example"></a>Beispiel

Das folgende Beispiel erstellt überladene Methoden, die entweder akzeptieren einen `String` oder `Decimal` Darstellung eines Dollarbetrag und der Rückgabewert eine Zeichenfolge, die die Mehrwertsteuer enthält.

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>In diesem Beispiel verwenden, um eine überladene Methode erstellen

1. Öffnen Sie ein neues Projekt, und fügen Sie eine Klasse, die mit dem Namen `TaxClass`.

2. Fügen Sie der `TaxClass` -Klasse folgenden Code hinzu.

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. Fügen Sie das folgende Verfahren zum Formular hinzu.

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. Fügen Sie eine Schaltfläche, um Ihr Formular, und rufen die `ShowTax` Prozedur aus der `Button1_Click` -Ereignis der Schaltfläche.

5. Führen Sie das Projekt, und klicken Sie auf dem Formular so testen Sie die überladene `ShowTax` Verfahren.

Zur Laufzeit wählt der Compiler die entsprechende überladene Funktion, die den verwendeten Parametern übereinstimmt. Wenn Sie die Schaltfläche klicken, die überladene Methode zuerst aufgerufen mit einem `Price` -Parameter, ist eine Zeichenfolge und die Meldung "der Preis ist eine Zeichenfolge. Steuer ist $5,12" wird angezeigt. `TaxAmount` wird aufgerufen, mit einem `Decimal` Wert der zweiten Ausführung und der Meldung, "Preis ist eine Dezimalzahl. Steuer ist $5,12" wird angezeigt.

## <a name="see-also"></a>Siehe auch

- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)
- [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
