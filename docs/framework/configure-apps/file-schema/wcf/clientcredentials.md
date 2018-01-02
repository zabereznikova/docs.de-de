---
title: '&lt;clientCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eaf46953d7b2c3f89e1f5b107dc9ddf5d1597875
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientcredentialsgt"></a><span data-ttu-id="3641a-102">&lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="3641a-102">&lt;clientCredentials&gt;</span></span>
<span data-ttu-id="3641a-103">Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="3641a-103">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="3641a-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3641a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3641a-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="3641a-105">\<behaviors></span></span>  
<span data-ttu-id="3641a-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3641a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="3641a-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="3641a-107">\<behavior></span></span>  
<span data-ttu-id="3641a-108">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="3641a-108">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3641a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3641a-109">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"  
      supportInteractive="Boolean" >  
   <clientCertificate>  
   </clientCertificate>  
   <digest>  
   </digest>  
   <isuedToken>  
   </isuedToken>  
   <peer>  
   </peer>  
   <serviceCertificate>  
   </serviceCertificate>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</clientCredentials>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3641a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3641a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3641a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3641a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3641a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3641a-112">Attributes</span></span>  
  
|<span data-ttu-id="3641a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3641a-113">Attribute</span></span>|<span data-ttu-id="3641a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3641a-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="3641a-115">Ein boolescher Wert, der angibt, ob ein interaktiver Benutzer in die Auswahl von Clientanmeldeinformationen zur Laufzeit einbezogen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3641a-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="3641a-116">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="3641a-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="3641a-117">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="3641a-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3641a-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3641a-118">Child Elements</span></span>  
  
|<span data-ttu-id="3641a-119">Element</span><span class="sxs-lookup"><span data-stu-id="3641a-119">Element</span></span>|<span data-ttu-id="3641a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3641a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3641a-121">\<ClientCertificate ></span><span class="sxs-lookup"><span data-stu-id="3641a-121">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="3641a-122">Gibt das zum Authentifizieren des Clients am Dienst verwendete Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="3641a-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="3641a-123">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="3641a-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="3641a-124">\<HttpDigest ></span><span class="sxs-lookup"><span data-stu-id="3641a-124">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="3641a-125">Gibt einen zum Authentifizieren des Clients am Dienst verwendeten Hashwert an.</span><span class="sxs-lookup"><span data-stu-id="3641a-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="3641a-126">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="3641a-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="3641a-127">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="3641a-127">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="3641a-128">Gibt einen zum Authentifizieren des Clients an einem Secure Token Service (STS) verwendeten benutzerdefinierten Tokentyp an.</span><span class="sxs-lookup"><span data-stu-id="3641a-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="3641a-129">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="3641a-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="3641a-130">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="3641a-130">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="3641a-131">Gibt die aktuellen Peeranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="3641a-131">Specifies a current peer credential.</span></span> <span data-ttu-id="3641a-132">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="3641a-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="3641a-133">\<ServiceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3641a-133">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="3641a-134">Gibt das zum Authentifizieren des Diensts am Client verwendete Zertifikat an und liefert eine Struktur zum Festlegen der Zertifikatsoptionen.</span><span class="sxs-lookup"><span data-stu-id="3641a-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="3641a-135">Dieses Zertifikat muss dem Client out-of-band vom Dienst zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3641a-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="3641a-136">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="3641a-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="3641a-137">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="3641a-137">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="3641a-138">Gibt Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="3641a-138">Specifies a Windows credential.</span></span> <span data-ttu-id="3641a-139">Der Standardwert sind die Anmeldeinformationen des aktuellen Threads.</span><span class="sxs-lookup"><span data-stu-id="3641a-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="3641a-140">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="3641a-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3641a-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3641a-141">Parent Elements</span></span>  
  
|<span data-ttu-id="3641a-142">Element</span><span class="sxs-lookup"><span data-stu-id="3641a-142">Element</span></span>|<span data-ttu-id="3641a-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3641a-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3641a-144">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="3641a-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3641a-145">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="3641a-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3641a-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3641a-146">Remarks</span></span>  
 <span data-ttu-id="3641a-147">Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3641a-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="3641a-148">Dieser Konfigurationsabschnitt kann auch zur Angabe von Dienstzertifikaten in Szenarien verwendet werden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.</span><span class="sxs-lookup"><span data-stu-id="3641a-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3641a-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3641a-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [<span data-ttu-id="3641a-150">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="3641a-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="3641a-151">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="3641a-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
