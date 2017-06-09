---
title: "Abrufen von Setupinformationen aus einer Anwendungsdom&#228;ne | Microsoft Docs"
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
  - "AppDomainSetup-Objekt"
  - "Anwendungsdomänen, Abrufen von Setupinformationen"
  - "Abrufen von Setupinformationen"
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Abrufen von Setupinformationen aus einer Anwendungsdom&#228;ne
Instanzen von Anwendungsdomänen bestehen aus Eigenschaften und <xref:System.AppDomainSetup>\-Informationen.  Sie können Setupinformationen aus einer Anwendungsdomäne abrufen, indem Sie die <xref:System.AppDomain?displayProperty=fullName>\-Klasse verwenden.  Diese Klasse stellt verschiedene Member bereit, die Konfigurationsinformationen zu einer Anwendungsdomäne abrufen können.  
  
 Sie können auch das **AppDomainSetup**\-Objekt für die Anwendungsdomäne abfragen, um Setupinformationen zu erhalten, die an die Domäne während deren Erstellung übergeben wurden.  
  
 Im folgenden Codebeispiel wird eine neue Anwendungsdomäne erstellt. Anschließend werden einige Memberwerte auf der Konsole ausgegeben.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 Im folgenden Codebeispiel werden für eine Anwendungsdomäne Setupinformationen eingestellt und anschließend abgerufen.  Beachten Sie, dass `AppDomain.SetupInformation.ApplicationBase` die Konfigurationsinformationen erhält.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## Siehe auch  
 [Hosting Overview](http://msdn.microsoft.com/de-de/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/de-de/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)