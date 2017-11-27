---
title: '&lt;message&gt; von &lt;netMsmqBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f3b03fcce02c51563ed006e62a3f77f76bede777
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="f6cf3-102">&lt;message&gt; von &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="f6cf3-102">&lt;message&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="f6cf3-103">Definiert die SOAP-Nachrichtensicherheitseinstellungen für diese `netMsmqBinding`-Bindung.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>  
  
 <span data-ttu-id="f6cf3-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f6cf3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f6cf3-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="f6cf3-105">\<bindings></span></span>  
<span data-ttu-id="f6cf3-106">\<NetMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="f6cf3-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="f6cf3-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="f6cf3-107">\<binding></span></span>  
<span data-ttu-id="f6cf3-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="f6cf3-108">\<security></span></span>  
<span data-ttu-id="f6cf3-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="f6cf3-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6cf3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6cf3-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6cf3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f6cf3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f6cf3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6cf3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="f6cf3-113">Attributes</span></span>  
  
|<span data-ttu-id="f6cf3-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="f6cf3-114">Attribute</span></span>|<span data-ttu-id="f6cf3-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6cf3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6cf3-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="f6cf3-116">algorithmSuite</span></span>|<span data-ttu-id="f6cf3-117">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest, die die nachrichtenbasierte Sicherheit für über den MSMQ-Transport gesendete Nachrichten sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="f6cf3-118">Der Standardwert ist `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-118">The default value is `Aes256`.</span></span> <span data-ttu-id="f6cf3-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|  
|<span data-ttu-id="f6cf3-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f6cf3-120">clientCredentialType</span></span>|<span data-ttu-id="f6cf3-121">Gibt den Anmeldeinformationstyp an, der bei der Clientauthentifizierung für über den MSMQ-Transport gesendete Nachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="f6cf3-122">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="f6cf3-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f6cf3-123">-None: Dies ermöglicht den Dienst, mit anonymen Clients zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="f6cf3-124">Weder der Dienst noch der Client erfordern Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="f6cf3-125">-Windows: Dies ermöglicht SOAP-Austausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="f6cf3-126">Dies führt immer zur Durchführung einer auf Kerberos basierenden Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="f6cf3-127">-UserName: Dies ermöglicht den Dienst zu fordern, die der Client mit benutzernamenanmeldeinformationen authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="f6cf3-128">In diesem Fall muss die Anmeldeinformationen angegeben werden mithilfe der `clientCredentials` Verhalten **Vorsicht:** [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Senden eines kennworthashwerts oder die Ableitung von Schlüsseln mit Kennwörtern sowie die Verwendung solcher Schlüssel für die nachrichtensicherheit nicht unterstützt.  </span><span class="sxs-lookup"><span data-stu-id="f6cf3-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="f6cf3-129">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] setzt daher prinzipiell durch, dass der Austausch gesichert wird, wenn UserName-Anmeldeinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-129">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="f6cf3-130">Für diesen Modus ist es erforderlich, dass das Dienstzertifikat auf dem Client mithilfe des `clientCredential`-Verhaltens und `serviceCertificate` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="f6cf3-131">-Certificate: Dies ermöglicht den Dienst zu fordern, die der Client über ein Zertifikat authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="f6cf3-132">Die Clientanmeldeinformationen müssen in diesem Fall über das `clientCredentials`-Verhalten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="f6cf3-133">In diesem Fall müssen die Dienstanmeldeinformationen mit dem `clientCredentials`-Verhalten durch Bereitstellen von `serviceCertificate` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="f6cf3-134">-CardSpace: Dies ermöglicht den Dienst zu fordern, die der Client mit einem CardSpace authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="f6cf3-135">`serviceCertiifcate` muss im `clientCredential`-Verhalten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-135">The `serviceCertiifcate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="f6cf3-136">Der Standardwert ist `Windows`.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-136">The default value is `Windows`.</span></span> <span data-ttu-id="f6cf3-137">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6cf3-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f6cf3-138">Child Elements</span></span>  
 <span data-ttu-id="f6cf3-139">Keine</span><span class="sxs-lookup"><span data-stu-id="f6cf3-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6cf3-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f6cf3-140">Parent Elements</span></span>  
  
|<span data-ttu-id="f6cf3-141">Element</span><span class="sxs-lookup"><span data-stu-id="f6cf3-141">Element</span></span>|<span data-ttu-id="f6cf3-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6cf3-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6cf3-143">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="f6cf3-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="f6cf3-144">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="f6cf3-144">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6cf3-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6cf3-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [<span data-ttu-id="f6cf3-146">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="f6cf3-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="f6cf3-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="f6cf3-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="f6cf3-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="f6cf3-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f6cf3-149">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="f6cf3-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f6cf3-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="f6cf3-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="f6cf3-151">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="f6cf3-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
