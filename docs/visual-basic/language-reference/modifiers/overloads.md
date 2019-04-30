---
title: Overloads (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 0d68846938aba809a7a3a6f7d27f185bb90a39cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920678"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)
Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur bzw. mehrere mit dem gleichen Namen neu deklariert.  
  
## <a name="remarks"></a>Hinweise  
 *Überladen von* wird die Bereitstellung von mehr als eine Definition für einen angegebenen Eigenschaft oder Prozedur im gleichen Bereich. Durch das erneute Deklarieren einer Eigenschaft oder Prozedur mit einer anderen Signatur wird gelegentlich aufgerufen *Ausblenden nach Signatur*.  
  
## <a name="rules"></a>Regeln  
  
- **Deklarationskontext.** Sie können `Overloads` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.  
  
- **Kombinierte Modifizierer.** Sie können keine angeben `Overloads` zusammen mit [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in derselben Prozedurdeklaration.  
  
- **Erforderliche Unterschiede.** Die *Signatur* in dieser Deklaration muss sich von der Signatur jeder Eigenschaft oder Prozedur, die sie überlädt. Die Signatur besteht aus der Eigenschaft oder dem Prozedurnamen und dem Folgenden:  
  
    - der Anzahl der Parameter  
  
    - Der Reihenfolge der Parameter  
  
    - der Datentypen der Parameter  
  
    - der Anzahl der Typparameter (für eine generische Prozedur)  
  
    - der Rückgabetyp (nur für eine Konvertierungsoperatorprozedur)  
  
     Alle Überladungen müssen denselben Namen aufweisen. Jede muss sich jedoch von allen anderen in mindestens einem der vorstehenden Punkte unterscheiden. Dadurch kann der Compiler unterscheiden, welche Version verwendet werden muss, wenn der Code die Eigenschaft oder Prozedur aufruft.  
  
- **Nicht zulässige Unterschiede.** Das Ändern von mindestens einem der folgenden Punkte ist für das Überladen einer Eigenschaft oder Prozedur nicht gültig, da sie kein Bestandteil der Signatur sind:  
  
    - ob ein Wert (für eine Prozedur) zurückgegeben wird  
  
    - der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)  
  
    - die Namen der Parameter oder Typparameter  
  
    - die Einschränkungen hinsichtlich der Typparameter (für eine generische Prozedur)  
  
    - Parametermodifiziererschlüsselwörter (wie `ByRef` oder `Optional`)  
  
    - Eigenschaft oder Prozedurmodifiziererschlüsselwörter (wie `Public` oder `Shared`)  
  
- **Optionaler Modifizierer.** Sie müssen den `Overloads`-Modifizierer nicht verwenden, wenn Sie mehrere überladene Eigenschaften oder Prozeduren in derselben Klasse definieren. Wenn Sie jedoch `Overloads` in einer der Deklarationen verwenden, müssen Sie sie in allen davon verwenden.  
  
- **Shadowing und Überladung.** `Overloads` kann auch auf ein vorhandenes Member oder eine Gruppe von überladenen Membern in einer Basisklasse verwendet werden. Wenn Sie `Overloads` auf diese Art und Weise verwenden, deklarieren Sie die Eigenschaft oder Methode mit demselben Namen und derselben Parameterliste als Basisklassenmember, und Sie stellen das `Shadows`-Schlüsselwort nicht bereit.  
  
 Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.  
  
 Der `Overloads`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Prozedurüberladung](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
