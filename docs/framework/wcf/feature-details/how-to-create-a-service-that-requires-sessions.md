---
title: "Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert
Sitzungen erstellen einen Freigabezustand zwischen zwei oder mehr Endpunkten, der nützliche Funktionen wie Rückrufe, Multi-Hop-Sicherheit und Zuordnungen zwischen Clients und Dienstinstanzen ermöglicht. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Sitzungen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Clientanwendungen finden Sie unter [mit Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>So geben Sie an, dass die Bindung eines Vertrags Sitzungen unterstützen muss  
  
1.  Erstellen Sie einen Dienstvertrag mit mindestens einem Vorgang. Ein Beispiel zum Erstellen eines Dienstvertrags finden Sie unter [Gewusst wie: Definieren eines Dienstvertrags](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2.  Ändern der <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName> , die den Vertrag deklariert, durch Festlegen der <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName> -Eigenschaft entweder:  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> Wenn dieser Vertrag innerhalb einer Sitzung ausgeführt werden muss.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> Wenn dieser Vertrag innerhalb einer Sitzung ausgeführt werden kann.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> Wenn dieser Vertrag nicht innerhalb einer Sitzung ausgeführt werden muss.  
  
3.  Konfigurieren Sie den Dienstendpunkt so, dass er eine Bindung verwendet, die Sitzungen unterstützt. Im folgenden Beispiel veranschaulicht die Verwendung von der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName>, die eine WS unterstützt`-`ReliableMessaging-Sitzung.  
  
     <!-- TODO: review snippet reference [!code[SCA.Session#2](../../../../samples/snippets/common/VS_Snippets_CFX/sca.session/common/hostapplication.exe.config#2)]  -->
     <!-- TODO: review snippet reference [!code-csharp[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]  -->
     <!-- TODO: review snippet reference [!code-vb[SCA.Session#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/hostapplication.exe.config#2)]  -->  
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode zeigt, wie eine sitzungsanforderung auf Vertragsebene angeben und eine Konfigurationsdatei verwenden, unterstützt diese Anforderung mit der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName> Bindung.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]  
  
 <!-- TODO: review snippet reference [!code[SCA.Session#2](../../../../samples/snippets/common/VS_Snippets_CFX/sca.session/common/hostapplication.exe.config#2)]  -->
 <!-- TODO: review snippet reference [!code-csharp[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]  -->
 <!-- TODO: review snippet reference [!code-vb[SCA.Session#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/hostapplication.exe.config#2)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName>   
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.SessionMode?displayProperty=fullName>