---
title: '&lt;system.identityModel&gt;'
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 1b3121a6e7e036ec268cf83ffbf545c0e669a9b9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206137"
---
# <a name="ltsystemidentitymodelgt"></a><span data-ttu-id="b5ec9-102">&lt;system.identityModel&gt;</span><span class="sxs-lookup"><span data-stu-id="b5ec9-102">&lt;system.identityModel&gt;</span></span>
<span data-ttu-id="b5ec9-103">Ermöglicht die Konfiguration für Windows Identity Foundation (WIF)-Optionen in Anwendungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="b5ec9-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b5ec9-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5ec9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5ec9-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5ec9-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b5ec9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b5ec9-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5ec9-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b5ec9-108">Attributes</span></span>  
 <span data-ttu-id="b5ec9-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="b5ec9-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b5ec9-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5ec9-110">Child Elements</span></span>  
  
|<span data-ttu-id="b5ec9-111">Element</span><span class="sxs-lookup"><span data-stu-id="b5ec9-111">Element</span></span>|<span data-ttu-id="b5ec9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5ec9-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5ec9-113">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b5ec9-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="b5ec9-114">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5ec9-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5ec9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b5ec9-116">Element</span><span class="sxs-lookup"><span data-stu-id="b5ec9-116">Element</span></span>|<span data-ttu-id="b5ec9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5ec9-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="b5ec9-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5ec9-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5ec9-119">Remarks</span></span>  
 <span data-ttu-id="b5ec9-120">Hinzufügen einer `<system.identityModel>` Abschnitt der Konfigurationsdatei auf einen Dienst oder Anwendung für die Verwendung von Windows Identity Foundation (WIF) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="b5ec9-121">Die `<system.identityModel>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5ec9-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5ec9-122">Example</span></span>  
 <span data-ttu-id="b5ec9-123">Das folgende Beispiel veranschaulicht das Hinzufügen einer `<system.identityModel>` Abschnitt einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="b5ec9-124">Sie müssen zuerst Abschnitt und den Namespace der Deklaration der Konfiguration unter Hinzufügen der `<configSections>` Element.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="b5ec9-125">Hinzufügen der `<system.IdentityModel>` Element an der Konfigurationsdatei an eine oder mehrere Identity-Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="b5ec9-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5ec9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5ec9-126">See Also</span></span>  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
