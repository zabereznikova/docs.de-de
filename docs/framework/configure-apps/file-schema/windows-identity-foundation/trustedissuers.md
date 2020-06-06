---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251762"
---
# \<trustedIssuers>
<span data-ttu-id="b0ab3-101">Konfiguriert die Liste der vertrauenswürdigen Aussteller Zertifikate, die von der Konfigurations basierten Aussteller Namen Registrierung verwendet werden ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ).</span><span class="sxs-lookup"><span data-stu-id="b0ab3-101">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
## <a name="syntax"></a><span data-ttu-id="b0ab3-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0ab3-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0ab3-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b0ab3-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b0ab3-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0ab3-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="b0ab3-105">Attributes</span></span>  
 <span data-ttu-id="b0ab3-106">Keine</span><span class="sxs-lookup"><span data-stu-id="b0ab3-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0ab3-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0ab3-107">Child Elements</span></span>  
  
|<span data-ttu-id="b0ab3-108">Element</span><span class="sxs-lookup"><span data-stu-id="b0ab3-108">Element</span></span>|<span data-ttu-id="b0ab3-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b0ab3-109">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="b0ab3-110">Fügt der Auflistung vertrauenswürdiger Aussteller ein Zertifikat hinzu.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-110">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="b0ab3-111">Das Zertifikat wird mit dem- `thumbprint` Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-111">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="b0ab3-112">Dieses Attribut ist erforderlich und sollte die ASN. 1-codierte Form des Zertifikat Fingerabdrucks enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-112">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="b0ab3-113">Das `name` -Attribut ist optional und kann verwendet werden, um einen anzeigen Amen für das Zertifikat anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-113">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="b0ab3-114">Löscht alle Zertifikate aus der Sammlung vertrauenswürdiger Aussteller.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-114">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="b0ab3-115">Entfernt ein Zertifikat aus der Sammlung vertrauenswürdiger Aussteller.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-115">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="b0ab3-116">Das Zertifikat wird mit dem- `thumbprint` Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-116">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="b0ab3-117">Dieses Attribut ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-117">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0ab3-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0ab3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b0ab3-119">Element</span><span class="sxs-lookup"><span data-stu-id="b0ab3-119">Element</span></span>|<span data-ttu-id="b0ab3-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b0ab3-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="b0ab3-121">Konfiguriert die Aussteller Namen Registrierung.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-121">Configures the issuer name registry.</span></span> <span data-ttu-id="b0ab3-122">**Wichtig:**  Das- `type` Attribut des- `<issuerNameRegistry>` Elements muss auf die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse verweisen, damit das- `<trustedIssuers>` Element gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-122">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0ab3-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-123">Remarks</span></span>  
 <span data-ttu-id="b0ab3-124">Windows Identity Foundation (WIF) bietet eine einzige Implementierung der- <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse, die standardmäßig die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-124">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="b0ab3-125">Die Registrierung des Konfigurations Aussteller namens verwaltet eine Liste der vertrauenswürdigen Aussteller, die aus der Konfiguration geladen werden.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-125">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="b0ab3-126">In der Liste werden die einzelnen Aussteller Namen mit dem X. 509-Zertifikat verknüpft, das zum Überprüfen der Signatur der vom Aussteller erzeugten Token erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-126">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="b0ab3-127">Die Liste der vertrauenswürdigen Aussteller Zertifikate wird unter dem- `<trustedIssuers>` Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-127">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="b0ab3-128">Jedes Element in der Liste ordnet einen mmamonischen Aussteller Namen dem X. 509-Zertifikat zu, das zum Überprüfen der Signatur von Token benötigt wird, die von diesem Aussteller erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-128">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="b0ab3-129">Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und mithilfe des- `<add>` Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-129">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="b0ab3-130">Sie können Aussteller (Zertifikate) aus der Liste löschen oder entfernen, indem Sie `<clear>` die `<remove>` Elemente und verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-130">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="b0ab3-131">Das- `type` Attribut des- `<issuerNameRegistry>` Elements muss auf die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse verweisen, damit das- `<trustedIssuers>` Element gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-131">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0ab3-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0ab3-132">Example</span></span>  
 <span data-ttu-id="b0ab3-133">Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-133">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0ab3-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-134">See also</span></span>

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
