---
title: Overload Resolution
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
ms.openlocfilehash: 84d52bbbfb34c2e5d67ed6a1810ab3e32fafda22
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266871"
---
# <a name="overload-resolution-visual-basic"></a>Überladungsauflösung (Visual Basic)
Wenn der Visual Basic-Compiler einen Aufruf einer Prozedur erlässt, die in mehreren überladenen Versionen definiert ist, muss der Compiler entscheiden, welche der Überladungen aufzurufen sind. Dies geschieht, indem die folgenden Schritte ausgeführt werden:  
  
1. **Zugänglichkeit.** Es eliminiert jede Überlastung mit einer Zugriffsebene, die verhindert, dass der aufrufende Code ihn aufruft.  
  
2. **Anzahl der Parameter.** Es eliminiert jede Überlastung, die eine andere Anzahl von Parametern definiert, als im Aufruf angegeben werden.  
  
3. **Parameterdatentypen.** Der Compiler gibt Instanzmethoden die Voreinstellung gegenüber Erweiterungsmethoden. Wenn eine Instanzmethode gefunden wird, die nur Erweiterungskonvertierungen erfordert, um dem Prozeduraufruf zu entsprechen, werden alle Erweiterungsmethoden gelöscht, und der Compiler fährt nur mit den Instanzmethodenkandidaten fort. Wenn keine solche Instanzmethode gefunden wird, wird sie sowohl mit Instanz- als auch mit Erweiterungsmethoden fortgesetzt.  
  
     In diesem Schritt wird eine Überlastung eliminiert, für die die Datentypen der aufrufenden Argumente nicht in die in der Überladung definierten Parametertypen konvertiert werden können.  
  
4. **Einschränkende Konvertierungen.** Es eliminiert alle Überladungen, die eine eingrenzende Konvertierung von den aufrufenden Argumenttypen in die definierten Parametertypen erfordern. Dies gilt unabhängig davon, ob der Typprüfungsschalter ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) oder `On` `Off`ist.  
  
5. **Geringste Verbreiterung.** Der Compiler betrachtet die verbleibenden Überladungen paarweise. Für jedes Paar werden die Datentypen der definierten Parameter verglichen. Wenn die Typen in einem der Überladungen alle auf die entsprechenden Typen in der anderen erweitern, eliminiert der Compiler letztere. Das heißt, es behält die Überlastung, die die geringste Erweiterung erfordert.  
  
6. **Einzelkandidat.** Es wird weiterhin Überladungen in Paaren betrachtet, bis nur noch eine Überladung verbleibt, und der Aufruf dieser Überladung wird aufgelöst. Wenn der Compiler die Überladungen nicht auf einen einzelnen Kandidaten reduzieren kann, wird ein Fehler generiert.  
  
 Die folgende Abbildung zeigt den Prozess, der bestimmt, welche einer Gruppe überladener Versionen aufzurufen ist.  
  
 ![Flussdiagramm des Überladungsauflösungsprozesses](./media/overload-resolution/determine-overloaded-version.gif "Auflösen zwischen überlasteten Versionen")
  
 Das folgende Beispiel veranschaulicht diesen Überladungsauflösungsprozess.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 Beim ersten Aufruf eliminiert der Compiler die erste Überladung, da`Short`der Typ des ersten Arguments`Byte`( ) auf den Typ des entsprechenden Parameters ( ) beschränkt wird. Anschließend wird die dritte Überladung eliminiert, da sich`Short` jeder `Single`Argumenttyp in der zweiten Überladung`Integer` ( `Single`und ) auf den entsprechenden Typ in der dritten Überladung ( und ) erweitert. Die zweite Überladung erfordert weniger Erweiterungen, sodass der Compiler sie für den Aufruf verwendet.  
  
 Beim zweiten Aufruf kann der Compiler keine der Überladungen auf der Grundlage der Verengung eliminieren. Die dritte Überladung wird aus dem gleichen Grund wie beim ersten Aufruf eliminiert, da die zweite Überladung mit weniger Erweiterung der Argumenttypen aufrufen kann. Der Compiler kann jedoch nicht zwischen der ersten und zweiten Überladung auflösen. Jeder verfügt über einen definierten Parametertyp, der sich`Byte` `Short`auf `Single` den `Double`entsprechenden Typ im anderen ( nach , aber nach ) erweitert. Der Compiler generiert daher einen Fehler bei der Überladungsauflösung.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Überladene optionale und ParamArray-Argumente  
 Wenn zwei Überladungen einer Prozedur identische Signaturen haben, mit der Ausnahme, dass der letzte Parameter in einem als [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) und in der anderen [als ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) deklariert wird, löst der Compiler einen Aufruf dieser Prozedur wie folgt auf:  
  
|Wenn der Aufruf das letzte Argument als|Der Compiler löst den Aufruf der Überladung auf und deklariert das letzte Argument als|  
|---|---|  
|Kein Wert (Argument weggelassen)|`Optional`|  
|Ein einzelner Wert|`Optional`|  
|Zwei oder mehr Werte in einer durch Kommas getrennten Liste|`ParamArray`|  
|Ein Array beliebiger Länge (einschließlich eines leeren Arrays)|`ParamArray`|  
  
## <a name="see-also"></a>Weitere Informationen

- [Optionale Parameter](./optional-parameters.md)
- [Parameter-Arrays](./parameter-arrays.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Erweiterungsmethoden](./extension-methods.md)
