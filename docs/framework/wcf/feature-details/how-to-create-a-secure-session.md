---
title: 'Vorgehensweise: Erstellen einer sicheren Sitzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: bdb0f89b950d086e04cbb9d6da161bd315fc64b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934383"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="5816d-102">Vorgehensweise: Erstellen einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="5816d-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="5816d-103">Mit Ausnahme [ \<der BasicHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Bindung verwenden die vom System bereitgestellten Bindungen in Windows Communication Foundation (WCF) automatisch sichere Sitzungen, wenn die Nachrichten Sicherheit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5816d-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="5816d-104">Standardmäßig überleben sichere Sitzungen keine Webserver, die wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5816d-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="5816d-105">Wenn eine sichere Sitzung eingerichtet wird, speichern der Client und der Dienst den Schlüssel zwischen, der der sicheren Sitzung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5816d-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="5816d-106">Beim Austauschen der Nachrichten wird nur ein Bezeichner des zwischengespeicherten Schlüssels ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="5816d-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="5816d-107">Wenn der Webserver wiederverwendet wird, wird der Cache ebenfalls wiederverwendet. Der Webserver kann den im Cache zwischengespeicherten Schlüssel für den Bezeichner dann nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="5816d-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="5816d-108">Wenn dies geschieht, wird für den Client eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5816d-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="5816d-109">Sichere Sitzungen, die ein Token für den Sicherheitszustandskontext verwenden, bleiben auch nach Wiederverwenden eines Webservers aktiv.</span><span class="sxs-lookup"><span data-stu-id="5816d-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="5816d-110">Weitere Informationen zum Verwenden eines Zustands behafteten SCT in einer sicheren Sitzung finden [Sie unter Gewusst wie: Erstellen Sie ein Sicherheitskontext Token für eine sichere](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)Sitzung.</span><span class="sxs-lookup"><span data-stu-id="5816d-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="5816d-111">So geben Sie an, dass ein Dienst sichere Sitzungen verwendet, indem er eine der vom System bereitgestellten Bindungen nutzt</span><span class="sxs-lookup"><span data-stu-id="5816d-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
- <span data-ttu-id="5816d-112">Konfigurieren Sie einen Dienst so, dass er eine vom System bereitgestellte Bindung verwendet, die die Nachrichtensicherheit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5816d-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="5816d-113">Mit Ausnahme [ \<der BasicHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Bindung verwendet WCF automatisch sichere Sitzungen, wenn die vom System bereitgestellten Bindungen für die Verwendung der Nachrichten Sicherheit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="5816d-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="5816d-114">In der folgenden Tabelle sind die vom System bereitgestellten Bindungen aufgeführt, die die Nachrichtensicherheit unterstützen. Außerdem ist angegeben, ob die Nachrichtensicherheit der standardmäßige Sicherheitsmechanismus ist.</span><span class="sxs-lookup"><span data-stu-id="5816d-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="5816d-115">Vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="5816d-115">System-provided binding</span></span>|<span data-ttu-id="5816d-116">Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="5816d-116">Configuration element</span></span>|<span data-ttu-id="5816d-117">Nachrichtensicherheit standardmäßig aktiviert</span><span class="sxs-lookup"><span data-stu-id="5816d-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="5816d-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5816d-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="5816d-119">Nein</span><span class="sxs-lookup"><span data-stu-id="5816d-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="5816d-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5816d-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="5816d-121">Ja</span><span class="sxs-lookup"><span data-stu-id="5816d-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="5816d-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5816d-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="5816d-123">Ja</span><span class="sxs-lookup"><span data-stu-id="5816d-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="5816d-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5816d-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="5816d-125">Ja</span><span class="sxs-lookup"><span data-stu-id="5816d-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="5816d-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="5816d-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="5816d-127">Nein</span><span class="sxs-lookup"><span data-stu-id="5816d-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="5816d-128">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="5816d-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="5816d-129">Nein</span><span class="sxs-lookup"><span data-stu-id="5816d-129">No</span></span>|  
  
     <span data-ttu-id="5816d-130">Im folgenden Codebeispiel wird die-Konfiguration verwendet, um `wsHttpBinding_Calculator` eine Bindung mit dem Namen anzugeben, die das [ \<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die Nachrichten Sicherheit und sichere Sitzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5816d-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
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
  
     <span data-ttu-id="5816d-131">Im folgenden Codebeispiel wird angegeben, dass die [ \<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die Nachrichten Sicherheit und sichere Sitzungen verwendet werden `secureCalculator` , um den Dienst zu sichern.</span><span class="sxs-lookup"><span data-stu-id="5816d-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    > <span data-ttu-id="5816d-132">Sichere Sitzungen können für die [ \<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) ausgeschaltet werden, indem das `establishSecurityContext` -Attribut `false`auf festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5816d-132">Secure sessions can be turned off for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="5816d-133">Für die anderen vom System bereitgestellten Bindungen können Sie sichere Sitzungen nur deaktivieren, indem Sie eine benutzerdefinierte Bindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="5816d-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="5816d-134">So geben Sie an, dass ein Dienst mithilfe einer benutzerdefinierten Bindung sichere Sitzungen verwendet</span><span class="sxs-lookup"><span data-stu-id="5816d-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
- <span data-ttu-id="5816d-135">Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP-Nachrichten mithilfe einer sicheren Sitzung geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="5816d-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="5816d-136">Weitere Informationen zum Erstellen einer benutzerdefinierten Bindung finden [Sie unter Gewusst wie: Passen Sie eine vom System bereit](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)gestellte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="5816d-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="5816d-137">Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine benutzerdefinierte Bindung anzugeben, die Nachrichten mithilfe einer sicheren Sitzung bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="5816d-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
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
  
     <span data-ttu-id="5816d-138">Das folgende Codebeispiel erstellt eine benutzerdefinierte Bindung, die den <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>-Authentifizierungsmodus verwendet, um eine sichere Sitzung mithilfe eines Bootstrap-Vorgangs zu starten.</span><span class="sxs-lookup"><span data-stu-id="5816d-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5816d-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5816d-139">See also</span></span>

- [<span data-ttu-id="5816d-140">WCF-Bindungsübersicht</span><span class="sxs-lookup"><span data-stu-id="5816d-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
