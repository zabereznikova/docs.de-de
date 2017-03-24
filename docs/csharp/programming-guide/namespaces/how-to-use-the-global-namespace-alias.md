---
title: "Gewusst wie: Verwenden des globalen Namespacealias (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Aliase [C#]"
  - "Globaler Namespace [C#]"
  - "Namespaces [C#], Globaler Namespacequalifizierer"
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Gewusst wie: Verwenden des globalen Namespacealias (C#-Programmierhandbuch)
Die Fähigkeit, auf einen Member im globalen [Namespace](../../../csharp/language-reference/keywords/namespace.md) zuzugreifen, ist nützlich, wenn der Member möglicherweise durch eine Entität gleichen Namens verdeckt ist.  
  
 Im folgenden Codebeispiel wird `Console` nach `TestApp.Console` aufgelöst, statt nach dem `Console`\-Typ im <xref:System>\-Namespace.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 Auch die Verwendung von `System.Console` führt zu einem Fehler, da der `System`\-Namespace von der `TestApp.System`\-Klasse verdeckt wird:  
  
 [!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 Sie können diesen Fehler jedoch umgehen, indem Sie `global::System.Console` folgendermaßen verwenden:  
  
 [!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 Wenn der linke Bezeichner `global` ist, beginnt die Suche nach dem rechten Bezeichner im globalen Namespace.  Die folgende Deklaration verweist beispielsweise auf `TestApp` als Member des globalen Namespaces.  
  
 [!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 Offensichtlich ist vom Erstellen eines eigenen Namespaces mit dem Namen `System` abzuraten, und Sie werden auch kaum jemals auf derartigen Code treffen.  In größeren Projekten ist es allerdings durchaus möglich, dass doppelte Namespaces auf die eine oder andere Weise vorkommen können.  In diesen Situationen garantiert der globale Namespacequalifizierer, dass Sie den Stammnamespace angeben können.  
  
## Beispiel  
 In diesem Beispiel schließt der `System`\-Namespace die `TestClass`\-Klasse ein, sodass `global::System.Console` benötigt wird, um auf die `System.Console`\-Klasse zu verweisen, die durch den `System`\-Namespace verdeckt wird.  Außerdem wird mit dem Alias `colAlias` auf den `System.Collections`\-Namespace verwiesen. Deshalb wurde die Instanz von <xref:System.Collections.Hashtable?displayProperty=fullName> mit diesem Alias statt mit dem Namespace erstellt.  
  
 [!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
  **A 1**  
**B 2**  
**C 3**   
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)   
 [. Operator](../../../csharp/language-reference/operators/member-access-operator.md)   
 [Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)