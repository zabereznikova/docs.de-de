---
title: Überladene Eigenschaften und Methoden (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: c0aa7c4a13e049045743044a98020a1aab2cf1a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652193"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Überladene Eigenschaften und Methoden (Visual Basic)

Überladen ist die Erstellung von mehr als eine Prozedur, Instanzkonstruktor oder Eigenschaft in einer Klasse mit dem gleichen Namen, aber unterschiedliche Argumenttypen.  
  
## <a name="overloading-usage"></a>Überladen Verbrauch

 Überladen ist besonders nützlich, wenn Ihr Objektmodell vorgegeben, die Verwendung identischer Namen für Prozeduren, die für unterschiedliche Datentypen angewendet werden. Z. B. eine Klasse, die mehrere unterschiedliche Datentypen anzeigen sollen, kann möglicherweise `Display` Prozeduren, die wie folgt aussehen:  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 Ohne überladen müssten Sie unterschiedliche Namen für jede Prozedur erstellen, auch wenn sie dasselbe, führen Sie als Nächstes dargestellt:  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 Überladen von erleichtert es, Eigenschaften oder Methoden verwendet werden, da es sich um eine Auswahl von Datentypen bereitstellt, die verwendet werden kann. Z. B. die überladene `Display` erläutert zuvor kann aufgerufen werden mit den folgenden Codezeilen:  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 Zur Laufzeit ruft Visual Basic das korrekte Verfahren basierend auf den Datentypen der Parameter, die Sie angeben.  
  
## <a name="overloading-rules"></a>Überladen von Regeln

 Sie erstellen ein überladenen Members für eine Klasse, durch Hinzufügen von zwei oder mehr Eigenschaften oder Methoden mit demselben Namen. Mit Ausnahme von überladenen Membern abgeleiteten jeder überladene Member muss unterschiedlichen Parameterlisten aufweisen, und die folgenden Elemente können nicht als Unterscheidungsmerkmal Feature beim Überladen einer Eigenschaft oder Prozedur verwendet werden:  
  
-   Modifizierer, wie z. B. `ByVal` oder `ByRef`, gilt für einen Member oder Parameter des Members.  
  
-   Namen von Parametern  
  
-   Rückgabetypen von Prozeduren  
  
 Die `Overloads` Schlüsselwort ist optional, beim Überladen, aber wenn eine überladene Member verwendet die `Overloads` -Schlüsselwort, und klicken Sie dann auf alle anderen überladene Member mit demselben Namen müssen auch dieses Schlüsselwort angeben.  
  
 Abgeleitete Klassen können geerbte Member mit Member mit identischen Parametern und die Parametertypen, genannten überladen *shadowing durch den Namen und derselben Signatur*. Wenn die `Overloads` Schlüsselwort wird verwendet, wenn shadowing nach Namen und derselben Signatur, die abgeleitete Klasse die Implementierung des Elements anstelle der Implementierung in der Basisklasse verwendet werden, und alle anderen Überladungen für dieses Element ist verfügbar auf Instanzen von der abgeleitete Klasse.  
  
 Wenn die `Overloads` -Schlüsselwort ausgelassen wird, wenn einen geerbten Member mit einem Member zu überladen, die identische Parameter und Parametertypen aufweist, und klicken Sie dann das überladen wird aufgerufen, *namentlich shadowing*. Shadowing anhand des Namens die geerbte Implementierung eines Elements ersetzt, und es macht alle anderen Überladungen auf Instanzen von der abgeleiteten Klasse und ihre Decedents nicht verfügbar.  
  
 Die `Overloads` und `Shadows` Modifizierer können nicht zusammen mit dem gleichen Eigenschaft oder Methode verwendet werden.  
  
### <a name="example"></a>Beispiel

 Das folgende Beispiel erstellt die überladene Methoden, die entweder akzeptieren ein `String` oder `Decimal` Darstellung ein Währungsbetrag und der Rückgabewert eine Zeichenfolge, die die Mehrwertsteuer enthält.  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>In diesem Beispiel verwenden, um eine überladene Methode erstellen
  
1.  Öffnen Sie ein neues Projekt und fügen Sie eine Klasse mit dem Namen `TaxClass`.  
  
2.  Fügen Sie der `TaxClass`-Klasse folgenden Code hinzu.  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  Fügen Sie das folgende Verfahren zum Formular hinzu.  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  Fügen Sie eine Schaltfläche auf Ihrem Formular, und rufen die `ShowTax` Prozedur aus dem `Button1_Click` -Ereignis der Schaltfläche.  
  
5.  Führen Sie das Projekt, und klicken Sie auf die Schaltfläche auf dem Formular so testen Sie die überladene `ShowTax` Prozedur.  
  
 Zur Laufzeit wählt der Compiler die entsprechenden überladene Funktion, die den verwendeten Parametern übereinstimmt. Wenn Sie die Schaltfläche klicken, die überladene Methode wird aufgerufen zunächst mit einer `Price` -Parameter, ist eine Zeichenfolge und die Meldung "Preis ist eine Zeichenfolge. Tax ist $5,12" wird angezeigt. `TaxAmount` wird aufgerufen, mit einem `Decimal` Wert ein zweites Mal und der Meldung, die "Preis ist eine Dezimalzahl. Tax ist $5,12" wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch

 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
