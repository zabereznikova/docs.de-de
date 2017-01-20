---
title: "Delegaten mit benannten im Vergleich zu anonymen Methoden (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Delegaten [C#], Mit benannten im Vergleich zu anonymen Methoden"
  - "Methoden [C#], In Delegaten"
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Delegaten mit benannten im Vergleich zu anonymen Methoden (C#-Programmierhandbuch)
Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) kann einer benannten Methode zugeordnet werden.  Wenn Sie einen Delegaten mit einer benannten Methode instanziieren, wird die Methode als Parameter übergeben. Beispiel:  
  
 [!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/csrefDelegates/Delegates.cs#1)]  
  
 Dies wird als Verwendung einer benannten Methode bezeichnet.  Mit einer benannten Methode erstellte Delegaten können entweder eine [static](../../../csharp/language-reference/keywords/static.md)\-Methode oder eine Instanzmethode kapseln.  Benannte Methoden sind die einzige Möglichkeit, in früheren Versionen von C\# einen Delegaten zu instanziieren.  In Situationen, in denen das Erstellen einer neuen Methode ein unerwünschter Aufwand wäre, ermöglicht es Ihnen C\# jedoch, einen Delegaten zu instanziieren und sofort einen Codeblock anzugeben, den der Delegat bei Aufruf verarbeitet.  Der Block kann entweder einen Lambda\-Ausdruck oder eine anonyme Methoden enthalten.  Weitere Informationen finden Sie unter [Anonyme Funktionen](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## Hinweise  
 Die Methode, die Sie als Delegatparameter übergeben, muss über die gleiche Signatur verfügen wie die Delegatdeklaration.  
  
 Eine Delegatinstanz kapselt entweder eine statische oder eine Instanzenmethode.  
  
 Obwohl Delegaten einen [out](../../../csharp/language-reference/keywords/out.md)\-Parameter verwenden können, ist dies für Multicast\-Ereignisdelegaten nicht zu empfehlen, da nicht vorhersagbar ist, welcher Delegat aufgerufen wird.  
  
## Beispiel 1  
 Im Folgenden sehen Sie ein einfaches Beispiel für die Deklaration und Verwendung eines Delegaten.  Beachten Sie, dass der Delegat `Del` und die zugeordnete Methode `MultiplyNumbers` die gleiche Signatur haben.  
  
 [!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/csrefDelegates/Delegates.cs#2)]  
  
## Beispiel 2  
 Im folgenden Beispiel gibt ein Delegat, der einer statischen und einer Instanzmethode zugeordnet wird, aus jeder dieser Methoden spezifische Informationen zurück.  
  
 [!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/csrefDelegates/Delegates.cs#3)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [Gewusst wie: Kombinieren von Delegaten \(Multicastdelegaten\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)