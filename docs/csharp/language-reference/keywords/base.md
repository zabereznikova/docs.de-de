---
title: "base (C#-Referenz) | Microsoft Docs"
description: base keyword (C#)
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "base"
  - "BaseClass.BaseClass"
  - "base_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "base-Schlüsselwort [C#]"
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# base (C#-Referenz)
Mit dem `base`\-Schlüsselwort kann innerhalb einer abgeleiteten Klasse auf Member der Basisklasse zugegriffen werden:  
  
-   Rufen Sie eine Methode der Basisklasse auf, die durch eine andere Methode überschrieben wurde.  
  
-   Geben Sie an, welcher Konstruktor der Basisklasse beim Erstellen von Instanzen der abgeleiteten Klasse aufgerufen werden soll.  
  
 Ein Zugriff auf eine Basisklasse ist nur in einem Konstruktor, einer Instanzenmethode oder einem Instanzeneigenschaften\-Accessor zulässig.  
  
 Das `base`\-Schlüsselwort darf nicht innerhalb einer statischen Methode verwendet werden.  
  
 Die Basisklasse, auf die zugegriffen wird, ist die in der Klassendeklaration angegebene Basisklasse.  Wenn Sie z. B. `class ClassB : ClassA` angeben, wird auf die Member von ClassA aus ClassB zugegriffen, unabhängig von der Basisklasse von ClassA.  
  
## Beispiel  
 In diesem Beispiel verfügen sowohl die `Person`\-Basisklasse als auch die abgeleitete `Employee`\-Klasse über eine Methode mit der Bezeichnung `Getinfo`.  Mithilfe des `base`\-Schlüsselworts kann die `Getinfo`\-Methode für die Basisklasse aus der abgeleiteten Klasse aufgerufen werden.  
  
 [!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/csharp/base_1.cs)]  
  
 Weitere Beispiele finden Sie unter [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) und [override](../../../csharp/language-reference/keywords/override.md).  
  
## Beispiel  
 In diesem Beispiel wird gezeigt, wie der aufgerufene Basisklassenkonstruktor angegeben werden kann, wenn Instanzen einer abgeleiteten Klasse erstellt werden.  
  
 [!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/csharp/base_2.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [this](../../../csharp/language-reference/keywords/this.md)