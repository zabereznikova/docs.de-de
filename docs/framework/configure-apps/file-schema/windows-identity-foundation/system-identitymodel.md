---
title: '&lt;system.identityModel&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 356dd1531f093282a1a8463b7d697400f8b45862
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemidentitymodelgt"></a><span data-ttu-id="94e18-102">&lt;system.identityModel&gt;</span><span class="sxs-lookup"><span data-stu-id="94e18-102">&lt;system.identityModel&gt;</span></span>
<span data-ttu-id="94e18-103">Ermöglicht die Konfiguration für Windows Identity Foundation (WIF)-Optionen in Anwendungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="94e18-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="94e18-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="94e18-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e18-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="94e18-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94e18-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="94e18-106">Attributes and Elements</span></span>  
 <span data-ttu-id="94e18-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="94e18-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94e18-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="94e18-108">Attributes</span></span>  
 <span data-ttu-id="94e18-109">Keine</span><span class="sxs-lookup"><span data-stu-id="94e18-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="94e18-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94e18-110">Child Elements</span></span>  
  
|<span data-ttu-id="94e18-111">Element</span><span class="sxs-lookup"><span data-stu-id="94e18-111">Element</span></span>|<span data-ttu-id="94e18-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94e18-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94e18-113">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="94e18-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="94e18-114">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="94e18-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94e18-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94e18-115">Parent Elements</span></span>  
  
|<span data-ttu-id="94e18-116">Element</span><span class="sxs-lookup"><span data-stu-id="94e18-116">Element</span></span>|<span data-ttu-id="94e18-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94e18-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="94e18-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="94e18-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94e18-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94e18-119">Remarks</span></span>  
 <span data-ttu-id="94e18-120">Hinzufügen einer `<system.identityModel>` Abschnitt der Konfigurationsdatei so konfigurieren Sie einen Dienst oder Anwendung für die Verwendung von Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="94e18-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="94e18-121">Die `<system.identityModel>` Element dargestellt ist, durch die <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="94e18-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e18-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94e18-122">Example</span></span>  
 <span data-ttu-id="94e18-123">Das folgende Beispiel veranschaulicht das Hinzufügen einer `<system.identityModel>` Abschnitt aus, um eine Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="94e18-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="94e18-124">Sie müssen zunächst Abschnitt und der Namespace der Deklaration der Konfiguration unter Hinzufügen der `<configSections>` Element.</span><span class="sxs-lookup"><span data-stu-id="94e18-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="94e18-125">Hinzufügen der `<system.IdentityModel>` Element zu Ihrer Konfigurationsdatei, ein oder mehrere Identity-Konfigurationen an.</span><span class="sxs-lookup"><span data-stu-id="94e18-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="94e18-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94e18-126">See Also</span></span>  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
