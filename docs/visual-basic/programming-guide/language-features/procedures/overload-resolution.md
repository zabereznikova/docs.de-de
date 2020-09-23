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
ms.openlocfilehash: 9b83eba8efc8dfe14b6ec1cbab270984977198e5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071364"
---
# <a name="overload-resolution-visual-basic"></a>Überladungsauflösung (Visual Basic)

Wenn der Visual Basic-Compiler auf einen aufzurufenden Vorgang einer Prozedur stößt, die in mehreren überladenen Versionen definiert ist, muss der Compiler entscheiden, welche der über Ladungen aufgerufen werden soll. Hierzu führen Sie die folgenden Schritte aus:  
  
1. **Barrierefreiheit.** Es entfernt sämtliche über Ladungen mit einer Zugriffsebene, die verhindert, dass der aufrufende Code ihn aufrufen kann.  
  
2. **Anzahl von Parametern.** Es beseitigt alle über Ladungen, die eine andere Anzahl von Parametern definieren, als im-Befehl angegeben sind.  
  
3. **Parameter Datentypen.** Der Compiler gibt Instanzmethoden als bevorzugte Erweiterungs Methoden an. Wenn eine Instanzmethode gefunden wird, die nur erweiternde Konvertierungen erfordert, um den Prozedur aufrufungen abzugleichen, werden alle Erweiterungs Methoden gelöscht, und der Compiler fährt mit nur den Instanzen Methoden Kandidaten fort. Wenn eine solche Instanzmethode nicht gefunden wird, wird Sie mit der Instanz-und der Erweiterungsmethode fortgesetzt.  
  
     In diesem Schritt entfällt jede Überladung, bei der die Datentypen der aufrufenden Argumente nicht in die in der Überladung definierten Parametertypen konvertiert werden können.  
  
4. **Einschränkende Konvertierungen.** Alle über Ladungen, die eine einschränkende Konvertierung von den aufrufenden Argument Typen in die definierten Parametertypen erfordern, werden eliminiert. Dies gilt unabhängig davon, ob der Schalter für die Typüberprüfung ([Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)) `On` oder ist `Off` .  
  
5. **Geringste Erweiterung.** Der Compiler betrachtet die verbleibenden über Ladungen paarweise. Für jedes Paar werden die Datentypen der definierten Parameter verglichen. Wenn die Typen in einer der über Ladungen alle zu den entsprechenden Typen in der anderen erweitert werden, entfernt der Compiler den letzteren. Das heißt, dass die Überladung beibehalten wird, die den geringsten Erweiterungs Aufwand erfordert.  
  
6. **Einzelner Kandidat.** Die über Ladungen in Paaren werden fortgesetzt, bis nur eine Überladung verbleibt, und der Aufrufen dieser Überladung wird aufgelöst. Wenn der Compiler die über Ladungen nicht auf einen einzelnen Kandidaten reduzieren kann, wird ein Fehler generiert.  
  
 Die folgende Abbildung zeigt den Prozess, der bestimmt, welche einer Reihe von überladenen Versionen aufgerufen werden.  
  
 ![Flussdiagramm des Überladungsauflösungsprozesses](./media/overload-resolution/determine-overloaded-version.gif "Auflösen von überladenen Versionen")
  
 Im folgenden Beispiel wird dieser Überladungs Auflösungsprozess veranschaulicht.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 Im ersten-Befehl entfernt der Compiler die erste Überladung, da der Typ des ersten Arguments ( `Short` ) auf den Typ des entsprechenden Parameters () beschränkt wird `Byte` . Anschließend wird die dritte Überladung beseitigt, da jeder Argumenttyp in der zweiten `Short` Überladung (und `Single` ) auf den entsprechenden Typ in der dritten Überladung (und) erweitert wird `Integer` `Single` . Die zweite Überladung erfordert weniger Erweiterungen, sodass der Compiler Sie für den-Befehl verwendet.  
  
 Im zweiten-Befehl kann der Compiler keine der über Ladungen auf der Basis der Einschränkung ausschließen. Die dritte Überladung wird aus demselben Grund wie beim ersten-Befehl entfernt, da Sie die zweite Überladung mit einer geringeren Erweiterung der Argument Typen aufrufen kann. Der Compiler kann jedoch nicht zwischen der ersten und der zweiten Überladung aufgelöst werden. Jede verfügt über einen definierten Parametertyp, der zum entsprechenden Typ in der anderen ( `Byte` `Short` , aber `Single` zu) erweitert wird `Double` . Der Compiler generiert daher einen Fehler bei der Überladungs Auflösung.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Überladene optionale und ParamArray-Argumente  

 Wenn zwei über Ladungen einer Prozedur identische Signaturen aufweisen, mit dem Unterschied, dass der letzte Parameter in einem und [ParamArray](../../../language-reference/modifiers/paramarray.md) in der anderen als [optional](../../../language-reference/modifiers/optional.md) deklariert wird, löst der Compiler einen Aufrufen dieser Prozedur wie folgt auf:  
  
|Wenn der-Befehl das letzte Argument als|Der Compiler löst den Aufrufen der-Überladung auf, die das letzte Argument deklariert, als|  
|---|---|  
|Kein Wert (Argument ausgelassen)|`Optional`|  
|Ein einzelner Wert|`Optional`|  
|Mindestens zwei Werte in einer durch Trennzeichen getrennten Liste|`ParamArray`|  
|Ein Array beliebiger Längen (einschließlich eines leeren Arrays)|`ParamArray`|  
  
## <a name="see-also"></a>Siehe auch

- [Optionale Parameter](./optional-parameters.md)
- [Parameterarrays](./parameter-arrays.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Überladungen](../../../language-reference/modifiers/overloads.md)
- [Erweiterungsmethoden](./extension-methods.md)
