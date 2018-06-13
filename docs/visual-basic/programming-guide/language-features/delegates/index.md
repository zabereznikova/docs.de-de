---
title: Delegaten (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [Visual Basic]
- Visual Basic code, delegates
ms.assetid: 410b60dc-5e60-4ec0-bfae-426755a2ee28
ms.openlocfilehash: 99fe0eee194fae21615652c9426bf6027fbf4354
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652882"
---
# <a name="delegates-visual-basic"></a>Delegaten (Visual Basic)
Delegaten sind Objekte, die auf Methoden verweisen. Sie werden zuweilen als *typsichere Funktionszeiger* beschrieben, da sie in anderen Programmiersprachen verwendeten Funktionszeigern ähneln. Im Gegensatz zu Funktionszeigern, Visual Basic-Delegaten ein Verweistyp, basierend auf der Klasse sind jedoch <xref:System.Delegate?displayProperty=nameWithType>. Delegaten können sowohl auf freigegebene Methoden – Methoden, die ohne eine bestimmte Instanz einer Klasse aufgerufen werden können – als auch Instanzmethoden verweisen.  
  
## <a name="delegates-and-events"></a>Delegaten und Ereignisse  
 Delegaten sind in Situationen hilfreich, in denen Sie einen Mittler zwischen einer aufrufenden Prozedur und der aufgerufenen Prozedur benötigen. Ein Beispiel: Sie möchten, dass ein Objekt, das Ereignisse auslöst, unter verschiedenen Bedingungen verschiedene Ereignishandler aufrufen kann. Leider ist dem Objekt, das die Ereignisse auslöst, nicht im Voraus bekannt, welcher Ereignishandler ein bestimmtes Ereignis verarbeitet. Visual Basic können Sie dynamisch zuordnen Ereignishandlern mit Ereignissen durch das Erstellen eines Delegaten für die Sie bei der Verwendung der `AddHandler` Anweisung. Zur Laufzeit leitet der Delegat dann Aufrufe an den entsprechenden Ereignishandler weiter.  
  
 Obwohl Sie Ihre eigenen Delegaten in den meisten Fällen erstellen können, die Visual Basic wird der Delegat erstellt und der Details für Sie übernimmt. Eine `Event`-Anweisung definiert z.B. implizit eine Delegatklasse mit dem Namen `<EventName>EventHandler` als geschachtelte Klasse der Klasse, die die `Event`-Anweisung enthält, und mit der gleichen Signatur wie das Ereignis. Die `AddressOf`-Anweisung erstellt implizit eine Instanz eines Delegaten, die auf eine bestimmte Prozedur verweist. Die folgenden beiden Codezeilen sind gleichwertig. In der ersten Zeile sehen Sie die explizite Erstellung einer Instanz von `Eventhandler` mit einem Verweis auf die `Button1_Click`-Methode, die als Argument gesendet wird. Die zweite Zeile ist eine praktischere Möglichkeit, das Gleiche auszuführen.  
  
 [!code-vb[VbVbalrDelegates#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_1.vb)]  
  
 Die schnelle Methode zum Erstellen von Delegaten können Sie immer dort verwenden, wo der Compiler den Delegattyp anhand des Kontexts bestimmen kann.  
  
## <a name="declaring-events-that-use-an-existing-delegate-type"></a>Deklarieren von Ereignissen, die einen vorhandenen Delegattyp verwenden  
 In manchen Situationen empfiehlt es sich, ein Ereignis so zu deklarieren, dass es einen vorhandenen Delegattyp als zugrunde liegenden Delegaten verwendet. Die folgende Syntax veranschaulicht dies:  
  
 [!code-vb[VbVbalrDelegates#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_2.vb)]  
  
 Dies ist nützlich, wenn mehrere Ereignisse an den gleichen Handler weitergeleitet werden sollen.  
  
## <a name="delegate-variables-and-parameters"></a>Delegatvariablen und -parameter  
 Sie können Delegaten für andere, nicht auf Ereignisse bezogene Tasks (z.B. freies Threading) oder für Prozeduren verwenden, die zur Laufzeit verschiedene Versionen von Funktionen aufrufen müssen.  
  
 Ein Beispiel: Eine Anwendung für Gebrauchtwagen-Kleinanzeigen enthält ein Listenfeld mit den Namen von Fahrzeugen. Die Anzeigen sind nach Titel sortiert, wobei es sich in der Regel um die Marke handelt. Ein Problem kann dann auftreten, wenn bei einigen Autos das Baujahr vor der Marke steht. Das Problem besteht darin, dass die integrierte Suchfunktion des Listenfelds nur nach Zeichencodes sortiert. Daher werden alle Anzeigen, die mit dem Jahr beginnen, an den Beginn der Liste sortiert, erst dann folgen die Anzeigen, die mit der Marke beginnen.  
  
 Um dies zu beheben, können Sie eine Sortierprozedur in einer Klasse erstellen, die in den meisten Listenfeldern die standardmäßige alphabetische Sortierung verwendet, jedoch zur Laufzeit auf die benutzerdefinierte Sortierung für Gebrauchtwagenanzeigen umgestellt werden kann. Dafür übergeben Sie die benutzerdefinierte Sortierprozedur mithilfe von Delegaten zur Laufzeit an die Sortierklasse.  
  
## <a name="addressof-and-lambda-expressions"></a>AddressOf- und Lambda-Ausdrücke  
 Jede Delegatklasse definiert einen Konstruktor, dem die Spezifikation einer Objektmethode übergeben wird. Ein Argument für einen Delegatkonstruktor muss ein Verweis auf eine Methode oder ein Lambda-Ausdruck sein.  
  
 Verwenden Sie die folgende Syntax, um einen Verweis auf eine Methode festzulegen:  
  
 `AddressOf` [`expression`.]`methodName`  
  
 Der Typ von `expression` muss zur Kompilierungszeit der Name einer Klasse oder Schnittstelle sein, die eine Methode des angegebenen Namens enthält, deren Signatur mit der Signatur der Delegatklasse übereinstimmt. Bei `methodName` kann es sich um eine freigegebene Methode oder um eine Instanzmethode handeln. Der `methodName` ist nicht optional, selbst dann nicht, wenn Sie einen Delegaten für die Standardmethode der Klasse erstellen.  
  
 Verwenden Sie die folgende Syntax, um einen Lambda-Ausdruck festzulegen:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 Das folgende Beispiel zeigt sowohl `AddressOf`- als auch Lambda-Ausdrücke, mit denen der Verweis für einen Delegaten angegeben wird.  
  
 [!code-vb[VbVbalrDelegates#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_3.vb)]  
  
 Die Signatur der Funktion muss mit der des Delegattyps übereinstimmen. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md). Beispiele für Lambda-Ausdrücke und `AddressOf`-Zuweisungen zu Delegaten finden Sie unter [Gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Gewusst wie: Aufrufen einer Delegatenmethode](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)|Zeigt anhand eines Beispiels, wie Sie eine Methode einem Delegaten zuweisen und diese Methode anschließend über den Delegaten aufrufen.|  
|[Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)|Veranschaulicht, wie Delegaten verwendet werden, um eine Prozedur an eine andere Prozedur zu übergeben.|  
|[Gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)|Beschreibt, wie Subs und Funktionen Delegaten oder Handlern zugewiesen werden können, auch wenn deren Signaturen nicht identisch sind.|  
|[Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)|Stellt eine Übersicht über Ereignisse in Visual Basic bereit.|
