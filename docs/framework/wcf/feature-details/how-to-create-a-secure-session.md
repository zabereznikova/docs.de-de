---
title: 'Vorgehensweise: Erstellen einer sicheren Sitzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: c2e2b34c1d1589f26f3aea80384b5a96f1c64fb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544717"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="fde5a-102">Vorgehensweise: Erstellen einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="fde5a-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="fde5a-103">Mit Ausnahme von der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binden, verwenden die vom System bereitgestellten Bindungen in der Windows Communication Foundation (WCF) automatisch sichere Sitzungen, wenn die nachrichtensicherheit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fde5a-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="fde5a-104">Standardmäßig überleben sichere Sitzungen keine Webserver, die wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fde5a-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="fde5a-105">Wenn eine sichere Sitzung eingerichtet wird, speichern der Client und der Dienst den Schlüssel zwischen, der der sicheren Sitzung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fde5a-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="fde5a-106">Beim Austauschen der Nachrichten wird nur ein Bezeichner des zwischengespeicherten Schlüssels ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="fde5a-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="fde5a-107">Wenn der Webserver wiederverwendet wird, wird der Cache ebenfalls wiederverwendet. Der Webserver kann den im Cache zwischengespeicherten Schlüssel für den Bezeichner dann nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="fde5a-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="fde5a-108">Wenn dies geschieht, wird für den Client eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fde5a-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="fde5a-109">Sichere Sitzungen, die ein zustandsbehaftetes Token für den Sicherheitskontext verwenden, bleiben auch nach Wiederverwenden eines Webservers aktiv.</span><span class="sxs-lookup"><span data-stu-id="fde5a-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="fde5a-110">Weitere Informationen zur Verwendung eines zustandsbehafteten SCT in sicheren Sitzungen finden Sie unter [Vorgehensweise: Erstellen Sie einen Sicherheitskontext für eine sichere Sitzung Token](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="fde5a-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="fde5a-111">So geben Sie an, dass ein Dienst sichere Sitzungen verwendet, indem er eine der vom System bereitgestellten Bindungen nutzt</span><span class="sxs-lookup"><span data-stu-id="fde5a-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="fde5a-112">Konfigurieren Sie einen Dienst so, dass er eine vom System bereitgestellte Bindung verwendet, die die Nachrichtensicherheit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fde5a-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="fde5a-113">Mit Ausnahme von der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binden, wenn vom System bereitgestellten Bindungen konfiguriert sind, automatisch mit nachrichtensicherheit, WCF sichere Sitzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="fde5a-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="fde5a-114">In der folgenden Tabelle sind die vom System bereitgestellten Bindungen aufgeführt, die die Nachrichtensicherheit unterstützen. Außerdem ist angegeben, ob die Nachrichtensicherheit der standardmäßige Sicherheitsmechanismus ist.</span><span class="sxs-lookup"><span data-stu-id="fde5a-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="fde5a-115">Vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="fde5a-115">System-provided binding</span></span>|<span data-ttu-id="fde5a-116">Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="fde5a-116">Configuration element</span></span>|<span data-ttu-id="fde5a-117">Nachrichtensicherheit standardmäßig aktiviert</span><span class="sxs-lookup"><span data-stu-id="fde5a-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="fde5a-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fde5a-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="fde5a-119">Nein</span><span class="sxs-lookup"><span data-stu-id="fde5a-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="fde5a-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fde5a-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="fde5a-121">Ja</span><span class="sxs-lookup"><span data-stu-id="fde5a-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="fde5a-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fde5a-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="fde5a-123">Ja</span><span class="sxs-lookup"><span data-stu-id="fde5a-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="fde5a-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fde5a-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="fde5a-125">Ja</span><span class="sxs-lookup"><span data-stu-id="fde5a-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="fde5a-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="fde5a-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="fde5a-127">Nein</span><span class="sxs-lookup"><span data-stu-id="fde5a-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="fde5a-128">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="fde5a-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="fde5a-129">Nein</span><span class="sxs-lookup"><span data-stu-id="fde5a-129">No</span></span>|  
  
     <span data-ttu-id="fde5a-130">Das folgende Codebeispiel verwendet die Konfiguration zum Angeben einer Bindung, die mit dem Namen `wsHttpBinding_Calculator` , verwendet der [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die nachrichtensicherheit und sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="fde5a-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="fde5a-131">Das folgende Codebeispiel gibt an, dass die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die nachrichtensicherheit und sichere Sitzungen werden zum Schützen der `secureCalculator` Service.</span><span class="sxs-lookup"><span data-stu-id="fde5a-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="fde5a-132">Sichere Sitzungen deaktiviert werden für die [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) durch Festlegen der `establishSecurityContext` -Attribut auf `false`.</span><span class="sxs-lookup"><span data-stu-id="fde5a-132">Secure sessions can be turned off for the [<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="fde5a-133">Für die anderen vom System bereitgestellten Bindungen können Sie sichere Sitzungen nur deaktivieren, indem Sie eine benutzerdefinierte Bindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="fde5a-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="fde5a-134">So geben Sie an, dass ein Dienst mithilfe einer benutzerdefinierten Bindung sichere Sitzungen verwendet</span><span class="sxs-lookup"><span data-stu-id="fde5a-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="fde5a-135">Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP-Nachrichten mithilfe einer sicheren Sitzung geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="fde5a-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="fde5a-136">Weitere Informationen zum Erstellen einer benutzerdefinierten Bindung finden Sie unter [Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="fde5a-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="fde5a-137">Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine benutzerdefinierte Bindung anzugeben, die Nachrichten mithilfe einer sicheren Sitzung bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="fde5a-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="fde5a-138">Das folgende Codebeispiel erstellt eine benutzerdefinierte Bindung, die den <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>-Authentifizierungsmodus verwendet, um eine sichere Sitzung mithilfe eines Bootstrap-Vorgangs zu starten.</span><span class="sxs-lookup"><span data-stu-id="fde5a-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fde5a-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fde5a-139">See also</span></span>
- [<span data-ttu-id="fde5a-140">WCF-Bindungsübersicht</span><span class="sxs-lookup"><span data-stu-id="fde5a-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
