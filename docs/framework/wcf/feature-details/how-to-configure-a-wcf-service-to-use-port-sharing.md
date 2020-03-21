---
title: 'Vorgehensweise: Konfigurieren eines Windows Communication Foundation-Dienstes zum Durchführen der Anschlussfreigabe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
ms.openlocfilehash: cd8d76137ac195e452a7d66fb6ddbeda405a922f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185091"
---
# <a name="how-to-configure-a-windows-communication-foundation-service-to-use-port-sharing"></a>Vorgehensweise: Konfigurieren eines Windows Communication Foundation-Dienstes zum Durchführen der Anschlussfreigabe
Die einfachste Möglichkeit, die Portfreigabe von net.tcp://in Ihrer Windows Communication Foundation <xref:System.ServiceModel.NetTcpBinding>(WCF)-Anwendung zu verwenden, besteht darin, einen Dienst mithilfe der verfügbar zu machen.  
  
 Diese Bindung verfügt über eine <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A>-Eigenschaft, die festlegt, ob die net.tcp://-Anschlussfreigabe für den mit dieser Bindung zu konfigurierenden Dienst aktiviert ist.  
  
 Der folgende Vorgang zeigt, wie Sie die <xref:System.ServiceModel.NetTcpBinding>-Klasse zum Öffnen eines Endpunkts am Uniform Resource Identifier (URI) net.tcp://localhost/MyService verwenden können, zuerst im Code und dann mithilfe von Konfigurationselementen.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-code"></a>So aktivieren Sie die net.tcp://-Anschlussfreigabe für eine NetTcpBinding im Code  
  
1. Erstellen Sie einen Dienst, `IMyService` um `MyService`einen Vertrag namens zu implementieren und ihn aufzurufen .  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2. Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A>-Eigenschaft auf `true` fest.  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3. Erstellen Sie einen <xref:System.ServiceModel.ServiceHost>, und fügen Sie ihm den Dienstendpunkt für `MyService` hinzu, der die <xref:System.ServiceModel.NetTcpBinding>, für die die Anschlussfreigabe aktiviert wurde, verwendet und der am Endpunkt-Adress-URI "net.tcp://localhost/MyService" eine Abhörung durchführt.  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    > In diesem Beispiel wird der Standard-TCP-Anschluss 808 verwendet, da der Endpunkt-Adress-URI keine andere Anschlussnummer angibt. Da die Anschlussfreigabe explizit für die Transportbindung aktiviert wurde, kann dieser Dienst den Anschluss 808 für andere Dienste in anderen Vorgängen freigeben. Wenn die Anschlussfreigabe nicht zulässig wäre und eine andere Anwendung bereits den Anschluss 808 verwenden würde, würde dieser Dienst beim Öffnen eine <xref:System.ServiceModel.AddressAlreadyInUseException> ausgeben.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-configuration"></a>So aktivieren Sie die net.tcp://-Anschlussfreigabe für eine NetTcpBinding in der Konfiguration  
  
1. Das folgende Beispiel zeigt, wie Sie die Anschlussfreigabe aktivieren und den Dienstendpunkt mithilfe von Konfigurationselementen hinzufügen können.  
  
```xml  
<system.serviceModel>  
  <bindings>  
    <netTcpBinding name="portSharingBinding"
                   portSharingEnabled="true" />  
  </bindings>  
  <services>  
    <service name="MyService">  
        <endpoint address="net.tcp://localhost/MyService"  
                  binding="netTcpBinding"  
                  contract="IMyService"  
                  bindingConfiguration="portSharingBinding" />  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Net.TCP-Portfreigabe](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)
