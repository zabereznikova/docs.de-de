---
title: "extern-Alias (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "alias_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Aliase [C#], extern-Schlüsselwort"
  - "Aliase, extern-Schlüsselwort"
  - "extern alias-Schlüsselwort [C#]"
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# extern-Alias (C#-Referenz)
Unter Umständen müssen Sie auf zwei Versionen von Assemblys verweisen, die über die gleichen vollqualifizierten Typnamen verfügen.  So kann es beispielsweise vorkommen, dass Sie zwei oder mehr Versionen einer Assembly in derselben Anwendung verwenden müssen.  Durch Verwendung eines externen Assemblyaliases können die jeweiligen Namespaces der Assemblys innerhalb von Namespaces unter dem Namen des Aliases auf Stammebene umschlossen werden, sodass sie in derselben Datei verwendet werden können.  
  
> [!NOTE]
>  Das [extern](../../../csharp/language-reference/keywords/extern.md)\-Schlüsselwort wird auch als Methodenmodifizierer verwendet, um eine Methode zu deklarieren, die in nicht verwaltetem Code geschrieben wurde.  
  
 Um auf zwei Assemblys mit demselben voll qualifizierten Typnamen zu verweisen, muss ein Alias in einer Befehlseingabeaufforderung folgendermaßen angegeben werden:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 Dies erstellt die externen Aliase `GridV1` und `GridV2`.  Um diese Aliase aus einem Programm heraus zu verwenden, verweisen Sie auf sie mithilfe des `extern`\-Schlüsselworts.  Beispiele:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Jede externe Aliasdeklaration führt einen zusätzlichen Namespace auf Stammebene ein, der dem globalen Namespace entspricht, aber nicht in diesem enthalten ist.  Somit kann auf Typen jeder Assembly eindeutig unter Verwendung des voll qualifizierten Namens zugegriffen werden, der seinen Stamm im entsprechenden Namespacealias hat.  
  
 Im vorherigen Beispiel wäre `GridV1::Grid` das Steuerelement von `grid.dll` und `GridV2::Grid` das von `grid20.dll`.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Namespaceschlüsselwörter](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)