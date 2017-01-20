---
title: "Gewusst wie: Indizierte Eigenschaften bei der COM-Interop-Programmierung (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Indizierte Eigenschaften [C#]"
  - "Office-Programmierung [C#], Indizierte Eigenschaften"
  - "Eigenschaften [C#], Indiziert"
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Indizierte Eigenschaften bei der COM-Interop-Programmierung (C#-Programmierhandbuch)
*Indizierte Eigenschaften* verbessern die Art und Weise, auf die COM\-Eigenschaften, die über Parameter verfügen, von C\#\-Programmierung genutzt werden.  Indizierte Eigenschaften funktionieren zusammen mit anderen in Visual C\# 2010 eingeführten Funktionen zur Verbesserung der Microsoft Office\-Programmierung, wie [\-benannten und optionalen Argumenten](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), dem neuen [dynamic](../../../csharp/language-reference/keywords/dynamic.md)\-Typ und [eingebetteten Typinformationen](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 In früheren Versionen von C\# konnte auf Methoden nur als Eigenschaften zugegriffen werden, wenn die `get`\-Methode über keine Parameter, und die `set`\-Methode über ausschließlich einen Wertparameter verfügte.  Diese Bedingungen treffen jedoch nicht auf alle COM\-Eigenschaften zu.  Die Excel\-Eigenschaft [Range](http://go.microsoft.com/fwlink/?LinkId=166053) verfügt beispielsweise über einen `get`\-Accessor, der einen Parameter für den Namen des Bereichs erfordert.  Da zuvor auf die `Range`\-Eigenschaft nicht direkt zugegriffen werden konnte, musste stattdessen die `get_Range`\-Methode verwendet werden. Beispiel:  
  
 [!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/indexedpropscom/program.cs#1)]  
  
 Indizierte Eigenschaften ermöglichen stattdessen, Folgendes zu schreiben:  
  
 [!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/indexedpropscom/program.cs#2)]  
  
> [!NOTE]
>  Im vorherigen Beispiel wird auch die Funktion für [optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) verwendet, die in Visual C\# 2010 eingeführt wurde und Ihnen ermöglicht, `Type.Missing` wegzulassen.  
  
 Auf ähnliche Weise sind zum Festlegen des Werts der `Value`\-Eigenschaft eines [Range](http://go.microsoft.com/fwlink/?LinkId=179211)\-Objekts in Visual C\# 2008 und früher zwei Argumente erforderlich.  Durch das erste Argument wird ein optionaler Parameter angegeben, der den Typ des Bereichswerts angibt.  Mit dem zweiten Argument wird der Wert für die `Value`\-Eigenschaft bereitgestellt.  Vor Visual C\# 2010 war in C\# nur ein Argument gestattet.  Daher musste statt einer regulär festgelegten Methode entweder die `set_Value`\-Methode oder eine andere Eigenschaft verwendet werden, [Value2](http://go.microsoft.com/fwlink/?LinkId=166050).  Die folgende Beispiele veranschaulichen diese Techniken.  In beiden wird der Wert der Zelle "A1" auf `Name` festgelegt.  
  
 [!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/indexedpropscom/program.cs#3)]  
  
 Indizierte Eigenschaften ermöglichen stattdessen, folgenden Code zu schreiben:  
  
 [!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/indexedpropscom/program.cs#4)]  
  
 Sie können keine eigenen indizierten Eigenschaften erstellen.  Die Funktion unterstützt lediglich die Nutzung vorhandener indizierter Eigenschaften.  
  
## Beispiel  
 Der folgende Code veranschaulicht ein vollständiges Beispiel.  Weitere Informationen zum Einrichten eines Projekts, das auf die Office\-API zugreift, finden Sie unter [Gewusst wie: Zugreifen auf Office\-Interop\-Objekte mithilfe von Visual C\#\-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
 [!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/indexedpropscom/program.cs#5)]  
  
## Siehe auch  
 [Benannte und optionale Argumente](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office\-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)   
 [Gewusst wie: Zugreifen auf Office\-Interop\-Objekte mithilfe von Visual C\#\-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)   
 [Exemplarische Vorgehensweise: Office\-Programmierung](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)