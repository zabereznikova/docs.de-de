---
title: "Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly | Microsoft Docs"
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
  - "Assemblys [.NET Framework], Abrufen von Informationen aus"
  - "Abrufen von Assemblyinformationen"
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly
Der <xref:System.Reflection>\-Namespace enthält viele Methoden, mit denen Sie Informationen aus einer Assembly erhalten können.  In diesem Abschnitt wird eine dieser Methoden vorgestellt.  Zusätzliche Informationen finden Sie unter [Übersicht über Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md).  
  
 Mit dem folgenden Beispielcode werden Typ\- und Memberinformationen aus einer Assembly abgerufen.  
  
## Beispiel  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## Siehe auch  
 [Hosting Overview](http://msdn.microsoft.com/de-de/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/de-de/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)