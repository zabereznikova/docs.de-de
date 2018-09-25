---
title: 'Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
author: BrucePerlerMS
ms.openlocfilehash: 85954dd89bdb576b68d234a364a406a6e0d2145b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079882"
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a><span data-ttu-id="29a09-102">Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="29a09-102">How to: Create a Security Context Token for a Secure Session</span></span>
<span data-ttu-id="29a09-103">Durch das Verwenden eines zustandsbehafteten Sicherheitskontexttokens (SCT) in einer sicheren Sitzung, kann die Sitzung verhindern, dass der Dienst wiederverwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29a09-103">By using a stateful security context token (SCT) in a secure session, the session can withstand the service being recycled.</span></span> <span data-ttu-id="29a09-104">Wenn beispielsweise ein zustandsloses SCT in einer sicheren Sitzung verwendet wird und die IIS (Internet Information Services) zurückgesetzt werden, gehen die Sitzungsdaten, die dem Dienst zugewiesen sind, verloren.</span><span class="sxs-lookup"><span data-stu-id="29a09-104">For instance, when a stateless SCT is used in a secure session and Internet Information Services (IIS) is reset, then the session data that is associated with the service is lost.</span></span> <span data-ttu-id="29a09-105">Zu den Sitzungsdaten gehört auch ein SCT-Token-Cache.</span><span class="sxs-lookup"><span data-stu-id="29a09-105">This session data includes an SCT token cache.</span></span> <span data-ttu-id="29a09-106">Wenn ein Client also das nächste Mal dem Dienst einen zustandsloses SCT sendet, wird ein Fehler zurückgegeben, da der diesem SCT zugewiesene Schlüssel nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="29a09-106">So, the next time a client sends the service a stateless SCT, an error is returned, because the key that is associated with the SCT cannot be retrieved.</span></span> <span data-ttu-id="29a09-107">Wenn jedoch ein zustandsbehafteter SCT verwendet wird, enthält das SCT den diesem SCT zugewiesenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="29a09-107">If, however, a stateful SCT is used, then the key that is associated with the SCT is contained within the SCT.</span></span> <span data-ttu-id="29a09-108">Da der Schlüssel im SCT enthalten ist und somit auch in der Nachricht, wird die sichere Sitzung nicht von der Wiederverwendung des Dienstes beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="29a09-108">Because the key is contained within the SCT and thus contained within the message, the secure session is not affected by the service being recycled.</span></span> <span data-ttu-id="29a09-109">Standardmäßig verwendet Windows Communication Foundation (WCF) zustandslose SCTs in einer sicheren Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="29a09-109">By default, Windows Communication Foundation (WCF) uses stateless SCTs in a secure session.</span></span> <span data-ttu-id="29a09-110">Dieses Thema erläutert, wie Sie zustandsbehaftete SCTs in einer sicheren Sitzung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="29a09-110">This topic details how to use stateful SCTs in a secure session.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29a09-111">Zustandsbehaftete SCTs können nicht in einer sicheren Sitzung verwendet werden, die einen Vertrag einschließt, der vom <xref:System.ServiceModel.Channels.IDuplexChannel> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="29a09-111">Stateful SCTs cannot be used in a secure session that involves a contract that derives from <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29a09-112">Bei Anwendungen, die zustandsbehaftete SCTs in einer sicheren Sitzung verwenden, muss die Thread-Identität des Dienstes ein Benutzerkonto sein, dem ein Benutzerprofil zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="29a09-112">For applications that use stateful SCTs in a secure session, the thread identity for the service must be a user account that has an associated user profile.</span></span> <span data-ttu-id="29a09-113">Wenn der Dienst unter einem Konto ausgeführt wird, für das kein Benutzerprofil festgelegt wurde, z. B. ein `Local Service`, wird möglicherweise eine Ausnahme ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="29a09-113">When the service is run under an account that does not have a user profile, such as `Local Service`, an exception may be thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29a09-114">Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftetes SCT.</span><span class="sxs-lookup"><span data-stu-id="29a09-114">When impersonation is required on Windows XP, use a secure session without a stateful SCT.</span></span> <span data-ttu-id="29a09-115">Wenn Token für den Sicherheitszustandskontext (SCTs) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="29a09-115">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="29a09-116">Weitere Informationen finden Sie unter [nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="29a09-116">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a><span data-ttu-id="29a09-117">So verwenden Sie zustandsbehaftete SCTs in einer sicheren Sitzung</span><span class="sxs-lookup"><span data-stu-id="29a09-117">To use stateful SCTs in a secure session</span></span>  
  
-   <span data-ttu-id="29a09-118">Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP-Nachrichten durch eine sichere Sitzung mit einem zustandsbehafteten SCT geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="29a09-118">Create a custom binding that specifies that SOAP messages are protected by a secure session that uses a stateful SCT.</span></span>  
  
    1.  <span data-ttu-id="29a09-119">Definieren Sie eine benutzerdefinierte Bindung, durch das Hinzufügen einer [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) in die Konfigurationsdatei für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="29a09-119">Define a custom binding, by adding a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the configuration file for the service.</span></span>  
  
        ```xml  
        <customBinding>  
        ```  
  
    2.  <span data-ttu-id="29a09-120">Hinzufügen einer [ \<Bindung >](../../../../docs/framework/misc/binding.md) untergeordnetes Element der [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="29a09-120">Add a [\<binding>](../../../../docs/framework/misc/binding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="29a09-121">Geben Sie einen Bindungsnamen an, indem Sie das `name`-Attribut auf einen eindeutigen Namen in der Konfigurationsdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="29a09-121">Specify a binding name by setting the `name` attribute to a unique name within the configuration file.</span></span>  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  <span data-ttu-id="29a09-122">Geben Sie den Authentifizierungsmodus für Nachrichten an und von diesem Dienst gesendet werden, durch das Hinzufügen einer [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) untergeordnetes Element der [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="29a09-122">Specify the authentication mode for messages sent to and from this service by adding a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="29a09-123">Legen Sie fest, dass eine sichere Sitzung verwendet wird, indem Sie das `authenticationMode`-Attribut auf `SecureConversation` setzen.</span><span class="sxs-lookup"><span data-stu-id="29a09-123">Specify that a secure session is used by setting the `authenticationMode` attribute to `SecureConversation`.</span></span> <span data-ttu-id="29a09-124">Legen Sie fest, dass zustandsbehaftete SCTs verwendet werden, indem Sie das `requireSecurityContextCancellation`-Attribut auf `false` setzen.</span><span class="sxs-lookup"><span data-stu-id="29a09-124">Specify that stateful SCTs are used by setting the `requireSecurityContextCancellation` attribute to `false`.</span></span>  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  <span data-ttu-id="29a09-125">Angeben, wie der Client authentifiziert wird, während die sichere Sitzung, durch das Hinzufügen hergestellt wurde einer [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) untergeordnetes Element der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="29a09-125">Specify how the client is authenticated while the secure session is established by adding a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element to the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="29a09-126">Geben Sie an, wie der Client authentifiziert wird, indem Sie das `authenticationMode`-Attribut setzen.</span><span class="sxs-lookup"><span data-stu-id="29a09-126">Specify how the client is authenticated by setting the `authenticationMode` attribute.</span></span>  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  <span data-ttu-id="29a09-127">Geben Sie die nachrichtencodierung, indem Sie ein Codierungselement, z. B. hinzufügen [ \<TextMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span><span class="sxs-lookup"><span data-stu-id="29a09-127">Specify the message encoding by adding an encoding element, such as [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6.  <span data-ttu-id="29a09-128">Geben Sie den Transport, indem Sie ein Transportelement, z. B. Hinzufügen der [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span><span class="sxs-lookup"><span data-stu-id="29a09-128">Specify the transport by adding a transport element, such as the [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
        ```xml  
        <httpTransport />  
        ```  
  
     <span data-ttu-id="29a09-129">Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine benutzerdefinierte Bindung anzugeben, die Nachrichten mit zustandsbehafteten SCTs in einer sicheren Sitzung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="29a09-129">The following code example uses configuration to specify a custom binding that messages can use with stateful SCTs in a secure session.</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="29a09-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29a09-130">Example</span></span>  
 <span data-ttu-id="29a09-131">Das folgende Codebeispiel erstellt eine benutzerdefinierte Bindung, die den <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>-Authentifizierungsmodus verwendet, um eine sichere Sitzung mithilfe eines Bootstrap-Vorgangs zu starten.</span><span class="sxs-lookup"><span data-stu-id="29a09-131">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 <span data-ttu-id="29a09-132">Bei der Windows-Authentifizierung in Kombination mit einem zustandsbehafteten SCT verwendet wird, füllt WCF nicht auf die <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> Eigenschaft mit dem tatsächlichen Aufrufer Identität des sondern legt die Eigenschaft auf anonym.</span><span class="sxs-lookup"><span data-stu-id="29a09-132">When Windows authentication is used in combination with a stateful SCT, WCF does not populate the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property with the actual caller's identity but instead sets the property to anonymous.</span></span> <span data-ttu-id="29a09-133">Da WCF-Sicherheit den Inhalt des dienstsicherheitskontextes für jede Anfrage vom eingehenden SCT neu erstellen muss, der Server ist nicht die sicherheitssitzung im Speicher des nachvollziehen.</span><span class="sxs-lookup"><span data-stu-id="29a09-133">Because WCF security must re-create the content of the service security context for every request from the incoming SCT, the server does not keep track of the security session in the memory.</span></span> <span data-ttu-id="29a09-134">Da die <xref:System.Security.Principal.WindowsIdentity>-Instanz nicht in das SCT serialisiert werden kann, gibt die <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>-Eigenschaft eine anonyme Identität zurück.</span><span class="sxs-lookup"><span data-stu-id="29a09-134">Because it is impossible to serialize the <xref:System.Security.Principal.WindowsIdentity> instance into the SCT, the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property returns an anonymous identity.</span></span>  
  
 <span data-ttu-id="29a09-135">Die folgende Konfiguration weist dieses Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="29a09-135">The following configuration exhibits this behavior.</span></span>  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29a09-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29a09-136">See Also</span></span>  
 [<span data-ttu-id="29a09-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="29a09-137">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
