---
title: <message> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: c623b7daf1e91c9c1800b9653525cd51b1087506
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768952"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="cd989-102">\<message> of \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="cd989-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="cd989-103">Definiert die SOAP-Nachrichtensicherheitseinstellungen für diese `netMsmqBinding`-Bindung.</span><span class="sxs-lookup"><span data-stu-id="cd989-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="cd989-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd989-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="cd989-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd989-105">Attributes and Elements</span></span>

<span data-ttu-id="cd989-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd989-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cd989-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd989-107">Attributes</span></span>

|<span data-ttu-id="cd989-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="cd989-108">Attribute</span></span>|<span data-ttu-id="cd989-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd989-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="cd989-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="cd989-110">algorithmSuite</span></span>|<span data-ttu-id="cd989-111">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest, die die nachrichtenbasierte Sicherheit für über den MSMQ-Transport gesendete Nachrichten sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="cd989-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="cd989-112">Der Standardwert ist `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="cd989-112">The default value is `Aes256`.</span></span> <span data-ttu-id="cd989-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="cd989-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="cd989-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="cd989-114">clientCredentialType</span></span>|<span data-ttu-id="cd989-115">Gibt den Anmeldeinformationstyp an, der bei der Clientauthentifizierung für über den MSMQ-Transport gesendete Nachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cd989-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="cd989-116">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cd989-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cd989-117">– None: Dies ermöglicht dem Dienst, mit anonymen Clients zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="cd989-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="cd989-118">Weder der Dienst noch der Client erfordern Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="cd989-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="cd989-119">-   Windows: Dies ermöglicht SOAP-Austausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="cd989-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="cd989-120">Dies führt immer zur Durchführung einer auf Kerberos basierenden Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="cd989-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="cd989-121">-Benutzername: Dies ermöglicht den Dienst die Forderung, die der Client mit benutzernamenanmeldeinformationen authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="cd989-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="cd989-122">In diesem Fall muss die Anmeldeinformationen angegeben werden mithilfe der `clientCredentials` Verhalten **vorsichtig vor:**  Senden von kennwortdigests oder das Ableiten der Schlüssel mit Kennwörtern sowie die Verwendung solcher Schlüssel für die nachrichtensicherheit unterstützt Windows Communication Foundation (WCF) nicht.</span><span class="sxs-lookup"><span data-stu-id="cd989-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="cd989-123">Aus diesem Grund erzwingt WCF an, dass der Austausch gesichert wird, wenn UserName-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd989-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="cd989-124">Für diesen Modus ist es erforderlich, dass das Dienstzertifikat auf dem Client mithilfe des `clientCredential`-Verhaltens und `serviceCertificate` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd989-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="cd989-125">-Zertifikat: Dies ermöglicht den Dienst die Forderung, die der Client mit einem Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="cd989-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="cd989-126">Die Clientanmeldeinformationen müssen in diesem Fall über das `clientCredentials`-Verhalten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd989-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="cd989-127">In diesem Fall müssen die Dienstanmeldeinformationen mit dem `clientCredentials`-Verhalten durch Bereitstellen von `serviceCertificate` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd989-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="cd989-128">-CardSpace: Dies ermöglicht den Dienst die Forderung, die der Client mithilfe von CardSpace authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="cd989-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="cd989-129">`serviceCertificate` muss im `clientCredential`-Verhalten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd989-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="cd989-130">Der Standardwert ist `Windows`.</span><span class="sxs-lookup"><span data-stu-id="cd989-130">The default value is `Windows`.</span></span> <span data-ttu-id="cd989-131">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="cd989-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cd989-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd989-132">Child Elements</span></span>

<span data-ttu-id="cd989-133">Keiner</span><span class="sxs-lookup"><span data-stu-id="cd989-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cd989-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd989-134">Parent Elements</span></span>

|<span data-ttu-id="cd989-135">Element</span><span class="sxs-lookup"><span data-stu-id="cd989-135">Element</span></span>|<span data-ttu-id="cd989-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd989-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cd989-137">\<security></span><span class="sxs-lookup"><span data-stu-id="cd989-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="cd989-138">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="cd989-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="cd989-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd989-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="cd989-140">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="cd989-140">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="cd989-141">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="cd989-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cd989-142">Bindungen</span><span class="sxs-lookup"><span data-stu-id="cd989-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cd989-143">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="cd989-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cd989-144">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="cd989-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cd989-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="cd989-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
