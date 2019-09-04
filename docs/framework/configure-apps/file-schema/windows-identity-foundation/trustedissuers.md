---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251762"
---
# <a name="trustedissuers"></a><span data-ttu-id="254d3-101">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="254d3-101">\<trustedIssuers></span></span>
<span data-ttu-id="254d3-102">Konfiguriert die Liste der vertrauenswürdigen Aussteller Zertifikate, die von der Konfigurations basierten Aussteller Namen Registrierung verwendet<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>werden ().</span><span class="sxs-lookup"><span data-stu-id="254d3-102">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
<span data-ttu-id="254d3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="254d3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="254d3-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="254d3-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="254d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="254d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="254d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="254d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="254d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlerconfiguration->** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="254d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="254d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerNameRegistry->** ](issuernameregistry.md)</span><span class="sxs-lookup"><span data-stu-id="254d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)</span></span>\
<span data-ttu-id="254d3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Treuhänder >**</span><span class="sxs-lookup"><span data-stu-id="254d3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="254d3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="254d3-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="254d3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="254d3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="254d3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="254d3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="254d3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="254d3-113">Attributes</span></span>  
 <span data-ttu-id="254d3-114">None</span><span class="sxs-lookup"><span data-stu-id="254d3-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="254d3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="254d3-115">Child Elements</span></span>  
  
|<span data-ttu-id="254d3-116">Element</span><span class="sxs-lookup"><span data-stu-id="254d3-116">Element</span></span>|<span data-ttu-id="254d3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="254d3-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="254d3-118">Fügt der Auflistung vertrauenswürdiger Aussteller ein Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="254d3-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="254d3-119">Das Zertifikat wird mit dem `thumbprint` -Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="254d3-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="254d3-120">Dieses Attribut ist erforderlich und sollte die ASN. 1-codierte Form des Zertifikat Fingerabdrucks enthalten.</span><span class="sxs-lookup"><span data-stu-id="254d3-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="254d3-121">Das `name` -Attribut ist optional und kann verwendet werden, um einen anzeigen Amen für das Zertifikat anzugeben.</span><span class="sxs-lookup"><span data-stu-id="254d3-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="254d3-122">Löscht alle Zertifikate aus der Sammlung vertrauenswürdiger Aussteller.</span><span class="sxs-lookup"><span data-stu-id="254d3-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="254d3-123">Entfernt ein Zertifikat aus der Sammlung vertrauenswürdiger Aussteller.</span><span class="sxs-lookup"><span data-stu-id="254d3-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="254d3-124">Das Zertifikat wird mit dem `thumbprint` -Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="254d3-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="254d3-125">Dieses Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="254d3-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="254d3-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="254d3-126">Parent Elements</span></span>  
  
|<span data-ttu-id="254d3-127">Element</span><span class="sxs-lookup"><span data-stu-id="254d3-127">Element</span></span>|<span data-ttu-id="254d3-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="254d3-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="254d3-129">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="254d3-129">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="254d3-130">Konfiguriert die Aussteller Namen Registrierung.</span><span class="sxs-lookup"><span data-stu-id="254d3-130">Configures the issuer name registry.</span></span> <span data-ttu-id="254d3-131">**Wichtig:**  Das `type` -Attribut `<issuerNameRegistry>` des-Elements muss auf <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> die-Klasse `<trustedIssuers>` verweisen, damit das-Element gültig ist.</span><span class="sxs-lookup"><span data-stu-id="254d3-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="254d3-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="254d3-132">Remarks</span></span>  
 <span data-ttu-id="254d3-133">Windows Identity Foundation (WIF) bietet eine einzige Implementierung <xref:System.IdentityModel.Tokens.IssuerNameRegistry> der-Klasse, die standardmäßig die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="254d3-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="254d3-134">Die Registrierung des Konfigurations Aussteller namens verwaltet eine Liste der vertrauenswürdigen Aussteller, die aus der Konfiguration geladen werden.</span><span class="sxs-lookup"><span data-stu-id="254d3-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="254d3-135">In der Liste werden die einzelnen Aussteller Namen mit dem X. 509-Zertifikat verknüpft, das zum Überprüfen der Signatur der vom Aussteller erzeugten Token erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="254d3-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="254d3-136">Die Liste der vertrauenswürdigen Aussteller Zertifikate wird unter dem `<trustedIssuers>` -Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="254d3-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="254d3-137">Jedes Element in der Liste ordnet einen mmamonischen Aussteller Namen dem X. 509-Zertifikat zu, das zum Überprüfen der Signatur von Token benötigt wird, die von diesem Aussteller erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="254d3-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="254d3-138">Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und mithilfe `<add>` des-Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="254d3-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="254d3-139">Sie können Aussteller (Zertifikate) aus der Liste löschen oder entfernen, indem Sie `<clear>` die `<remove>` Elemente und verwenden.</span><span class="sxs-lookup"><span data-stu-id="254d3-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="254d3-140">Das `type` -Attribut `<issuerNameRegistry>` des-Elements muss auf <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> die-Klasse `<trustedIssuers>` verweisen, damit das-Element gültig ist.</span><span class="sxs-lookup"><span data-stu-id="254d3-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="254d3-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="254d3-141">Example</span></span>  
 <span data-ttu-id="254d3-142">Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="254d3-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="254d3-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="254d3-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
