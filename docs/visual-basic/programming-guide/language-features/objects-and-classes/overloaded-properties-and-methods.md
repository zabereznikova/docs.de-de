---
title: Überladene Eigenschaften und Methoden
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
ms.openlocfilehash: 1672f12773ece012c580253b6dafbf9d0ac8f07c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389151"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Überladene Eigenschaften und Methoden (Visual Basic)

Überladen ist die Erstellung von mehr als einer Prozedur, einem Instanzkonstruktor oder einer Eigenschaft in einer Klasse mit demselben Namen, aber unterschiedlichen Argument Typen.

## <a name="overloading-usage"></a>Überladen der Verwendung

Das überladen ist besonders nützlich, wenn das Objektmodell vorschreibt, dass Sie identische Namen für Prozeduren verwenden, die auf unterschiedliche Datentypen angewendet werden. Beispielsweise könnte eine Klasse, die mehrere unterschiedliche Datentypen anzeigen kann, über `Display` Prozeduren verfügen, die wie folgt aussehen:

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

Ohne überladen müssen Sie für jede Prozedur eindeutige Namen erstellen, auch wenn Sie das gleiche tun, wie im folgenden dargestellt:

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

Das überladen vereinfacht die Verwendung von Eigenschaften oder Methoden, da es eine Auswahl von Datentypen ermöglicht, die verwendet werden können. Beispielsweise kann die zuvor beschriebene überladene `Display` Methode mit einer der folgenden Codezeilen aufgerufen werden:

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

Zur Laufzeit ruft Visual Basic die richtige Prozedur auf Grundlage der Datentypen der Parameter auf, die Sie angeben.

## <a name="overloading-rules"></a>Überladen von Regeln

 Sie erstellen ein überladenes Element für eine Klasse, indem Sie zwei oder mehr Eigenschaften oder Methoden mit demselben Namen hinzufügen. Mit Ausnahme überladener abgeleiteter Member muss jedes überladene Element über unterschiedliche Parameterlisten verfügen, und die folgenden Elemente können nicht als differenzierende Funktion verwendet werden, wenn eine Eigenschaft oder Prozedur überladen wird:

- Modifiziererer, z `ByVal` . b. oder `ByRef` , die für einen Member gelten, oder Parameter des Members.

- Parameternamen

- Rückgabe Typen von Prozeduren

Das `Overloads` Schlüsselwort ist beim Überladen optional. Wenn jedoch ein überladenes Element das `Overloads` Schlüsselwort verwendet, müssen auch alle anderen überladenen Member mit demselben Namen dieses Schlüsselwort angeben.

Abgeleitete Klassen können geerbte Member mit Membern mit identischen Parametern und Parametertypen überladen. Dies ist ein Prozess, *der als shadowingby Name und Signatur*bezeichnet wird. Wenn das `Overloads` Schlüsselwort beim shadodown nach Name und Signatur verwendet wird, wird die Implementierung des Members der abgeleiteten Klasse anstelle der Implementierung in der Basisklasse verwendet, und alle anderen über Ladungen für diesen Member sind für Instanzen der abgeleiteten Klasse verfügbar.

Wenn das- `Overloads` Schlüsselwort beim Überladen eines geerbten Members mit einem Member mit identischen Parametern und Parametertypen weggelassen wird, wird das überladen als *shadowingby Name*bezeichnet. Shadowingby Name ersetzt die geerbte Implementierung eines Members und macht alle anderen über Ladungen für Instanzen der abgeleiteten Klasse und deren Elemente nicht verfügbar.

Die `Overloads` `Shadows` modifiziererer und können nicht gleichzeitig mit der gleichen Eigenschaft oder Methode verwendet werden.

### <a name="example"></a>Beispiel

Im folgenden Beispiel werden überladene Methoden erstellt, die entweder eine- `String` oder `Decimal` -Darstellung eines Dollarbetrags akzeptieren und eine Zeichenfolge zurückgeben, die die Verkaufssteuer enthält.

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>So verwenden Sie dieses Beispiel zum Erstellen einer überladenen Methode

1. Öffnen Sie ein neues Projekt, und fügen Sie eine Klasse namens hinzu `TaxClass` .

2. Fügen Sie der `TaxClass` -Klasse den folgenden Code hinzu.

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. Fügen Sie dem Formular die folgende Prozedur hinzu.

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. Fügen Sie dem Formular eine Schaltfläche hinzu, und nennen Sie die `ShowTax` Prozedur aus dem- `Button1_Click` Ereignis der Schaltfläche.

5. Führen Sie das Projekt aus, und klicken Sie auf die Schaltfläche auf dem Formular, um die überladene `ShowTax` Prozedur

Zur Laufzeit wählt der Compiler die geeignete überladene Funktion aus, die den verwendeten Parametern entspricht. Wenn Sie auf die Schaltfläche klicken, wird die überladene Methode zuerst mit einem Parameter aufgerufen, bei dem `Price` es sich um eine Zeichenfolge handelt, und die Meldung "Price ist eine Zeichenfolge Steuern ist $5,12 "wird angezeigt. `TaxAmount`wird mit einem `Decimal` Wert beim zweiten Mal und in der Meldung "price is a Decimal" aufgerufen. Steuern ist $5,12 "wird angezeigt.

## <a name="see-also"></a>Weitere Informationen

- [Objekte und Klassen](index.md)
- [Shadowing in Visual Basic](../declared-elements/shadowing.md)
- [Sub-Anweisung](../../../language-reference/statements/sub-statement.md)
- [Grundlagen der Vererbung](inheritance-basics.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [ByVal](../../../language-reference/modifiers/byval.md)
- [ByRef](../../../language-reference/modifiers/byref.md)
- [Overloads](../../../language-reference/modifiers/overloads.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
