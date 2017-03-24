---
title: "add (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "add_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Add-Ereignisaccessor [C#]"
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# add (C#-Referenz)
Mit dem `add`\-Kontextschlüsselwort wird ein benutzerdefinierter Ereignisaccessor definiert, der aufgerufen wird, wenn das [Ereignis](../../../csharp/language-reference/keywords/event.md) von Clientcode abonniert wird.  Wenn Sie einen benutzerdefinierten `add`\-Accessor angeben, müssen Sie auch einen [remove](../../../csharp/language-reference/keywords/remove.md)\-Accessor angeben.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Ereignis mit benutzerdefinierten `add`\-Accessoren und benutzerdefinierten [remove](../../../csharp/language-reference/keywords/remove.md)\-Accessoren veranschaulicht.  Das vollständige Beispiel finden Sie unter [Gewusst wie: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/add_1.cs)]  
  
 Normalerweise müssen Sie keine eigenen benutzerdefinierten Ereignisaccessoren bereitstellen.  Die Accessoren, die vom Compiler beim Deklarieren eines Ereignisses automatisch generiert werden, sind in den meisten Szenarios ausreichend.  
  
## Siehe auch  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)