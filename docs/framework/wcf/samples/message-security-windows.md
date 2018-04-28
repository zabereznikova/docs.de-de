---
title: Nachrichtensicherheit – Windows
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
caps.latest.revision: 34
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: d42f266e51f6d5dd8c772d674736adc729b2ac2c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="message-security-windows"></a><span data-ttu-id="2aa6e-102">Nachrichtensicherheit – Windows</span><span class="sxs-lookup"><span data-stu-id="2aa6e-102">Message Security Windows</span></span>
<span data-ttu-id="2aa6e-103">In diesem Beispiel wird veranschaulicht, wie eine <xref:System.ServiceModel.WSHttpBinding>-Bindung konfiguriert wird, um mit Windows-Authentifizierung Sicherheit auf Nachrichtenebene zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-103">This sample demonstrates how to configure a <xref:System.ServiceModel.WSHttpBinding> binding to use message-level security with Windows authentication.</span></span> <span data-ttu-id="2aa6e-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="2aa6e-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="2aa6e-105">In diesem Beispiel wird der Dienst in Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).</span><span class="sxs-lookup"><span data-stu-id="2aa6e-105">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2aa6e-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2aa6e-107">Die Standardsicherheit für die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) ist nachrichtensicherheit, die mithilfe der Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-107">The default security for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) is message security using Windows authentication.</span></span> <span data-ttu-id="2aa6e-108">Legen Sie die Konfigurationsdateien in diesem Beispiel explizit die `mode` Attribut des der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) zu `Message` und die `clientCredentialType` -Attribut auf `Windows`.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-108">The configuration files in this sample explicitly set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) to `Message` and the `clientCredentialType` attribute to `Windows`.</span></span> <span data-ttu-id="2aa6e-109">Diese Werte sind die Standardwerte für diese Bindung, wurden allerdings, wie in der folgenden Beispielkonfiguration zur Veranschaulichung ihrer Verwendung, explizit konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-109">These values are the default values for this binding, but they have been explicitly configured, as shown in the following sample configuration to demonstrate their use.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="2aa6e-110">Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-110">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="2aa6e-111">Die Clientbindung wird mit dem entsprechenden `securityMode` und `authenticationMode` konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-111">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"   
            binding="wsHttpBinding"   
            bindingConfiguration="Binding1"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      <!--The default security for the WSHttpBinding is-->  
      <!--Message security using Windows authentication. -->  
      <!--This configuration explicitly defines the security mode -->  
      <!--as Message and the clientCredentialType as Windows  -->  
      <!--for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="2aa6e-112">Der Quellcode für den Dienst wurde geändert, um zu veranschaulichen, wie <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> verwendet werden kann, um auf die Identität des Aufrufers zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-112">The service source code has been modified to demonstrate how the <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> can be used to access the identity of the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="2aa6e-113">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="2aa6e-114">Die erste aufgerufene Methode – `GetCallerIdentity` – gibt den Namen der Identität des Aufrufers zurück an den Client.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-114">The first method called - `GetCallerIdentity` - returns the name of the caller identity back to the client.</span></span> <span data-ttu-id="2aa6e-115">Drücken Sie im Konsolenfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-115">Press ENTER in the console window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2aa6e-116">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="2aa6e-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2aa6e-117">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2aa6e-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="2aa6e-118">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2aa6e-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="2aa6e-119">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2aa6e-119">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa6e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aa6e-120">See Also</span></span>
