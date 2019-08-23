---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 32aad3529ded6d0234b1bcb388ecbbc3b0a11c87
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944274"
---
# <a name="trustedissuers"></a><span data-ttu-id="8acb7-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="8acb7-101">\<trustedIssuers></span></span>
<span data-ttu-id="8acb7-102">Konfiguriert die Liste der vertrauenswürdigen Aussteller Zertifikate, die von der Konfigurations basierten Aussteller Namen Registrierung verwendet<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>werden ().</span><span class="sxs-lookup"><span data-stu-id="8acb7-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="8acb7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8acb7-103">\<system.identityModel></span></span>  
<span data-ttu-id="8acb7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8acb7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="8acb7-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="8acb7-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8acb7-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="8acb7-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="8acb7-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="8acb7-107">\<issuerNameRegistry></span></span>  
<span data-ttu-id="8acb7-108">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="8acb7-108">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8acb7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8acb7-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8acb7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8acb7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8acb7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8acb7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8acb7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8acb7-112">Attributes</span></span>  
 <span data-ttu-id="8acb7-113">None</span><span class="sxs-lookup"><span data-stu-id="8acb7-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8acb7-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8acb7-114">Child Elements</span></span>  
  
|<span data-ttu-id="8acb7-115">Element</span><span class="sxs-lookup"><span data-stu-id="8acb7-115">Element</span></span>|<span data-ttu-id="8acb7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8acb7-116">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="8acb7-117">Fügt der Auflistung vertrauenswürdiger Aussteller ein Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="8acb7-117">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="8acb7-118">Das Zertifikat wird mit dem `thumbprint` -Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="8acb7-118">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="8acb7-119">Dieses Attribut ist erforderlich und sollte die ASN. 1-codierte Form des Zertifikat Fingerabdrucks enthalten.</span><span class="sxs-lookup"><span data-stu-id="8acb7-119">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="8acb7-120">Das `name` -Attribut ist optional und kann verwendet werden, um einen anzeigen Amen für das Zertifikat anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8acb7-120">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="8acb7-121">Löscht alle Zertifikate aus der Sammlung vertrauenswürdiger Aussteller.</span><span class="sxs-lookup"><span data-stu-id="8acb7-121">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="8acb7-122">Entfernt ein Zertifikat aus der Sammlung vertrauenswürdiger Aussteller.</span><span class="sxs-lookup"><span data-stu-id="8acb7-122">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="8acb7-123">Das Zertifikat wird mit dem `thumbprint` -Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="8acb7-123">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="8acb7-124">Dieses Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8acb7-124">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8acb7-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8acb7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8acb7-126">Element</span><span class="sxs-lookup"><span data-stu-id="8acb7-126">Element</span></span>|<span data-ttu-id="8acb7-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8acb7-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8acb7-128">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="8acb7-128">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="8acb7-129">Konfiguriert die Aussteller Namen Registrierung.</span><span class="sxs-lookup"><span data-stu-id="8acb7-129">Configures the issuer name registry.</span></span> <span data-ttu-id="8acb7-130">**Wichtig:**  Das `type` -Attribut `<issuerNameRegistry>` des-Elements muss auf <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> die-Klasse `<trustedIssuers>` verweisen, damit das-Element gültig ist.</span><span class="sxs-lookup"><span data-stu-id="8acb7-130">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8acb7-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8acb7-131">Remarks</span></span>  
 <span data-ttu-id="8acb7-132">Windows Identity Foundation (WIF) bietet eine einzige Implementierung <xref:System.IdentityModel.Tokens.IssuerNameRegistry> der-Klasse, die standardmäßig die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="8acb7-132">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="8acb7-133">Die Registrierung des Konfigurations Aussteller namens verwaltet eine Liste der vertrauenswürdigen Aussteller, die aus der Konfiguration geladen werden.</span><span class="sxs-lookup"><span data-stu-id="8acb7-133">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="8acb7-134">In der Liste werden die einzelnen Aussteller Namen mit dem X. 509-Zertifikat verknüpft, das zum Überprüfen der Signatur der vom Aussteller erzeugten Token erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8acb7-134">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="8acb7-135">Die Liste der vertrauenswürdigen Aussteller Zertifikate wird unter dem `<trustedIssuers>` -Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="8acb7-135">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="8acb7-136">Jedes Element in der Liste ordnet einen mmamonischen Aussteller Namen dem X. 509-Zertifikat zu, das zum Überprüfen der Signatur von Token benötigt wird, die von diesem Aussteller erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8acb7-136">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="8acb7-137">Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und mithilfe `<add>` des-Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8acb7-137">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="8acb7-138">Sie können Aussteller (Zertifikate) aus der Liste löschen oder entfernen, indem Sie `<clear>` die `<remove>` Elemente und verwenden.</span><span class="sxs-lookup"><span data-stu-id="8acb7-138">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="8acb7-139">Das `type` -Attribut `<issuerNameRegistry>` des-Elements muss auf <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> die-Klasse `<trustedIssuers>` verweisen, damit das-Element gültig ist.</span><span class="sxs-lookup"><span data-stu-id="8acb7-139">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8acb7-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8acb7-140">Example</span></span>  
 <span data-ttu-id="8acb7-141">Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8acb7-141">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8acb7-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8acb7-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
