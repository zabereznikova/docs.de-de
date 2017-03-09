---
title: "Delegates (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "02/25/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "delegates [Visual Basic]"
  - "Visual Basic code, delegates"
ms.assetid: 410b60dc-5e60-4ec0-bfae-426755a2ee28
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Delegates (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Delegaten sind Objekte, die auf Methoden verweisen.  Sie werden mitunter als *typsichere Funktionszeiger* bezeichnet, da sie Funktionszeigern ähneln, die in anderen Programmiersprachen verwendet werden.  Im Gegensatz zu Funktionszeigern sind [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Delegaten ein Referenztyp, der auf der <xref:System.Delegate?displayProperty=fullName>\-Klasse basiert.  Delegaten können sowohl auf freigegebene Methoden \(d. h. Methoden, die ohne eine bestimmte Instanz einer Klasse aufgerufen werden können\) als auch auf Instanzenmethoden verweisen.  
  
## Delegaten und Ereignisse  
 Delegaten sind in Situationen nützlich, in denen Sie einen Mittler zwischen einer aufrufenden Prozedur und der aufgerufenen Prozedur benötigen.  Vielleicht soll z. B. ein Objekt, das Ereignisse auslöst, die Fähigkeit haben, in verschiedenen Situationen unterschiedliche Ereignishandler aufzurufen.  Leider ist dem Objekt, von dem die Ereignisse ausgelöst werden, nicht vorzeitig bekannt, von welchem Ereignishandler ein bestimmtes Ereignis behandelt wird.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] ermöglicht die dynamische Zuordnung von Ereignishandlern zu Ereignissen durch Erstellen eines Delegaten, wenn die `AddHandler`\-Anweisung verwendet wird.  Zur Laufzeit leitet der Delegat dann Aufrufe an den entsprechenden Ereignishandler weiter.  
  
 Sie können zwar auch eigene Delegaten erstellen, doch in den meisten Fällen generiert [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] den Delegaten und verarbeitet die Details.  Eine `Event`\-Anweisung definiert z. B. implizit eine Delegatklasse mit dem Namen `<EventName>EventHandler` als geschachtelte Klasse der Klasse, die die `Event`\-Anweisung enthält, und mit der gleichen Signatur wie das Ereignis.  Die `AddressOf`\-Anweisung erstellt implizit eine Instanz eines Delegaten, die auf eine bestimmte Prozedur verweist.  Die folgenden zwei Codezeilen sind gleichwertig.  In der ersten Zeile wird die explizite Erstellung einer Instanz von `Eventhandler` mit einem Verweis auf die `Button1_Click`\-Methode angezeigt, die als Argument gesendet wird.  Die zweite Zeile ist eine zweckmäßigere Möglichkeit, den gleichen Schritt auszuführen.  
  
 [!code-vb[VbVbalrDelegates#6](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/delegates_1.vb)]  
  
 Die schnelle Methode zum Erstellen von Delegaten können Sie immer dort verwenden, wo der Compiler den Delegattyp anhand des Kontexts erkennen kann.  
  
## Deklarieren von Ereignissen, die einen vorhandenen Delegattyp verwenden  
 In manchen Situationen empfiehlt es sich, ein Ereignis so zu deklarieren, dass es einen vorhandenen Delegattyp als zugrunde liegenden Delegaten verwendet.  Die folgende Syntax veranschaulicht dies:  
  
 [!code-vb[VbVbalrDelegates#7](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/delegates_2.vb)]  
  
 Dies ist nützlich, wenn mehrere Ereignisse an den gleichen Handler weitergeleitet werden sollen.  
  
## Delegatvariablen und \-parameter  
 Sie können Delegaten für andere, nicht mit Ereignissen verknüpfte Aufgaben \(z. B. freies Threading\) oder für Prozeduren verwenden, die zur Laufzeit verschiedene Versionen von Funktionen aufrufen müssen.  
  
 Beispiel: Eine Anwendung für Gebrauchtwagen\-Kleinanzeigen enthält ein Listenfeld mit den Namen von Fahrzeugen.  Die Anzeigen sind nach Titel sortiert. Der Titel ist in der Regel der Name des Fahrzeugherstellers.  Ein mögliches Problem tritt auf, wenn bei einigen Autos das Herstellungsjahr des Autos vor dem Herstellernamen steht.  Das Problem besteht darin, dass die integrierte Suchfunktion des Listenfelds nur nach Zeichencodes sortiert. Dadurch werden alle Anzeigen, die mit dem Jahr beginnen, an den Beginn der Liste platziert, erst dann folgen die Anzeigen, die mit dem Herstellernamen beginnen.  
  
 Um dies zu beheben, können Sie eine Sortierprozedur in einer Klasse erstellen, die auf der standardmäßigen alphabetischen Sortierung basiert, die für die meisten Listenfelder gilt, jedoch zur Laufzeit auf die benutzerdefinierte Sortierung für Gebrauchtwagen umgestellt werden kann.  Dafür übergeben Sie die benutzerdefinierte Sortierprozedur mithilfe von Delegaten zur Laufzeit an die Sortierklasse.  
  
## AddressOf\- und Lambda\-Ausdrücke  
 Jede Delegatklasse definiert einen Konstruktor, an den die Spezifikation einer Objektmethode übergeben wird.  Ein Argument für einen Delegatkonstruktor muss ein Verweis auf eine Methode oder ein Lambda\-Ausdruck sein.  
  
 Verwenden Sie die folgende Syntax, um einen Verweis auf eine Methode festzulegen:  
  
 `AddressOf` \[`expression`.\]`methodName`  
  
 Der Typ von `expression` muss zur Kompilierungszeit der Name einer Klasse oder Schnittstelle sein, die eine Methode des angegebenen Namens enthält, deren Signatur mit der Signatur der Delegatklasse übereinstimmt.  Mit `methodName` kann entweder eine freigegebene Methode oder eine Instanzenmethode angegeben werden.  `methodName` ist nicht optional, selbst dann nicht, wenn Sie einen Delegaten für die Standardmethode der Klasse erstellen.  
  
 Verwenden Sie die folgende Syntax, um einen Lambda\-Ausdruck festzulegen:  
  
 `Function` \(\[`parm` As `type`, `parm2` As `type2`, ...\]\) `expression`  
  
 Im folgenden Beispiel werden sowohl `AddressOf`\- als auch Lambda\-Ausdrücke angezeigt, mit denen der Verweis für einen Delegaten angegeben wird.  
  
 [!code-vb[VbVbalrDelegates#15](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/delegates_3.vb)]  
  
 Die Signatur der Funktion muss mit dem Delegattyp übereinstimmen.  Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  Weitere Beispiele für Lambda\-Ausdrücke und `AddressOf`\-Zuweisungen zu Delegaten finden Sie unter [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[How to: Invoke a Delegate Method](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)|Zeigt anhand eines Beispiels, wie Sie eine Methode einem Delegaten zuweisen und diese Methode anschließend über den Delegaten aufrufen.|  
|[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)|Veranschaulicht, wie Delegaten verwendet werden, um eine Prozedur einer anderen Prozedur zu übergeben.|  
|[Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)|Beschreibt, wie Unterroutinen und Funktionen Delegaten oder Handlern zugewiesen werden können, auch wenn deren Signaturen nicht identisch sind.|  
|[Events](../../../../visual-basic/programming-guide/language-features/events/events.md)|Stellt eine Übersicht über Ereignisse in Visual Basic bereit.|