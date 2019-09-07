---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400498"
---
# <a name="clientcredentials"></a><span data-ttu-id="21dce-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="21dce-101">\<clientCredentials></span></span>
<span data-ttu-id="21dce-102">Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="21dce-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
<span data-ttu-id="21dce-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="21dce-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="21dce-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="21dce-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="21dce-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21dce-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="21dce-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21dce-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="21dce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="21dce-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="21dce-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Client Anmelde Informationen >**</span><span class="sxs-lookup"><span data-stu-id="21dce-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21dce-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="21dce-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21dce-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="21dce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="21dce-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="21dce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21dce-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="21dce-112">Attributes</span></span>  
  
|<span data-ttu-id="21dce-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="21dce-113">Attribute</span></span>|<span data-ttu-id="21dce-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21dce-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="21dce-115">Ein boolescher Wert, der angibt, ob ein interaktiver Benutzer in die Auswahl von Clientanmeldeinformationen zur Laufzeit einbezogen werden kann.</span><span class="sxs-lookup"><span data-stu-id="21dce-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="21dce-116">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="21dce-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="21dce-117">Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.</span><span class="sxs-lookup"><span data-stu-id="21dce-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21dce-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21dce-118">Child Elements</span></span>  
  
|<span data-ttu-id="21dce-119">Element</span><span class="sxs-lookup"><span data-stu-id="21dce-119">Element</span></span>|<span data-ttu-id="21dce-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21dce-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21dce-121">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="21dce-121">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="21dce-122">Gibt das zum Authentifizieren des Clients am Dienst verwendete Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="21dce-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="21dce-123">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="21dce-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="21dce-124">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="21dce-124">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="21dce-125">Gibt einen zum Authentifizieren des Clients am Dienst verwendeten Hashwert an.</span><span class="sxs-lookup"><span data-stu-id="21dce-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="21dce-126">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="21dce-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="21dce-127">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="21dce-127">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="21dce-128">Gibt einen zum Authentifizieren des Clients an einem Secure Token Service (STS) verwendeten benutzerdefinierten Tokentyp an.</span><span class="sxs-lookup"><span data-stu-id="21dce-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="21dce-129">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="21dce-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="21dce-130">\<peer></span><span class="sxs-lookup"><span data-stu-id="21dce-130">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="21dce-131">Gibt die aktuellen Peeranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="21dce-131">Specifies a current peer credential.</span></span> <span data-ttu-id="21dce-132">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="21dce-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="21dce-133">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="21dce-133">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="21dce-134">Gibt das zum Authentifizieren des Diensts am Client verwendete Zertifikat an und liefert eine Struktur zum Festlegen der Zertifikatsoptionen.</span><span class="sxs-lookup"><span data-stu-id="21dce-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="21dce-135">Dieses Zertifikat muss dem Client out-of-band vom Dienst zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="21dce-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="21dce-136">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="21dce-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="21dce-137">\<windows></span><span class="sxs-lookup"><span data-stu-id="21dce-137">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="21dce-138">Gibt Windows-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="21dce-138">Specifies a Windows credential.</span></span> <span data-ttu-id="21dce-139">Der Standardwert sind die Anmeldeinformationen des aktuellen Threads.</span><span class="sxs-lookup"><span data-stu-id="21dce-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="21dce-140">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="21dce-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21dce-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21dce-141">Parent Elements</span></span>  
  
|<span data-ttu-id="21dce-142">Element</span><span class="sxs-lookup"><span data-stu-id="21dce-142">Element</span></span>|<span data-ttu-id="21dce-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21dce-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21dce-144">\<behavior></span><span class="sxs-lookup"><span data-stu-id="21dce-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="21dce-145">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="21dce-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21dce-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21dce-146">Remarks</span></span>  
 <span data-ttu-id="21dce-147">Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="21dce-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="21dce-148">Dieser Konfigurationsabschnitt kann auch zur Angabe von Dienstzertifikaten in Szenarien verwendet werden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.</span><span class="sxs-lookup"><span data-stu-id="21dce-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21dce-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21dce-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="21dce-150">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="21dce-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="21dce-151">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="21dce-151">Securing Clients</span></span>](../../../wcf/securing-clients.md)
