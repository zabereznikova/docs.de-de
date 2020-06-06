---
title: <security> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 97c52fa4f062ed0c65d5b1a8ca47a1439ab04cf5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736480"
---
# <a name="security-of-nethttpbinding"></a><span data-ttu-id="12079-102">\<security> von \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="12079-102">\<security> of \<netHttpBinding></span></span>

<span data-ttu-id="12079-103">Definiert die Sicherheitsfunktionen von [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="12079-103">Defines the security capabilities of the [\<netHttpBinding>](nethttpbinding.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  

## <a name="syntax"></a><span data-ttu-id="12079-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12079-104">Syntax</span></span>

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12079-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="12079-105">Attributes and elements</span></span>

<span data-ttu-id="12079-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12079-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="12079-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="12079-107">Attributes</span></span>

|<span data-ttu-id="12079-108">attribute</span><span class="sxs-lookup"><span data-stu-id="12079-108">Attribute</span></span>|<span data-ttu-id="12079-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="12079-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="12079-110">Modus</span><span class="sxs-lookup"><span data-stu-id="12079-110">mode</span></span>|<span data-ttu-id="12079-111">(Optional)</span><span class="sxs-lookup"><span data-stu-id="12079-111">Optional.</span></span> <span data-ttu-id="12079-112">Gibt den verwendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="12079-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="12079-113">Der Standardwert lautet `None`.</span><span class="sxs-lookup"><span data-stu-id="12079-113">The default is `None`.</span></span> <span data-ttu-id="12079-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="12079-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|

## <a name="mode-attribute"></a><span data-ttu-id="12079-115">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="12079-115">mode attribute</span></span>

|<span data-ttu-id="12079-116">Wert</span><span class="sxs-lookup"><span data-stu-id="12079-116">Value</span></span>|<span data-ttu-id="12079-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="12079-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="12079-118">Keine</span><span class="sxs-lookup"><span data-stu-id="12079-118">None</span></span>|<span data-ttu-id="12079-119">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="12079-119">-   Messages are not secured during transfer.</span></span>|
|<span data-ttu-id="12079-120">Transport</span><span class="sxs-lookup"><span data-stu-id="12079-120">Transport</span></span>|<span data-ttu-id="12079-121">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="12079-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="12079-122">Die SOAP-Nachrichten werden bei der Verwendung von HTTPS gesichert.</span><span class="sxs-lookup"><span data-stu-id="12079-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="12079-123">Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="12079-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="12079-124">Der Client wird über ClientCredentialType authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="12079-124">The client is authenticated using the ClientCredentialType supplied.</span></span>|
|<span data-ttu-id="12079-125">`Message`</span><span class="sxs-lookup"><span data-stu-id="12079-125">Message</span></span>|<span data-ttu-id="12079-126">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="12079-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="12079-127">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="12079-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="12079-128">Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="12079-128">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="12079-129">Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="12079-129">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|
|<span data-ttu-id="12079-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="12079-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="12079-131">Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="12079-131">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="12079-132">Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="12079-132">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="12079-133">Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="12079-133">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|
|<span data-ttu-id="12079-134">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="12079-134">TransportCredentialOnly</span></span>|<span data-ttu-id="12079-135">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="12079-135">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="12079-136">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="12079-136">It provides http-based client authentication.</span></span> <span data-ttu-id="12079-137">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="12079-137">This mode should be used with caution.</span></span> <span data-ttu-id="12079-138">Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="12079-138">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="12079-139">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12079-139">Child elements</span></span>

|<span data-ttu-id="12079-140">Element</span><span class="sxs-lookup"><span data-stu-id="12079-140">Element</span></span>|<span data-ttu-id="12079-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12079-141">Description</span></span>|
|-------------|-----------------|
|[\<transport>](transport-of-nethttpbinding.md)|<span data-ttu-id="12079-142">Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="12079-142">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="12079-143">Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="12079-143">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|
|[\<message>](message-of-nethttpbinding.md)|<span data-ttu-id="12079-144">Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="12079-144">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="12079-145">Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="12079-145">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="12079-146">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12079-146">Parent elements</span></span>

|<span data-ttu-id="12079-147">Element</span><span class="sxs-lookup"><span data-stu-id="12079-147">Element</span></span>|<span data-ttu-id="12079-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12079-148">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="12079-149">binding</span><span class="sxs-lookup"><span data-stu-id="12079-149">binding</span></span>|<span data-ttu-id="12079-150">Das Bindungs Element von [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="12079-150">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|

## <a name="remarks"></a><span data-ttu-id="12079-151">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="12079-151">Remarks</span></span>

 <span data-ttu-id="12079-152">Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="12079-152">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="12079-153">Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `netHttpBinding`-Element zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="12079-153">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="12079-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12079-154">See also</span></span>

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [<span data-ttu-id="12079-155">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="12079-155">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="12079-156">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="12079-156">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="12079-157">Bindungen</span><span class="sxs-lookup"><span data-stu-id="12079-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="12079-158">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="12079-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="12079-159">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="12079-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
