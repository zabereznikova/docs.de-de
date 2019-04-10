---
title: 'Vorgehensweise: Definieren eines Parameters für eine Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 55925b0f007b1be2f5d46ffc0854601f483b2e2d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333833"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Vorgehensweise: Definieren eines Parameters für eine Prozedur (Visual Basic)
Ein *Parameter* kann der aufrufenden Code einen Wert an die Prozedur übergeben werden, wenn er aufgerufen. Jeder Parameter für eine Prozedur deklariert die gleiche Weise, wie Sie eine Variable deklarieren, die die Namen und den Datentyp angibt. Sie geben auch den Übergabemechanismus und gibt an, ob der Parameter optional ist.  
  
 Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Um Parameter einer Prozedur zu definieren.  
  
1. Fügen Sie in der Deklaration der Prozedur der Name des Parameters an der Prozedur bei der Parameterliste, durch die Trennung von anderen Parametern durch Kommas.  
  
2. Entscheiden Sie, den Datentyp des Parameters.  
  
3. Führen Sie den Namen des Parameters mit einem `As` -Klausel, um den Datentyp anzugeben.  
  
4. Entscheiden Sie, den Übergabemechanismus, die, den Sie für den Parameter verwenden möchten. Übergeben Sie normalerweise einen Parameter ab, nach Wert, es sei denn, Sie möchten, dass das Verfahren, um ihren Wert in den aufrufenden Code ändern zu können.  
  
5. Der Parametername mit vorausgehen [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) den Übergabemechanismus angeben. Weitere Informationen finden Sie unter [Unterschiede zwischen Argumentübergabe nach Wert "und" By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6. Wenn der Parameter optional ist, geben Sie vor dem Übergabemechanismus [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) und folgen Sie den Datentyp des Parameters mit einem Gleichheitszeichen (`=`) und einen Standardwert.  
  
     Im folgende Beispiel wird die Gliederung definiert eine `Sub` Prozedur mit drei Parametern. Die ersten beiden sind erforderlich, und das dritte optional ist. Die Parameterdeklarationen werden in der Parameterliste durch Kommas getrennt.  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     Der erste Parameter nimmt eine `customer` Objekt und `updateCustomer` können direkt aktualisieren, der an übergebene Variable `c` , da das Argument übergeben wird [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Die Werte der beiden letzten Argumente kann von die Prozedur kann nicht geändert werden, da sie übergeben werden [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Wenn der aufrufende Code keinen Wert für bereitstellt der `level` -Parameter für Visual Basic wird es auf den Standardwert 0.  
  
     Wenn die typüberprüfung wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `Off`, `As` -Klausel ist optional, wenn Sie einen Parameter definieren. Jedoch wenn Sie einen Parameter verwendet eine `As` -Klausel, alle müssen verwenden. Wenn der Schalter für die typüberprüfung ist `On`, `As` -Klausel ist erforderlich für jede Parameterdefinition.  
  
     Angabe von Datentypen für alle von Programmierelementen heißt als *starke Typisierung*. Wenn Sie festlegen, `Option Strict On`, Visual Basic erzwingt eine starke Typisierung. Dies wird dringend empfohlen, den folgenden Gründen empfohlen:  
  
    -   Sie können IntelliSense-Unterstützung für Ihre Variablen und Parameter. Dadurch können Sie die Eigenschaften und andere Member zu sehen, wie Sie in Ihren Code eingeben.  
  
    -   Sie können den Compiler an, führen Sie die Überprüfung des Typs. Dadurch wird die catch-Anweisungen, die zur Laufzeit aufgrund von Fehlern wie z. B. Überlauf ausfallen können. Es fängt auch Aufrufe von Methoden für Objekte, die diese nicht unterstützen.  
  
    -   Es führt zu einer schnelleren Ausführung Ihres Codes. Ein Grund hierfür ist, wenn Sie einen Datentyp für ein Programmierelement nicht angeben, die Visual Basic-Compiler weist die `Object` Typ. Der kompilierte Code möglicherweise zwischen hin und her konvertiert `Object` und andere Datentypen, die Leistung verringert.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Rekursive Prozeduren](./recursive-procedures.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)
