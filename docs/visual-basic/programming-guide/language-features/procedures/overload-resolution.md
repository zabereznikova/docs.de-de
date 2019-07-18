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
ms.openlocfilehash: 4f81c7377423899c142c4270f325bbd7ed20b877
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792028"
---
# <a name="overload-resolution-visual-basic"></a>Überladungsauflösung (Visual Basic)
Stößt der Visual Basic-Compiler einen Aufruf an eine Prozedur, die in mehreren überladenen Versionen definiert ist, müssen Sie von der Compiler entscheiden, welche Überladung aufrufen. Hierzu werden die folgenden Schritte ausführen:  
  
1. **Barrierefreiheit.** Überladung mit der Zugriffsebene, die verhindert, dass den aufrufenden Code Aufrufen dieser beseitigt.  
  
2. **Anzahl von Parametern.** Überladung, die eine andere Anzahl von Parametern definiert als bereitgestellt werden, in dem Aufruf beseitigt.  
  
3. **Parameterdatentypen.** Der Compiler zieht Instanzmethoden über Erweiterungsmethoden. Wenn eine beliebige Instanzmethode, dass erfordert erweiterungskonvertierungen entsprechend den Prozeduraufruf gefunden wird, alle Erweiterungsmethoden werden gelöscht, und der Compiler, die mit nur den Instanzmethoden wird fortgesetzt. Wenn keine solche Instanzmethode gefunden wird, weiterhin mit sowohl die Instanz als auch die Erweiterungsmethoden.  
  
     In diesem Schritt entfällt diese alle Überladungen, die für die die Datentypen der Argumente der Aufruf mit den Parametertypen in der Überladung definiert konvertiert werden können.  
  
4. **Einschränkende Konvertierungen.** Überladung, die eine einschränkende Konvertierung von der aufrufenden Argumenttypen definierten Parametertypen erfordert beseitigt. Dies ist "true" gibt an, ob die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `On` oder `Off`.  
  
5. **Geringste Erweiterung.** Der Compiler betrachtet die verbleibenden Überladungen in Paaren. Für jedes Paar werden die Datentypen der definierten Parameter verglichen. Wenn die Typen in einer der Überladungen, die alle auf die entsprechenden Typen in der anderen erweitert werden kann, beseitigt der Compiler die zweite. D. h., bleibt die Überladung, die die geringste Menge an erweiternde erforderlich sind.  
  
6. **Einzelne Kandidat.** Da die Überladungen, bis nur eine paarweise überladen bleibt und löst des Aufrufs von dieser Überladung wird fortgesetzt. Wenn der Compiler die Überladungen, die einem einzelnen Kandidaten reduzieren kann, wird einen Fehler generiert.  
  
 Die folgende Abbildung zeigt den Prozess, der bestimmt, die einem Satz von überladenen Versionen aufgerufen.  
  
 ![Flussdiagramm des überladungsauflösungsprozesses](./media/overload-resolution/determine-overloaded-version.gif "zwischen überladenen Versionen auflösen")    
  
 Das folgende Beispiel veranschaulicht diese überladungsauflösungsprozesses.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 Im ersten Aufruf wird der Compiler beseitigt die erste Überladung, da der Typ des ersten Arguments (`Short`) wird in den Typ des entsprechenden Parameters (`Byte`). Klicken Sie dann beseitigt, die dritte Überladung, da jedes Typargument in der zweiten Überladung (`Short` und `Single`) wird in den entsprechenden Typen in der dritten Überladung erweitert (`Integer` und `Single`). Die zweite Überladung eine geringere Erweiterung erfordert, damit der Compiler für den Aufruf verwendet.  
  
 Im zweiten Aufruf kann nicht vom Compiler Überladung einschränkende vermieden. Die dritte Überladung beseitigt aus demselben Grund wie der erste Aufruf, da die zweite Überladung mit geringerer Erweiterung der Argumenttypen aufgerufen werden kann. Jedoch kann der Compiler zwischen den ersten und zweiten Überladungen nicht auflösen. Jede hat einen definierten Parameter-Typ, der in den entsprechenden Typ in der anderen erweitert wird (`Byte` zu `Short`, aber `Single` zu `Double`). Aus diesem Grund generiert der Compiler einen Fehler bei der objektnamensauflösung Überladung.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Optionale überladen und ParamArray-Argumente  
 Wenn zwei Überladungen einer Prozedur identische Signaturen verfügen, mit dem Unterschied, dass der letzte Parameter deklariert, wird [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in einem und [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in die andere ist der Compiler löst einen Aufruf dieser Prozedur als Die folgende:  
  
|Wenn der Aufruf das letzte Argument als bereitstellt|Der Compiler löst den Aufruf an die Überladung, die das letzte Argument als deklarieren|  
|---|---|  
|Kein Wert (Argument ausgelassen wird)|`Optional`|  
|Ein einzelner Wert|`Optional`|  
|Zwei oder mehr Werte in einer durch Trennzeichen getrennte Liste|`ParamArray`|  
|Ein Array mit beliebiger Länge (einschließlich ein leeres Array)|`ParamArray`|  
  
## <a name="see-also"></a>Siehe auch

- [Optionale Parameter](./optional-parameters.md)
- [Parameterarrays](./parameter-arrays.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Erweiterungsmethoden](./extension-methods.md)
