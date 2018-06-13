---
title: 'Vorgehensweise: Erstellen einer sicheren Sitzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ce351a87e70b09a2f68654af817e28fa3145d79d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493197"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="97084-102">Vorgehensweise: Erstellen einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="97084-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="97084-103">Mit Ausnahme von der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binden, wird vom System bereitgestellten Bindungen in der Windows Communication Foundation (WCF) automatisch verwendet sichere Sitzungen, wenn die nachrichtensicherheit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="97084-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="97084-104">Standardmäßig überleben sichere Sitzungen keine Webserver, die wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97084-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="97084-105">Wenn eine sichere Sitzung eingerichtet wird, speichern der Client und der Dienst den Schlüssel zwischen, der der sicheren Sitzung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="97084-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="97084-106">Beim Austauschen der Nachrichten wird nur ein Bezeichner des zwischengespeicherten Schlüssels ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="97084-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="97084-107">Wenn der Webserver wiederverwendet wird, wird der Cache ebenfalls wiederverwendet. Der Webserver kann den im Cache zwischengespeicherten Schlüssel für den Bezeichner dann nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="97084-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="97084-108">Wenn dies geschieht, wird für den Client eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="97084-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="97084-109">Sichere Sitzungen, die ein zustandsbehaftetes Token für den Sicherheitskontext verwenden, bleiben auch nach Wiederverwenden eines Webservers aktiv.</span><span class="sxs-lookup"><span data-stu-id="97084-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="97084-110">Weitere Informationen zur Verwendung von eines zustandsbehafteten SCT in einer sicheren Sitzung finden Sie unter [Vorgehensweise: Erstellen Sie ein Sicherheitskontexttoken für eine Sicherheitssitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="97084-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="97084-111">So geben Sie an, dass ein Dienst sichere Sitzungen verwendet, indem er eine der vom System bereitgestellten Bindungen nutzt</span><span class="sxs-lookup"><span data-stu-id="97084-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="97084-112">Konfigurieren Sie einen Dienst so, dass er eine vom System bereitgestellte Bindung verwendet, die die Nachrichtensicherheit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97084-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="97084-113">Mit Ausnahme von der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Bindung, wenn vom System bereitgestellten Bindungen konfiguriert wurden, automatisch mit nachrichtensicherheit, WCF, sichere Sitzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="97084-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="97084-114">In der folgenden Tabelle sind die vom System bereitgestellten Bindungen aufgeführt, die die Nachrichtensicherheit unterstützen. Außerdem ist angegeben, ob die Nachrichtensicherheit der standardmäßige Sicherheitsmechanismus ist.</span><span class="sxs-lookup"><span data-stu-id="97084-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="97084-115">Vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="97084-115">System-provided binding</span></span>|<span data-ttu-id="97084-116">Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="97084-116">Configuration element</span></span>|<span data-ttu-id="97084-117">Nachrichtensicherheit standardmäßig aktiviert</span><span class="sxs-lookup"><span data-stu-id="97084-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="97084-118">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="97084-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="97084-119">Nein</span><span class="sxs-lookup"><span data-stu-id="97084-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="97084-120">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="97084-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="97084-121">Ja</span><span class="sxs-lookup"><span data-stu-id="97084-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="97084-122">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="97084-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="97084-123">Ja</span><span class="sxs-lookup"><span data-stu-id="97084-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="97084-124">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="97084-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="97084-125">Ja</span><span class="sxs-lookup"><span data-stu-id="97084-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="97084-126">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="97084-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="97084-127">Nein</span><span class="sxs-lookup"><span data-stu-id="97084-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="97084-128">\<NetMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="97084-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="97084-129">Nein</span><span class="sxs-lookup"><span data-stu-id="97084-129">No</span></span>|  
  
     <span data-ttu-id="97084-130">Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine Bindung mit dem Namen anzugeben `wsHttpBinding_Calculator` , verwendet der [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die nachrichtensicherheit und sichere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="97084-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
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
  
     <span data-ttu-id="97084-131">Das folgende Codebeispiel gibt an, dass die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die nachrichtensicherheit und sichere Sitzungen werden verwendet, um sichere der `secureCalculator` Service.</span><span class="sxs-lookup"><span data-stu-id="97084-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="97084-132">Sichere Sitzungen können für deaktiviert die [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) durch Festlegen der `establishSecurityContext` -Attribut auf `false`.</span><span class="sxs-lookup"><span data-stu-id="97084-132">Secure sessions can be turned off for the [<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="97084-133">Für die anderen vom System bereitgestellten Bindungen können Sie sichere Sitzungen nur deaktivieren, indem Sie eine benutzerdefinierte Bindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="97084-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="97084-134">So geben Sie an, dass ein Dienst mithilfe einer benutzerdefinierten Bindung sichere Sitzungen verwendet</span><span class="sxs-lookup"><span data-stu-id="97084-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="97084-135">Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP-Nachrichten mithilfe einer sicheren Sitzung geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="97084-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="97084-136">Weitere Informationen zum Erstellen einer benutzerdefinierten Bindung finden Sie unter [wie: Anpassen einer Bindung sicherheitsbindungsarten](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="97084-136">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="97084-137">Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine benutzerdefinierte Bindung anzugeben, die Nachrichten mithilfe einer sicheren Sitzung bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="97084-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
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
  
     <span data-ttu-id="97084-138">Das folgende Codebeispiel erstellt eine benutzerdefinierte Bindung, die den <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>-Authentifizierungsmodus verwendet, um eine sichere Sitzung mithilfe eines Bootstrap-Vorgangs zu starten.</span><span class="sxs-lookup"><span data-stu-id="97084-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="97084-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97084-139">See Also</span></span>  
 [<span data-ttu-id="97084-140">WCF-Bindungsübersicht</span><span class="sxs-lookup"><span data-stu-id="97084-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
