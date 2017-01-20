---
title: "into (C#-Referenz) | Microsoft Docs"
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
  - "into_CSharpKeyword"
  - "into"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "into-Schlüsselwort [C#]"
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# into (C#-Referenz)
Das `into`\-Kontextschlüsselwort kann zum Erstellen eines temporären Bezeichners verwendet werden, um die Ergebnisse der Klauseln [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) oder [select](../../../csharp/language-reference/keywords/select-clause.md) in einem neuen Bezeichner zu speichern.  Dieser Bezeichner kann wiederum ein Generator für zusätzliche Abfragebefehle sein.  Beim Einsatz in einer `group`\-Klausel oder `select`\-Klausel wird die Verwendung des neuen Bezeichners gelegentlich als *Fortsetzung* bezeichnet.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie das `into`\-Schlüsselwort verwenden, um einen temporären Bezeichner `fruitGroup` zu aktivieren, der über einen abgeleiteten Typ `IGrouping` verfügt.  Durch den Einsatz des Bezeichners können Sie die <xref:System.Linq.Enumerable.Count%2A>\-Methode für jede Gruppe aufrufen und nur die Gruppen auswählen, die zwei oder mehr Wörter enthalten.  
  
 [!code-cs[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/csquerykeywords/Into.cs#18)]  
  
 Der Einsatz von `into` in einer `group`\-Klausel ist nur dann notwendig, wenn Sie zusätzliche Abfrageoperationen für jede Gruppe ausführen möchten.  Weitere Informationen finden Sie unter [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md).  
  
 Ein Beispiel für den Einsatz von `into` in einer `join`\-Klausel finden Sie unter [join\-Klausel](../../../csharp/language-reference/keywords/join-clause.md).  
  
## Siehe auch  
 [Abfrageschlüsselwörter \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md)