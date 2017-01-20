---
title: "value (C#-Referenz) | Microsoft Docs"
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
  - "value_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "value-Schlüsselwort [C#]"
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# value (C#-Referenz)
Das kontextbezogene Schlüsselwort `value` wird im set\-Accessor in herkömmlichen Eigenschaftendeklarationen verwendet.  Es ähnelt einem Eingabeparameter in einer Methode.  Das Wort `value` verweist auf den Wert, der der Eigenschaft vom Clientcode zugewiesen werden soll.  `MyDerivedClass` verfügt im folgenden Beispiel über die Eigenschaft `Name`, die dem Sicherungsspeicher `name` mit dem `value`\-Parameter eine neue Zeichenfolge zuweist.  Aus der Clientcodeperspektive wird der Vorgang als einfache Zuweisung geschrieben.  
  
 [!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#26)]  
  
 Nähere Informationen zur Verwendung von `value` finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)