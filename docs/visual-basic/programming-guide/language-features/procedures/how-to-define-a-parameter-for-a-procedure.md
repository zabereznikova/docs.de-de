---
title: 'Gewusst wie: Definieren eines Parameters für eine Prozedur (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eb4bac9208c03fd18e1904f58b247824d2c215da
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Gewusst wie: Definieren eines Parameters für eine Prozedur (Visual Basic)
Ein *Parameter* kann der aufrufenden Code einen Wert an die Prozedur übergeben werden, wenn es aufgerufen. Sie deklarieren jeden Parameter für eine Prozedur auf die gleiche Weise wie Sie eine Variable zu deklarieren, die den Namen und den Datentyp angibt. Sie geben auch den Übergabemechanismus und gibt an, ob der Parameter optional ist.  
  
 Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Um einen Parameter einer Prozedur zu definieren.  
  
1.  Fügen Sie in der Deklaration der Prozedur der Name des Parameters an die Prozedur Parameterliste, durch das es von anderen Parametern durch Kommas getrennt ein.  
  
2.  Entscheiden Sie, den Datentyp des Parameters.  
  
3.  Führen Sie den Namen des Parameters mit einem `As` -Klausel, um den Datentyp anzugeben.  
  
4.  Entscheiden Sie, den Übergabemechanismus für den Parameter den gewünschten. Übergeben Sie normalerweise einen Parameter ab, mit dem Wert, es sei denn, Sie die Prozedur, um dessen Wert in den Aufrufcode ändern zu können.  
  
5.  Der Name des Parameters mit vorausgehen [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) den Übergabemechanismus angeben. Weitere Informationen finden Sie unter [Unterschiede zwischen übergibt ein Argument nach Wert und nach Referenz](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Wenn der Parameter optional ist, geben Sie vor dem Übergabemechanismus [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) und folgen Sie den Datentyp des Parameters mit einem Gleichheitszeichen (`=`) und einen Standardwert.  
  
     Im folgende Beispiel wird die Gliederung definiert eine `Sub` Prozedur mit drei Parameter. Die ersten beiden sind erforderlich, und das dritte ist optional. Die Parameterdeklarationen werden in der Parameterliste durch Kommas getrennt.  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     Der erste Parameter akzeptiert eine `customer` -Objekt, und `updateCustomer` können direkt aktualisieren, die Variable übergeben, um `c` , da das Argument übergeben wird [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Die Prozedur kann nicht die Werte der beiden letzten Argumente nicht geändert werden, weil sie übergeben werden [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Wenn der aufrufende Code einen Wert für nicht angeben, ist die `level` Parameter, Visual Basic wird er auf den Standardwert 0.  
  
     Wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `Off`, `As` -Klausel ist optional, wenn Sie einen Parameter definieren. Jedoch wenn ein Parameter verwendet ein `As` -Klausel, alle muss verwenden. Wenn der Schalter für die typüberprüfung ist `On`, `As` -Klausel für jede Parameterdefinition erforderlich ist.  
  
     Das Festlegen von Datentypen für alle Programmierelemente genannt *starke Typisierung*. Bei Festlegung `Option Strict On`, Visual Basic erzwingt eine starke Typisierung. Dies wird dringend empfohlen, den folgenden Gründen empfohlen:  
  
    -   Dadurch werden IntelliSense-Unterstützung für die Variablen und Parametern. Dadurch können Sie ihre Eigenschaften und andere Elemente anzeigen, während der Eingabe im Code.  
  
    -   Sie können den Compiler an, führen Sie die Überprüfung des Typs. Dadurch wird das Abfangen von Anweisungen, die zur Laufzeit aufgrund von Fehlern, z. B. Überlauf ausgeführt werden kann. Auch fängt Sie Aufrufe von Methoden für Objekte, die sie unterstützen.  
  
    -   Es führt zu einer schnelleren Ausführung des Codes. Ein Grund dafür ist, dass wenn Sie einen Datentyp für ein Programmierelement nicht angeben, die Visual Basic-Compiler weist die `Object` Typ. Der kompilierte Code möglicherweise zwischen hin und her konvertiert `Object` und anderen Datentypen, die Leistung wird reduziert.  
  
## <a name="see-also"></a>Siehe auch

 [Verfahren](./index.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Rekursive Prozeduren](./recursive-procedures.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Objektorientierte Programmierung (Visual Basic)](../../concepts/object-oriented-programming.md)  
