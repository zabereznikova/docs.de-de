---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: c3e756f49b7054d6553eb6c3f1850f0fbce14943
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926113"
---
# <a name="clientcredentials"></a><span data-ttu-id="6b6bb-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="6b6bb-101">\<clientCredentials></span></span>
<span data-ttu-id="6b6bb-102">Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="6b6bb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6b6bb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6b6bb-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="6b6bb-104">\<behaviors></span></span>  
<span data-ttu-id="6b6bb-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="6b6bb-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="6b6bb-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6b6bb-106">\<behavior></span></span>  
<span data-ttu-id="6b6bb-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="6b6bb-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b6bb-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b6bb-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b6bb-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6bb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6b6bb-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b6bb-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b6bb-111">Attributes</span></span>  
  
|<span data-ttu-id="6b6bb-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="6b6bb-112">Attribute</span></span>|<span data-ttu-id="6b6bb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b6bb-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="6b6bb-114">Ein boolescher Wert, der angibt, ob ein interaktiver Benutzer in die Auswahl von Clientanmeldeinformationen zur Laufzeit einbezogen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="6b6bb-115">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="6b6bb-116">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b6bb-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6bb-117">Child Elements</span></span>  
  
|<span data-ttu-id="6b6bb-118">Element</span><span class="sxs-lookup"><span data-stu-id="6b6bb-118">Element</span></span>|<span data-ttu-id="6b6bb-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b6bb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b6bb-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="6b6bb-120">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="6b6bb-121">Gibt das zum Authentifizieren des Clients am Dienst verwendete Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="6b6bb-122">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="6b6bb-123">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="6b6bb-123">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="6b6bb-124">Gibt einen zum Authentifizieren des Clients am Dienst verwendeten Hashwert an.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="6b6bb-125">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="6b6bb-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="6b6bb-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="6b6bb-127">Gibt einen zum Authentifizieren des Clients an einem Secure Token Service (STS) verwendeten benutzerdefinierten Tokentyp an.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="6b6bb-128">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="6b6bb-129">\<peer></span><span class="sxs-lookup"><span data-stu-id="6b6bb-129">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="6b6bb-130">Gibt die aktuellen Peeranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-130">Specifies a current peer credential.</span></span> <span data-ttu-id="6b6bb-131">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="6b6bb-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="6b6bb-132">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="6b6bb-133">Gibt das zum Authentifizieren des Diensts am Client verwendete Zertifikat an und liefert eine Struktur zum Festlegen der Zertifikatsoptionen.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="6b6bb-134">Dieses Zertifikat muss dem Client out-of-band vom Dienst zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="6b6bb-135">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="6b6bb-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="6b6bb-136">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="6b6bb-137">Gibt Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-137">Specifies a Windows credential.</span></span> <span data-ttu-id="6b6bb-138">Der Standardwert sind die Anmeldeinformationen des aktuellen Threads.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="6b6bb-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b6bb-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6bb-140">Parent Elements</span></span>  
  
|<span data-ttu-id="6b6bb-141">Element</span><span class="sxs-lookup"><span data-stu-id="6b6bb-141">Element</span></span>|<span data-ttu-id="6b6bb-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b6bb-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b6bb-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6b6bb-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6b6bb-144">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b6bb-145">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b6bb-145">Remarks</span></span>  
 <span data-ttu-id="6b6bb-146">Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="6b6bb-147">Dieser Konfigurationsabschnitt kann auch zur Angabe von Dienstzertifikaten in Szenarien verwendet werden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.</span><span class="sxs-lookup"><span data-stu-id="6b6bb-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b6bb-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b6bb-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="6b6bb-149">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="6b6bb-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6b6bb-150">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="6b6bb-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)
