---
title: Delegaten
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [Visual Basic]
- Visual Basic code, delegates
ms.assetid: 410b60dc-5e60-4ec0-bfae-426755a2ee28
ms.openlocfilehash: 1f161248fa04f8fab0e5335413e69ca565732f71
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410682"
---
# <a name="delegates-visual-basic"></a>Delegaten (Visual Basic)

Delegaten sind Objekte, die auf Methoden verweisen. Sie werden zuweilen als *typsichere Funktionszeiger* beschrieben, da sie in anderen Programmiersprachen verwendeten Funktionszeigern ähneln. Im Gegensatz zu Funktions Zeigern sind Visual Basic Delegaten jedoch ein Verweistyp, der auf der-Klasse basiert <xref:System.Delegate?displayProperty=nameWithType> . Delegaten können sowohl auf freigegebene Methoden – Methoden, die ohne eine bestimmte Instanz einer Klasse aufgerufen werden können – als auch Instanzmethoden verweisen.

## <a name="delegates-and-events"></a>Delegaten und Ereignisse

Delegaten sind in Situationen hilfreich, in denen Sie einen Mittler zwischen einer aufrufenden Prozedur und der aufgerufenen Prozedur benötigen. Ein Beispiel: Sie möchten, dass ein Objekt, das Ereignisse auslöst, unter verschiedenen Bedingungen verschiedene Ereignishandler aufrufen kann. Leider ist dem Objekt, das die Ereignisse auslöst, nicht im Voraus bekannt, welcher Ereignishandler ein bestimmtes Ereignis verarbeitet. Visual Basic ermöglicht das dynamische Zuordnen von Ereignis Handlern zu Ereignissen durch Erstellen eines Delegaten für Sie, wenn Sie die- `AddHandler` Anweisung verwenden. Zur Laufzeit leitet der Delegat dann Aufrufe an den entsprechenden Ereignishandler weiter.

Obwohl Sie eigene Delegaten erstellen können, erstellt Visual Basic in den meisten Fällen den Delegaten und kümmert sich um die Details. Eine `Event`-Anweisung definiert z.B. implizit eine Delegatklasse mit dem Namen `<EventName>EventHandler` als geschachtelte Klasse der Klasse, die die `Event`-Anweisung enthält, und mit der gleichen Signatur wie das Ereignis. Die `AddressOf`-Anweisung erstellt implizit eine Instanz eines Delegaten, die auf eine bestimmte Prozedur verweist. Die folgenden beiden Codezeilen sind gleichwertig. In der ersten Zeile sehen Sie die explizite Erstellung einer Instanz von `EventHandler` mit einem Verweis auf die `Button1_Click`-Methode, die als Argument gesendet wird. Die zweite Zeile ist eine praktischere Möglichkeit, das Gleiche auszuführen.

[!code-vb[VbVbalrDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#6)]

Die schnelle Methode zum Erstellen von Delegaten können Sie immer dort verwenden, wo der Compiler den Delegattyp anhand des Kontexts bestimmen kann.

## <a name="declaring-events-that-use-an-existing-delegate-type"></a>Deklarieren von Ereignissen, die einen vorhandenen Delegattyp verwenden

In manchen Situationen empfiehlt es sich, ein Ereignis so zu deklarieren, dass es einen vorhandenen Delegattyp als zugrunde liegenden Delegaten verwendet. Die folgende Syntax veranschaulicht dies:

[!code-vb[VbVbalrDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#7)]

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

[!code-vb[VbVbalrDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class2.vb#15)]

Die Signatur der Funktion muss mit der des Delegattyps übereinstimmen. Weitere Informationen zu Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke](../procedures/lambda-expressions.md). Beispiele für Lambda-Ausdrücke und `AddressOf`-Zuweisungen zu Delegaten finden Sie unter [Gelockerte Delegatenkonvertierung](relaxed-delegate-conversion.md).

## <a name="related-topics"></a>Verwandte Themen

|Titel|BESCHREIBUNG|
|-----------|-----------------|
|[Vorgehensweise: Aufrufen einer Delegatenmethode](how-to-invoke-a-delegate-method.md)|Zeigt anhand eines Beispiels, wie Sie eine Methode einem Delegaten zuweisen und diese Methode anschließend über den Delegaten aufrufen.|
|[Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](how-to-pass-procedures-to-another-procedure.md)|Veranschaulicht, wie Delegaten verwendet werden, um eine Prozedur an eine andere Prozedur zu übergeben.|
|[Gelockerte Delegatenkonvertierung](relaxed-delegate-conversion.md)|Beschreibt, wie Subs und Funktionen Delegaten oder Handlern zugewiesen werden können, auch wenn deren Signaturen nicht identisch sind.|
|[Ereignisse](../events/index.md)|Stellt eine Übersicht über Ereignisse in Visual Basic bereit.|
