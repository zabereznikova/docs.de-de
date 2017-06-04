---
title: "How to: Wrap EAP Patterns in a Task | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, how to wrap EAP patterns"
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Wrap EAP Patterns in a Task
Das folgende Beispiel zeigt, wie eine beliebige Sequenz von Vorgängen des ereignisbasierten asynchronen Muster \(EAP\) als eine Aufgabe verfügbar gemacht, indem es <xref:System.Threading.Tasks.TaskCompletionSource%601> verwendet.  Darüber hinaus wird in dem Beispiel gezeigt, wie Sie mit einem <xref:System.Threading.CancellationToken> die integrierten Abbruchmethoden für die <xref:System.Net.WebClient>\-Objekte aufrufen.  
  
## Beispiel  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## Siehe auch  
 [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)