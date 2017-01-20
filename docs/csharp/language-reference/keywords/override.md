---
title: "override (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "override"
  - "override_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "override-Schlüsselwort [C#]"
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# override (C#-Referenz)
Der `override`\-Modifizierer wird benötigt, um die abstrakte oder virtuelle Implementierung einer geerbten Methode oder Eigenschaft bzw. eines geerbten Indexers oder Ereignisses zu erweitern oder zu ändern.  
  
## Beispiel  
 In diesem Beispiel muss die `Square`\-Klasse eine überschriebene Implementierung von `Area` bereitstellen, da `Area` von der abstrakten `ShapesClass` geerbt wird:  
  
 [!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#1)]  
  
 Eine `override`\-Methode stellt eine neue Implementierung eines von einer Basisklasse geerbten Members bereit.  Die durch eine `override`\-Deklaration überschriebene Methode wird als überschriebene Basismethode bezeichnet.  Diese muss dieselbe Signatur wie die `override`\-Methode aufweisen.  Weitere Informationen über die Vererbung finden Sie unter [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Eine nicht virtuelle oder statische Methode darf nicht überschrieben werden.  Bei der überschriebenen Basismethode muss es sich um eine `virtual`\-, `abstract`\- oder `override`\-Methode handeln.  
  
 Der Zugriff auf die `virtual`\-Methode kann durch eine `override`\-Deklaration nicht geändert werden.  Die `override`\-Methode und die `virtual`\-Methode müssen denselben [Zugriffsebenenmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md) aufweisen.  
  
 Zum Ändern einer `override`\-Methode können Sie nicht die Modifizierer `new`, `static` oder `virtual` verwenden.  
  
 Eine überschreibende Eigenschaftendeklaration muss genau denselben Zugriffsmodifizierer, Typ und Namen wie die geerbte Eigenschaft verwenden, und bei der überschriebenen Eigenschaft muss es sich um eine der Eigenschaften `virtual`, `abstract` oder `override` handeln.  
  
 Weitere Informationen zum Verwenden des `override`\-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern "override" und "new"](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter "Override" und "New" verwendet werden?](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## Beispiel  
 Im folgenden Beispiel werden die Basisklasse `Employee` und die abgeleitete Klasse `SalesEmployee` definiert.  Die `SalesEmployee`\-Klasse enthält die zusätzliche `salesbonus`\-Eigenschaft. Um diese zu berücksichtigen, überschreibt sie die `CalculatePay`\-Methode.  
  
 [!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#9)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)   
 [Virtuell](../../../csharp/language-reference/keywords/virtual.md)   
 [neu](../../../csharp/language-reference/keywords/new.md)   
 [Polymorphismus](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)