---
title: "Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs
In [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendungen kann ein Dienstvorgang asynchron oder synchron implementiert werden, ohne dem Client vorzuschreiben, wie er ihn aufzurufen hat.So können z. B. asynchrone Dienstvorgänge synchron aufrufen, und synchrone Dienstvorgänge können asynchron aufgerufen werden.Ein Beispiel für das asynchrone Aufrufen eines Vorgangs in einer Clientanwendung finden Sie unter [Vorgehensweise: Asynchrones Aufrufen von Dienstvorgängen](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu synchronen und asynchronen Vorgängen finden Sie unter [Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md) und [Synchrone und asynchrone Vorgänge](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).In diesem Thema wird die grundlegende Struktur eines asynchronen Dienstvorgangs beschrieben \(der Code ist nicht vollständig\).Ein ausführliches Beispiel für den Dienst und den Client finden Sie unter [Asynchronous](http://msdn.microsoft.com/de-de/833db946-f511-4f64-a26f-2759a11217c7).  
  
### Asynchrones Implementieren eines Dienstvorgangs  
  
1.  Deklarieren Sie im Dienstvertrag ein asynchrones Methodenpaar entsprechend den .NET\-Richtlinien für den asynchronen Entwurf.Die Methode `Begin` nimmt einen Parameter, ein Rückrufobjekt und ein Statusobjekt und gibt eine <xref:System.IAsyncResult?displayProperty=fullName>\-Methode und eine entsprechende `End`\-Methode aus, die ein <xref:System.IAsyncResult?displayProperty=fullName> nimmt und den Rückgabewert ausgibt.Weitere Informationen zu asynchronen Anrufen finden Sie unter [Entwurfsmuster für die asynchrone Programmierung](http://go.microsoft.com/fwlink/?LinkId=248221).  
  
2.  Markieren Sie die Methode `Begin` des asynchronen Methodenpaars mit dem Attribut <xref:System.ServiceModel.OperationContractAttribute?displayProperty=fullName>, und legen Sie die Eigenschaft <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=fullName> auf `true` fest.Der folgende Code führt beispielsweise die Schritte 1 und 2 aus.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3.  Implementieren Sie das Methodenpaar `Begin/End` in Ihrer Dienstklasse gemäß den asynchronen Entwurfsrichtlinien von .NET.Das folgende Codebeispiel zeigt eine Implementierung, in der eine Zeichenkette sowohl in den Teilen `Begin` als auch `End` des asynchronen Dienstvorgangs auf die Konsole geschrieben ist, und der Rückgabewert des Vorgangs `End` wird an den Client ausgegeben.Das vollständige Codebeispiel finden Sie im Abschnitt "Beispiel".  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## Beispiel  
 Das folgende Codebeispiel zeigt:  
  
1.  Eine Dienstvertragschnittstelle mit:  
  
    1.  Einem synchronen `SampleMethod`\-Vorgang.  
  
    2.  Einem asynchronen `BeginSampleMethod`\-Vorgang.  
  
    3.  Einem asynchronen `BeginServiceAsyncMethod`\/`EndServiceAsyncMethod`\-Vorgangspaar.  
  
2.  Einer Dienstimplementierung mit einem <xref:System.IAsyncResult?displayProperty=fullName>\-Objekt.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## Siehe auch  
 [Entwerfen von Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md)   
 [Synchrone und asynchrone Vorgänge](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)