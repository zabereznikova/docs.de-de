---
title: "Gewusst wie: Konfigurieren einer Anwendungsdom&#228;ne | Microsoft Docs"
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
  - "Anwendungsdomänen, Konfigurieren"
  - "ApplicationBase-Eigenschaft"
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Konfigurieren einer Anwendungsdom&#228;ne
Sie können der Common Language Runtime Konfigurationsinformationen für eine neue Anwendungsdomäne über die <xref:System.AppDomainSetup>\-Klasse zur Verfügung stellen.  Beim Erstellen Ihrer eigenen Anwendungsdomänen ist die <xref:System.AppDomainSetup.ApplicationBase%2A>\-Eigenschaft am wichtigsten.  Alle anderen **AppDomainSetup**\-Eigenschaften werden hauptsächlich von Common Language Runtime\-Hosts zum Konfigurieren einer bestimmten Anwendungsdomäne verwendet.  
  
 Die **ApplicationBase**\-Eigenschaft legt das Stammverzeichnis der Anwendung fest.  Erhält die Common Language Runtime eine Typanforderung, wird in dem durch die **ApplicationBase**\-Eigenschaft angegebenen Verzeichnis nach der Assembly gesucht, die diesen Typ enthält.  
  
> [!NOTE]
>  Eine neue Anwendungsdomäne erbt ausschließlich die **ApplicationBase**\-Eigenschaft des Erstellers.  
  
 Im folgenden Codebeispiel wird eine Instanz der **AppDomainSetup**\-Klasse erzeugt, die zum Erstellen einer neuen Anwendungsdomäne verwendet wird. Anschließend werden die Informationen auf der Konsole ausgegeben, und die Anwendungsdomäne wird entladen.  
  
## Beispiel  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## Siehe auch  
 [Hosting Overview](http://msdn.microsoft.com/de-de/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/de-de/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)