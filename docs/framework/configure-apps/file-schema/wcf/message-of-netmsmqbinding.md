---
title: <message> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 306bc56820cdbcba17cce9fc50d426260eb0e0d4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360666"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="85912-102">\<message> of \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="85912-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="85912-103">Definiert die SOAP-Nachrichtensicherheitseinstellungen für diese `netMsmqBinding`-Bindung.</span><span class="sxs-lookup"><span data-stu-id="85912-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="85912-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="85912-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="85912-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="85912-105">\<bindings>\\</span></span>
<span data-ttu-id="85912-106">\<netMsmqBinding>\\</span><span class="sxs-lookup"><span data-stu-id="85912-106">\<netMsmqBinding>\\</span></span>
<span data-ttu-id="85912-107">\<binding>\\</span><span class="sxs-lookup"><span data-stu-id="85912-107">\<binding>\\</span></span>
<span data-ttu-id="85912-108">\<security>\\</span><span class="sxs-lookup"><span data-stu-id="85912-108">\<security>\\</span></span>
<span data-ttu-id="85912-109">\<message></span><span class="sxs-lookup"><span data-stu-id="85912-109">\<message></span></span>

## <a name="syntax"></a><span data-ttu-id="85912-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="85912-110">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="85912-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="85912-111">Attributes and Elements</span></span>

<span data-ttu-id="85912-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85912-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="85912-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="85912-113">Attributes</span></span>

|<span data-ttu-id="85912-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="85912-114">Attribute</span></span>|<span data-ttu-id="85912-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85912-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="85912-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="85912-116">algorithmSuite</span></span>|<span data-ttu-id="85912-117">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest, die die nachrichtenbasierte Sicherheit für über den MSMQ-Transport gesendete Nachrichten sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="85912-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="85912-118">Der Standardwert ist `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="85912-118">The default value is `Aes256`.</span></span> <span data-ttu-id="85912-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="85912-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="85912-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="85912-120">clientCredentialType</span></span>|<span data-ttu-id="85912-121">Gibt den Anmeldeinformationstyp an, der bei der Clientauthentifizierung für über den MSMQ-Transport gesendete Nachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="85912-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="85912-122">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="85912-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="85912-123">– None: Dies ermöglicht dem Dienst, mit anonymen Clients zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="85912-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="85912-124">Weder der Dienst noch der Client erfordern Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="85912-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="85912-125">-   Windows: Dies ermöglicht SOAP-Austausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="85912-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="85912-126">Dies führt immer zur Durchführung einer auf Kerberos basierenden Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="85912-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="85912-127">-Benutzername: Dies ermöglicht den Dienst die Forderung, die der Client mit benutzernamenanmeldeinformationen authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="85912-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="85912-128">In diesem Fall muss die Anmeldeinformationen angegeben werden mithilfe der `clientCredentials` Verhalten **vorsichtig vor:**  Senden von kennwortdigests oder das Ableiten der Schlüssel mit Kennwörtern sowie die Verwendung solcher Schlüssel für die nachrichtensicherheit unterstützt Windows Communication Foundation (WCF) nicht.</span><span class="sxs-lookup"><span data-stu-id="85912-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="85912-129">Aus diesem Grund erzwingt WCF an, dass der Austausch gesichert wird, wenn UserName-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="85912-129">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="85912-130">Für diesen Modus ist es erforderlich, dass das Dienstzertifikat auf dem Client mithilfe des `clientCredential`-Verhaltens und `serviceCertificate` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="85912-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="85912-131">-Zertifikat: Dies ermöglicht den Dienst die Forderung, die der Client mit einem Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="85912-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="85912-132">Die Clientanmeldeinformationen müssen in diesem Fall über das `clientCredentials`-Verhalten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85912-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="85912-133">In diesem Fall müssen die Dienstanmeldeinformationen mit dem `clientCredentials`-Verhalten durch Bereitstellen von `serviceCertificate` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85912-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="85912-134">-CardSpace: Dies ermöglicht den Dienst die Forderung, die der Client mithilfe von CardSpace authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="85912-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="85912-135">
  `serviceCertificate\` muss im `clientCredential\`-Verhalten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="85912-135">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="85912-136">Der Standardwert ist `Windows`.</span><span class="sxs-lookup"><span data-stu-id="85912-136">The default value is `Windows`.</span></span> <span data-ttu-id="85912-137">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="85912-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="85912-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85912-138">Child Elements</span></span>

<span data-ttu-id="85912-139">Keine</span><span class="sxs-lookup"><span data-stu-id="85912-139">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="85912-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85912-140">Parent Elements</span></span>

|<span data-ttu-id="85912-141">Element</span><span class="sxs-lookup"><span data-stu-id="85912-141">Element</span></span>|<span data-ttu-id="85912-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85912-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="85912-143">\<security></span><span class="sxs-lookup"><span data-stu-id="85912-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="85912-144">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="85912-144">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="85912-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85912-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="85912-146">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="85912-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="85912-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="85912-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="85912-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="85912-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="85912-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="85912-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="85912-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="85912-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="85912-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="85912-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
