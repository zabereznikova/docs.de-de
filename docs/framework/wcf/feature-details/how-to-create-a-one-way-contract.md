---
title: "Vorgehensweise: Erstellen eines unidirektionalen Vertrags | Microsoft Docs"
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
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Vorgehensweise: Erstellen eines unidirektionalen Vertrags
Dieses Thema zeigt die grundlegenden Schritte zum Erstellen von Methoden, die einen unidirektionalen Vertrag verwenden.Solche Methoden rufen Vorgänge in einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst von einem Client auf, erwarten aber keine Antwort.Dieser Vertragstyp kann verwendet werden, um z. B. Benachrichtigungen für viele Abonnenten zu veröffentlichen.Sie können unidirektionale Verträge auch beim Erstellen eines Duplexvertrags \(bidirektionalen Vertrags\) verwenden. Dies ermöglicht eine unabhängige Kommunikation zwischen Clients und Servern, sodass beide Aufrufe des jeweils anderen initiieren können.So wird insbesondere dem Server ermöglicht, unidirektionale Aufrufe an den Client durchzuführen, die der Client als Ereignisse behandeln kann.Ausführliche Informationen zum Angeben von unidirektionalen Methoden finden Sie in der Beschreibung zur <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>\-Methode und zur <xref:System.ServiceModel.OperationContractAttribute>\-Klasse.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen einer Clientanwendung für einen Duplexvertrag finden Sie unter [Vorgehensweise: Zugreifen auf Dienste mit unidirektionalen und Anforderung\-Antwort\-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md).Ein Arbeitsbeispiel finden Sie im Beispiel [Unidirektional](../../../../docs/framework/wcf/samples/one-way.md).  
  
### So erstellen Sie einen unidirektionalen Vertrag  
  
1.  Erstellen Sie einen Dienstvertrag, indem Sie die <xref:System.ServiceModel.ServiceContractAttribute>\-Klasse auf die Schnittstelle anwenden, die die Methoden definiert, die der Dienst implementieren soll.  
  
2.  Geben Sie an, welche Methoden in der Schnittstelle ein Client aufrufen kann, indem Sie die <xref:System.ServiceModel.OperationContractAttribute>\-Klasse auf die Methoden anwenden.  
  
3.  Definieren Sie die Vorgänge, die keine unidirektionale Ausgabe \(keinen Rückgabewert und keine out\- oder ref\-Parameter\) haben dürfen, indem Sie die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>\-Eigenschaft auf `true` festlegen.Beachten Sie, dass alle Vorgänge mit der <xref:System.ServiceModel.OperationContractAttribute>\-Klasse standardmäßig einen Anforderung\-Antwort\-Vertrag erfüllen, weil die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>\-Eigenschaft standardmäßig `false` lautet.Wenn Sie einen unidirektionalen Vertrag für die Methode definieren möchten, müssen Sie den Wert der Attributeigenschaft folglich explizit auf `true` festlegen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein Vertrag für einen Dienst definiert, der mehrere unidirektionale Methoden besitzt.Alle diese Methoden haben unidirektionale Verträge mit Ausnahme von `Equals`, das standardmäßig auf Anforderung\-Antwort festgelegt ist und ein Ergebnis zurückgibt.  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## Siehe auch  
 <xref:System.ServiceModel.ServiceContractAttribute>   
 <xref:System.ServiceModel.OperationContractAttribute>   
 [Entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md)   
 [Gewusst wie: Definieren eines Dienstvertrags](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)   
 [Sitzung](../../../../docs/framework/wcf/samples/session.md)   
 [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)