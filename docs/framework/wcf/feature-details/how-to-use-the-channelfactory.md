---
title: "Vorgehensweise: Verwenden der ChannelFactory | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Vorgehensweise: Verwenden der ChannelFactory
Die generische <xref:System.ServiceModel.ChannelFactory%601>\-Klasse wird in komplexen Szenarien verwendet, in denen eine Kanalfactory erstellt werden muss, die zum Erstellen mehrerer Kanäle eingesetzt werden kann.  
  
### So erstellen und verwenden Sie die ChannelFactory\-Klasse  
  
1.  Erstellen Sie einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst, und führen Sie ihn aus.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Konfigurieren von Diensten](../../../../docs/framework/wcf/configuring-services.md) und [Hosting\-Dienste](../../../../docs/framework/wcf/hosting-services.md).  
  
2.  Verwenden Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), um den Vertrag \(Schnittstelle\) für den Client zu generieren.  
  
3.  Verwenden Sie im Clientcode die <xref:System.ServiceModel.ChannelFactory%601>\-Klasse, um mehrere Endpunktlistener zu erstellen.  
  
## Beispiel  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]