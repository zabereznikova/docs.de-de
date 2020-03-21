---
title: 'Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: 495de5a926cfc0c5aab88337f5f33b991c49e71a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184992"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a>Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert
Sitzungen erstellen einen Freigabezustand zwischen zwei oder mehr Endpunkten, der nützliche Funktionen wie Rückrufe, Multi-Hop-Sicherheit und Zuordnungen zwischen Clients und Dienstinstanzen ermöglicht. Weitere Informationen zu Sitzungen in Windows Communication Foundation (WCF)-Anwendungen finden Sie unter [Verwenden von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>So geben Sie an, dass die Bindung eines Vertrags Sitzungen unterstützen muss  
  
1. Erstellen Sie einen Dienstvertrag mit mindestens einem Vorgang. Ein Beispiel für das Erstellen eines Servicevertrags finden Sie unter [Gewusst wie: Definieren eines Servicevertrags](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2. Ändern Sie <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>, das den Vertrag deklariert, durch Festlegen der <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>-Eigenschaft auf einen der folgenden Werte:  
  
    - <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, wenn dieser Vertrag innerhalb einer Sitzung ausgeführt werden muss.  
  
    - <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>, wenn dieser Vertrag innerhalb einer Sitzung ausgeführt werden kann.  
  
    - <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>, wenn dieser Vertrag nicht innerhalb einer Sitzung ausgeführt werden darf.  
  
3. Konfigurieren Sie den Dienstendpunkt so, dass er eine Bindung verwendet, die Sitzungen unterstützt. Im folgenden Konfigurationsbeispiel wird die Verwendung von <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> veranschaulicht, die eine WS`-`ReliableMessaging-Sitzung unterstützt.  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="example"></a>Beispiel  
 Der folgende Beispielcode zeigt, wie Sie mit der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>-Bindung eine Sitzungsanforderung auf Vertragsebene angeben und eine Konfigurationsdatei verwenden, um diese Anforderung zu unterstützen.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
