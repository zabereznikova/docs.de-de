---
title: Prozeduren
ms.date: 04/28/2017
helpviewer_keywords:
- procedures [Visual Basic], structured code
- Visual Basic code, procedures
- procedures [Visual Basic], types of
- structured code [Visual Basic], procedures
- procedures
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
ms.openlocfilehash: 926d2dcc7f29102457d5ed9632e7455f8f0c7b96
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071325"
---
# <a name="procedures-in-visual-basic"></a>Prozeduren in Visual Basic

Eine *Prozedur* ist ein Block von Visual Basic Anweisungen, die von einer Deklarations Anweisung ( `Function` , `Sub` , `Operator` , `Get` , `Set` ) und einer entsprechenden `End` Deklaration eingeschlossen werden. Alle ausführbaren Anweisungen in Visual Basic müssen sich innerhalb einiger Prozeduren befinden.  
  
## <a name="calling-a-procedure"></a>Aufrufen einer Prozedur  

 Sie rufen eine Prozedur an einer anderen Stelle im Code auf. Dies wird als *Prozeduraufruf* bezeichnet. Wenn die Ausführung der Prozedur abgeschlossen ist, übergibt die Prozedur die Kontrolle wieder an den Code, von dem sie aufgerufen wurde. Dieser Code wird als *aufrufender Code* bezeichnet. Der aufrufende Code ist eine Anweisung, oder ein Ausdruck in einer Anweisung, die die Prozedur mit einem Namen angibt und dieser die Kontrolle übergibt.  
  
## <a name="returning-from-a-procedure"></a>Nach dem Abschluss der Prozedur  

 Wenn die Prozedur abgeschlossen wurde, übergibt sie die Kontrolle wieder an den aufrufenden Code. Zu diesem Zweck kann eine [Return-Anweisung](../../../language-reference/statements/return-statement.md), die entsprechende Exit- [Anweisungs](../../../language-reference/statements/exit-statement.md) Anweisung für die Prozedur oder die [End- \<keyword> Statement](../../../language-reference/statements/end-keyword-statement.md) -Anweisung der Prozedur verwendet werden. Dann wird die Kontrolle wieder an den aufrufenden Code im Anschluss an die Stelle des Prozeduraufrufs übergeben.  
  
- Mit einer `Return`-Anweisung wird die Kontrolle sofort wieder an den aufrufenden Code übergeben. Anweisungen, die hinter der `Return`-Anweisung stehen, werden nicht ausgeführt. Es können sich mehrere `Return`-Anweisungen in derselben Prozedur befinden.  
  
- Mit einer `Exit Sub`- oder `Exit Function`-Anweisung wird die Kontrolle sofort wieder an den aufrufenden Code übergeben. Anweisungen, die hinter der `Exit`-Anweisung stehen, werden nicht ausgeführt. Es können sich mehrere `Exit`-Anweisungen in derselben Prozedur befinden. Außerdem können sich sowohl `Return`- als auch `Exit`-Anweisungen in derselben Prozedur befinden.  
  
- Wenn eine Prozedur weder eine `Return`- noch eine `Exit`-Anweisung aufweist, schließt sie mit einer `End Sub`- oder `End Function`-, `End Get`- oder `End Set`-Anweisung hinter der letzten Anweisung des Texts der Prozedur ab. Die `End`-Anweisung übergibt die Kontrolle sofort wieder an den aufrufenden Code. Es darf sich nur eine `End`-Anweisung in einer Prozedur befinden.  
  
## <a name="parameters-and-arguments"></a>Parameter und Argumente  

 In den meisten Fällen muss eine Prozedur bei jedem Aufruf unterschiedliche Daten verarbeiten. Diese Informationen können Sie im Rahmen eines Prozeduraufrufs an die Prozedur übergeben. Die Prozedur definiert keine oder mehrere *Parameter*. Diese Parameter stellen jeweils einen Wert dar, der von der Prozedur erwartet wird. Jedem Parameter in der Definition der Prozedur entspricht ein *Argument* im Prozeduraufruf. Ein Argument stellt einen Wert dar, den Sie an den entsprechenden Parameter in einem gegebenen Prozeduraufruf übergeben.  
  
## <a name="types-of-procedures"></a>Prozedurtypen  

 Visual Basic verwendet mehrere Arten von Prozeduren:  
  
- [Sub-Prozeduren](./sub-procedures.md) führen Aktionen aus, geben jedoch keinen Wert an den aufrufenden Code zurück.  
  
- Ereignisbehandlungsprozeduren sind `Sub`-Prozeduren, die als Reaktion auf ein Ereignis ausgeführt werden, das durch eine Benutzeraktion oder durch Auftreten in einem Programm ausgelöst wurde.  
  
- [Function-Prozeduren](./function-procedures.md) geben einen Wert an den aufrufenden Code zurück. Bevor sie einen Wert zurückgeben, können sie noch weitere Aktionen ausführen.

    Einige in C# geschriebene Funktionen geben einen *Verweisrückgabewert* zurück. Funktionsaufrufer modifizieren den Rückgabewert. Diese Modifizierung wird durch den Zustand des aufgerufenen Objekts widergespiegelt. Ab Visual Basic 2017 kann Code von Visual Basic Verweisrückgabewerte verarbeiten, auch wenn er einen Wert nicht nach Verweis zurückgeben kann. Weitere Informationen finden Sie unter [Verweisrückgabewerte](ref-return-values.md).
  
- [Eigenschaftenprozeduren](./property-procedures.md) geben Werte von Eigenschaften auf Objekten und Modulen zurück und weisen diese zu.  
  
- [Operatorprozeduren](./operator-procedures.md) definieren das Verhalten von Standardoperatoren, wenn mindestens einer der beiden Operanden eine neu definierte Klasse oder Struktur ist.  
  
- [Generische Prozeduren in Visual Basic](../data-types/generic-procedures.md) definieren zusätzlich zu ihren normalen Parametern mindestens einen *Typparameter*, damit der aufrufende Code bei jedem Aufruf spezifische Datentypen übergeben kann.  
  
## <a name="procedures-and-structured-code"></a>Prozeduren und strukturierter Code  

 Jede Zeile ausführbaren Codes in Ihrer Anwendung muss sich in einer Prozedur befinden, wie z.B. `Main`, `calculate` oder `Button1_Click`. Wenn Sie große Prozeduren in kleinere austeilen, macht das Ihre Anwendung lesbarer.  
  
 Prozeduren sind beim Ausführen von wiederholten oder freigegebenen Aufgaben nützlich. Solche Aufgaben können z.B. häufig verwendete Berechnungen, das Bearbeiten von Text und Steuerelementen und Datenbankvorgänge sein. Sie können eine Prozedur von vielen verschiedenen Stellen in Ihrem Code aufrufen, damit Sie Prozeduren als Bausteine für Ihre Anwendung verwenden können.  
  
 Wenn Sie Ihren Code mit Prozeduren strukturieren, bringt das folgende Vorteile:  
  
- Mit Prozeduren können Sie Ihre Programme in diskrete logische Einheiten aufteilen. Außerdem ist es leichter, einzelne Einheiten zu debuggen als ein Programm ohne Prozeduren zu debuggen.  
  
- Nachdem Sie Prozeduren für ein Programm entwickelt haben, können Sie diese auch in anderen Programmen einsetzen, und das oft mit wenigen bis gar keinen Änderungen. So können Sie Codeduplikate vermeiden.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer Prozedur](./how-to-create-a-procedure.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Rekursive Prozeduren](./recursive-procedures.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Generic Procedures in Visual Basic](../data-types/generic-procedures.md)
- [Objekte und Klassen](../objects-and-classes/index.md)
