---
title: "Gewusst wie: Erstellen einer Anwendungsdom&#228;ne | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungsdomänen, Erstellen"
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen einer Anwendungsdom&#228;ne
Ein Common Language Runtime\-Host erstellt Anwendungsdomänen automatisch bei Bedarf.  Sie können allerdings auch eigene Anwendungsdomänen erstellen und diese in die Assemblys laden, die Sie persönlich verwalten möchten.  Darüber hinaus können Sie Anwendungsdomänen erstellen, aus denen heraus Code ausgeführt werden kann.  
  
 Sie erstellen eine neue Anwendungsdomäne, indem Sie eine der überladenen **CreateDomain**\-Methoden der <xref:System.AppDomain?displayProperty=fullName>\-Klasse verwenden.  Sie können der Anwendungsdomäne einen Namen zuweisen und durch dessen Verwendung auf die Domäne verweisen.  
  
 Im folgenden Codebeispiel wird eine neue Anwendungsdomäne erstellt, und es wird ihr der Name `MyDomain` zugewiesen. Anschließend wird der Name der Hostdomäne und der neu erstellten, untergeordneten Anwendungsdomäne auf der Konsole ausgegeben.  
  
## Beispiel  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## Siehe auch  
 [Hosting Overview](http://msdn.microsoft.com/de-de/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/de-de/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)