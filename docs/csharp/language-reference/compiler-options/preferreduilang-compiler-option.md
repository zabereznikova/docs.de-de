---
title: "/preferreduilang (C# Compiler Options) | Microsoft Docs"
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
  - "/preferreduilang"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "preferreduilang compiler option [C#]"
  - "/preferreduilang compiler option [C#]"
  - "-preferreduilang compiler option [C#]"
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /preferreduilang (C# Compiler Options)
Durch die Compileroption `/preferreduilang` verwenden, können Sie die Sprache angeben, in der die C\#\-Compiler\-Anzeigenausgabe, wie Fehlermeldungen.  
  
## Syntax  
  
```  
/preferreduilang: language  
```  
  
## Argumente  
 `language`  
 [Sprachenname](http://go.microsoft.com/fwlink/p/?LinkId=236992) Von der Compilerausgabe in Sprache, verwenden.  
  
## Hinweise  
 Sie können die `/preferreduilang`\-Compileroption verwenden, die Sprache anzugeben, dass Sie den C\#\-Compiler für Fehlermeldungen und anderen Befehlszeilenausgabe verwenden soll.  Sofern das Language Pack für die Sprache nicht installiert ist, wird die Spracheinstellung des Betriebssystems stattdessen verwendet, und kein Fehler wird ausgegeben.  
  
```c#  
csc.exe /preferreduilang:ja-JP  
```  
  
## Anforderungen  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)