---
title: 'Vorgehensweise: Erstellen einer sicheren Sitzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: f6fb73653add7362e8c8452e75be802395ffc3cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286525"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="9c5b4-102">Vorgehensweise: Erstellen einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="9c5b4-102">How to: Create a Secure Session</span></span>

<span data-ttu-id="9c5b4-103">Mit Ausnahme der- [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) Bindung verwenden die vom System bereitgestellten Bindungen in Windows Communication Foundation (WCF) automatisch sichere Sitzungen, wenn die Nachrichten Sicherheit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-103">With the exception of the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="9c5b4-104">Standardmäßig überleben sichere Sitzungen keine Webserver, die wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="9c5b4-105">Wenn eine sichere Sitzung eingerichtet wird, speichern der Client und der Dienst den Schlüssel zwischen, der der sicheren Sitzung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="9c5b4-106">Beim Austauschen der Nachrichten wird nur ein Bezeichner des zwischengespeicherten Schlüssels ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="9c5b4-107">Wenn der Webserver wiederverwendet wird, wird der Cache ebenfalls wiederverwendet. Der Webserver kann den im Cache zwischengespeicherten Schlüssel für den Bezeichner dann nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="9c5b4-108">Wenn dies geschieht, wird für den Client eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="9c5b4-109">Sichere Sitzungen, die ein Token für den Sicherheitszustandskontext verwenden, bleiben auch nach Wiederverwenden eines Webservers aktiv.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="9c5b4-110">Weitere Informationen zum Verwenden eines Zustands behafteten SCT in einer sicheren Sitzung finden Sie unter Gewusst [wie: Erstellen eines Sicherheitskontext Tokens für eine sichere Sitzung](how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="9c5b4-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="9c5b4-111">So geben Sie an, dass ein Dienst sichere Sitzungen verwendet, indem er eine der vom System bereitgestellten Bindungen nutzt</span><span class="sxs-lookup"><span data-stu-id="9c5b4-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
- <span data-ttu-id="9c5b4-112">Konfigurieren Sie einen Dienst so, dass er eine vom System bereitgestellte Bindung verwendet, die die Nachrichtensicherheit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="9c5b4-113">Mit Ausnahme der- [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) Bindung verwendet WCF automatisch sichere Sitzungen, wenn die vom System bereitgestellten Bindungen für die Verwendung der Nachrichten Sicherheit konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-113">With the exception of the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="9c5b4-114">In der folgenden Tabelle sind die vom System bereitgestellten Bindungen aufgeführt, die die Nachrichtensicherheit unterstützen. Außerdem ist angegeben, ob die Nachrichtensicherheit der standardmäßige Sicherheitsmechanismus ist.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="9c5b4-115">Vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="9c5b4-115">System-provided binding</span></span>|<span data-ttu-id="9c5b4-116">Konfigurationselement</span><span class="sxs-lookup"><span data-stu-id="9c5b4-116">Configuration element</span></span>|<span data-ttu-id="9c5b4-117">Nachrichtensicherheit standardmäßig aktiviert</span><span class="sxs-lookup"><span data-stu-id="9c5b4-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="9c5b4-118">Nein </span><span class="sxs-lookup"><span data-stu-id="9c5b4-118">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="9c5b4-119">Ja</span><span class="sxs-lookup"><span data-stu-id="9c5b4-119">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="9c5b4-120">Ja</span><span class="sxs-lookup"><span data-stu-id="9c5b4-120">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="9c5b4-121">Ja</span><span class="sxs-lookup"><span data-stu-id="9c5b4-121">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="9c5b4-122">Nein </span><span class="sxs-lookup"><span data-stu-id="9c5b4-122">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="9c5b4-123">Nein </span><span class="sxs-lookup"><span data-stu-id="9c5b4-123">No</span></span>|  
  
     <span data-ttu-id="9c5b4-124">Im folgenden Codebeispiel wird die-Konfiguration verwendet, um eine Bindung mit dem Namen anzugeben, die `wsHttpBinding_Calculator` [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , Nachrichten Sicherheit und sichere Sitzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-124">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
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
  
     <span data-ttu-id="9c5b4-125">Im folgenden Codebeispiel wird angegeben, dass [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , die Nachrichten Sicherheit und sichere Sitzungen verwendet werden, um den Dienst zu sichern `secureCalculator` .</span><span class="sxs-lookup"><span data-stu-id="9c5b4-125">The following code example specifies that the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    > <span data-ttu-id="9c5b4-126">Sichere Sitzungen können für das ausgeschaltet werden [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , indem das- `establishSecurityContext` Attribut auf festgelegt wird `false` .</span><span class="sxs-lookup"><span data-stu-id="9c5b4-126">Secure sessions can be turned off for the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="9c5b4-127">Für die anderen vom System bereitgestellten Bindungen können Sie sichere Sitzungen nur deaktivieren, indem Sie eine benutzerdefinierte Bindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-127">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="9c5b4-128">So geben Sie an, dass ein Dienst mithilfe einer benutzerdefinierten Bindung sichere Sitzungen verwendet</span><span class="sxs-lookup"><span data-stu-id="9c5b4-128">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
- <span data-ttu-id="9c5b4-129">Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP-Nachrichten mithilfe einer sicheren Sitzung geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-129">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="9c5b4-130">Weitere Informationen zum Erstellen einer benutzerdefinierten Bindung finden Sie unter Gewusst [wie: Anpassen einer System-Provided Bindung](../extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="9c5b4-130">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="9c5b4-131">Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine benutzerdefinierte Bindung anzugeben, die Nachrichten mithilfe einer sicheren Sitzung bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-131">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
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
  
     <span data-ttu-id="9c5b4-132">Das folgende Codebeispiel erstellt eine benutzerdefinierte Bindung, die den <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>-Authentifizierungsmodus verwendet, um eine sichere Sitzung mithilfe eines Bootstrap-Vorgangs zu starten.</span><span class="sxs-lookup"><span data-stu-id="9c5b4-132">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9c5b4-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c5b4-133">See also</span></span>

- [<span data-ttu-id="9c5b4-134">WCF-Bindungsübersicht</span><span class="sxs-lookup"><span data-stu-id="9c5b4-134">WCF Bindings Overview</span></span>](../bindings-overview.md)
