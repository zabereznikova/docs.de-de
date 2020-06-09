---
title: 'Vorgehensweise: Konfigurieren eines Windows Communication Foundation-Dienstes zum Durchführen der Anschlussfreigabe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
ms.openlocfilehash: 28f2858d68de99839d7fec66b0fe4528d7e42325
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579526"
---
# <a name="how-to-configure-a-windows-communication-foundation-service-to-use-port-sharing"></a><span data-ttu-id="e9b21-102">Vorgehensweise: Konfigurieren eines Windows Communication Foundation-Dienstes zum Durchführen der Anschlussfreigabe</span><span class="sxs-lookup"><span data-stu-id="e9b21-102">How to: Configure a Windows Communication Foundation Service to Use Port Sharing</span></span>
<span data-ttu-id="e9b21-103">Die einfachste Möglichkeit zur Verwendung von net. TCP://-Port Freigabe in Ihrer Windows Communication Foundation (WCF)-Anwendung besteht darin, einen Dienst mit dem verfügbar zu machen <xref:System.ServiceModel.NetTcpBinding> .</span><span class="sxs-lookup"><span data-stu-id="e9b21-103">The easiest way to use net.tcp:// port sharing in your Windows Communication Foundation (WCF) application is to expose a service using the <xref:System.ServiceModel.NetTcpBinding>.</span></span>  
  
 <span data-ttu-id="e9b21-104">Diese Bindung verfügt über eine <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A>-Eigenschaft, die festlegt, ob die net.tcp://-Anschlussfreigabe für den mit dieser Bindung zu konfigurierenden Dienst aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e9b21-104">This binding provides a <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property that controls whether net.tcp:// port sharing is enabled for the service being configured with this binding.</span></span>  
  
 <span data-ttu-id="e9b21-105">Der folgende Vorgang zeigt, wie Sie die <xref:System.ServiceModel.NetTcpBinding>-Klasse zum Öffnen eines Endpunkts am Uniform Resource Identifier (URI) net.tcp://localhost/MyService verwenden können, zuerst im Code und dann mithilfe von Konfigurationselementen.</span><span class="sxs-lookup"><span data-stu-id="e9b21-105">The following procedure shows how to use the <xref:System.ServiceModel.NetTcpBinding> class to open an endpoint at the Uniform Resource Identifier (URI) net.tcp://localhost/MyService, first in code and then by using configuration elements.</span></span>  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-code"></a><span data-ttu-id="e9b21-106">So aktivieren Sie die net.tcp://-Anschlussfreigabe für eine NetTcpBinding im Code</span><span class="sxs-lookup"><span data-stu-id="e9b21-106">To enable net.tcp:// port sharing on a NetTcpBinding in code</span></span>  
  
1. <span data-ttu-id="e9b21-107">Erstellen Sie einen Dienst, um einen Vertrag namens zu implementieren `IMyService` , und rufen Sie ihn auf `MyService` .</span><span class="sxs-lookup"><span data-stu-id="e9b21-107">Create a service to implement a contract called `IMyService` and call it `MyService`, .</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2. <span data-ttu-id="e9b21-108">Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A>-Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="e9b21-108">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property to `true`.</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3. <span data-ttu-id="e9b21-109">Erstellen Sie einen <xref:System.ServiceModel.ServiceHost>, und fügen Sie ihm den Dienstendpunkt für `MyService` hinzu, der die <xref:System.ServiceModel.NetTcpBinding>, für die die Anschlussfreigabe aktiviert wurde, verwendet und der am Endpunkt-Adress-URI "net.tcp://localhost/MyService" eine Abhörung durchführt.</span><span class="sxs-lookup"><span data-stu-id="e9b21-109">Create a <xref:System.ServiceModel.ServiceHost> and add the service endpoint to it for `MyService` that uses the port sharing-enabled <xref:System.ServiceModel.NetTcpBinding> and that listens at the endpoint address URI "net.tcp://localhost/MyService".</span></span>  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    > <span data-ttu-id="e9b21-110">In diesem Beispiel wird der Standard-TCP-Anschluss 808 verwendet, da der Endpunkt-Adress-URI keine andere Anschlussnummer angibt.</span><span class="sxs-lookup"><span data-stu-id="e9b21-110">This example uses the default TCP port of 808 because the endpoint address URI does not specify a different port number.</span></span> <span data-ttu-id="e9b21-111">Da die Anschlussfreigabe explizit für die Transportbindung aktiviert wurde, kann dieser Dienst den Anschluss 808 für andere Dienste in anderen Vorgängen freigeben.</span><span class="sxs-lookup"><span data-stu-id="e9b21-111">Because port sharing is explicitly enabled on the transport binding, this service can share port 808 with other services in other processes.</span></span> <span data-ttu-id="e9b21-112">Wenn die Anschlussfreigabe nicht zulässig wäre und eine andere Anwendung bereits den Anschluss 808 verwenden würde, würde dieser Dienst beim Öffnen eine <xref:System.ServiceModel.AddressAlreadyInUseException> ausgeben.</span><span class="sxs-lookup"><span data-stu-id="e9b21-112">If port sharing were not allowed and another application were already using port 808, this service would throw an <xref:System.ServiceModel.AddressAlreadyInUseException> when it was opened.</span></span>  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-configuration"></a><span data-ttu-id="e9b21-113">So aktivieren Sie die net.tcp://-Anschlussfreigabe für eine NetTcpBinding in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e9b21-113">To enable net.tcp:// port sharing on a NetTcpBinding in configuration</span></span>  
  
1. <span data-ttu-id="e9b21-114">Das folgende Beispiel zeigt, wie Sie die Anschlussfreigabe aktivieren und den Dienstendpunkt mithilfe von Konfigurationselementen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="e9b21-114">The following example shows how to enable port sharing and add the service endpoint using configuration elements.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9b21-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9b21-115">See also</span></span>

- [<span data-ttu-id="e9b21-116">Net.TCP-Anschlussfreigabe</span><span class="sxs-lookup"><span data-stu-id="e9b21-116">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)
- [<span data-ttu-id="e9b21-117">Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts</span><span class="sxs-lookup"><span data-stu-id="e9b21-117">How to: Enable the Net.TCP Port Sharing Service</span></span>](how-to-enable-the-net-tcp-port-sharing-service.md)
