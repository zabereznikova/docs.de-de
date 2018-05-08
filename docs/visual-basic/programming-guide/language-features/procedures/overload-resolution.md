---
title: Überladungsauflösung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: d95589eb16f45eeff10692cdc897bf65ebe2d84e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="overload-resolution-visual-basic"></a>Überladungsauflösung (Visual Basic)
Stößt der Visual Basic-Compiler einen Aufruf an eine Prozedur, die in mehreren überladenen Versionen definiert ist, muss der Compiler die Überladung aufrufen, entscheiden. Dies geschieht durch die folgenden Schritte ausführen:  
  
1.  **Barrierefreiheit.** Überladung mit der Zugriffsebene, die verhindert, dass den aufrufenden Code Aufrufen dieser beseitigt.  
  
2.  **Die Anzahl von Parametern.** Überladung, die eine andere Anzahl von Parametern definiert als angegeben wird, werden im Aufruf beseitigt.  
  
3.  **Parameterdatentypen.** Der Compiler gibt Instanzmethoden über Erweiterungsmethoden. Wenn Instanzmethode, dass erfordert, dass nur erweiterungskonvertierungen entsprechend den Prozeduraufruf gefunden wird, alle Erweiterungsmethoden werden gelöscht, und der Compiler fährt mit nur die Methode Kandidaten Instanz. Wenn keine solche Instanzmethode gefunden wird, wird er mit Instanz- und Erweiterungsmethoden fortgesetzt.  
  
     In diesem Schritt aber es wird Überladung für die die Datentypen der aufrufenden Argumente in die Parametertypen, die in der Überladung definiert konvertiert werden können.  
  
4.  **Einschränkende Konvertierungen.** Überladung, die eine einschränkende Konvertierung aus dem aufrufenden Argumenttypen mit den definierten Parametertypen erfordert beseitigt. Dies ist "true" gibt an, ob die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On` oder `Off`.  
  
5.  **Geringste Erweiterung.** Der Compiler betrachtet die verbleibenden Überladungen paarweise zugeordnet. Für jedes Paar vergleicht er die Datentypen der definierten Parameter. Wenn die Typen in eine der Überladungen, die alle auf die entsprechenden Typen in den anderen erweitert werden, entfällt der Compiler letztere. D. h., behält es die Überladung, die am wenigsten erweiternde erforderlich sind.  
  
6.  **Einzelne geeignet.** Sollten Überladungen paarweise zugeordnet, bis die einzige bleibt Überladung und des Aufrufs an diese Überladung löst wird fortgesetzt. Wenn der Compiler nicht die Überladungen, die einem einzelnen Kandidaten reduziert werden kann, wird einen Fehler generiert.  
  
 Die folgende Abbildung zeigt den Prozess, der bestimmt, die eine Reihe von überladenen Versionen aufrufen.  
  
 ![Flussdiagramm des überladungsauflösungsprozesses](./media/overloadres.gif "OverloadRes")  
Bei überladenen Versionen auflösen  
  
 Das folgende Beispiel veranschaulicht dieses überladungsauflösungsprozesses.  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 Beim ersten Aufruf beseitigt der Compiler die erste Überladung, da der Typ des ersten Arguments (`Short`) in den Typ des entsprechenden Parameters schränkt (`Byte`). Sie klicken Sie dann die dritte Überladung beseitigt, da jeder Argumenttyp der zweiten Überladung (`Short` und `Single`) in den entsprechenden Typ in die dritte Überladung erweitert (`Integer` und `Single`). Die zweite Überladung eine geringere Erweiterung erfordert, damit der Compiler für den Funktionsaufruf verwendet.  
  
 Im zweiten Aufruf kann nicht vom Compiler der Überladungen Einschränken vermieden. Die dritte Überladung beseitigt aus demselben Grund wie der erste Aufruf, da die zweite Überladung mit geringerer Erweiterung der Argumenttypen aufgerufen werden kann. Der Compiler kann nicht zwischen den ersten und zweiten Überladungen jedoch aufgelöst werden. Jede verfügt über einen definierten Parametertyp in den entsprechenden Typ in den anderen erweitert (`Byte` auf `Short`, aber `Single` auf `Double`). Aus diesem Grund generiert der Compiler Fehler Auflösung Überladung.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Überladene optionale und ParamArray-Argumente  
 Wenn zwei Überladungen einer Prozedur identische Signaturen verfügen, mit dem Unterschied, dass der letzte Parameter deklariert wird [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in einem und [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in anderen, löst der Compiler einen Aufruf an diese Prozedur als lautet folgendermaßen:  
  
|Wenn der Aufruf wird des letzten Arguments als|Der Compiler löst den Aufruf an die Überladung, die das letzte Argument als deklarieren|  
|---|---|  
|Kein Wert (Argument weggelassen)|`Optional`|  
|ein einzelner Wert|`Optional`|  
|Zwei oder mehr Werte in einer durch Trennzeichen getrennte Liste|`ParamArray`|  
|Ein Array mit beliebiger Länge (einschließlich ein leeres Array)|`ParamArray`|  
  
## <a name="see-also"></a>Siehe auch  
 [Optionale Parameter](./optional-parameters.md)  
 [Parameterarrays](./parameter-arrays.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)  
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)  
 [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)  
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Erweiterungsmethoden](./extension-methods.md)
