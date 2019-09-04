---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251789"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="e87e8-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e87e8-102">\<system.identityModel></span></span>
<span data-ttu-id="e87e8-103">Stellt die Konfiguration zum Aktivieren von WIF-Optionen (Windows Identity Foundation) in-Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="e87e8-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
<span data-ttu-id="e87e8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e87e8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e87e8-105">&nbsp;&nbsp; **\<System. IdentityModel->**</span><span class="sxs-lookup"><span data-stu-id="e87e8-105">&nbsp;&nbsp;**\<system.identityModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e87e8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e87e8-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e87e8-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e87e8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e87e8-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e87e8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e87e8-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e87e8-109">Attributes</span></span>  
 <span data-ttu-id="e87e8-110">None</span><span class="sxs-lookup"><span data-stu-id="e87e8-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e87e8-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e87e8-111">Child Elements</span></span>  
  
|<span data-ttu-id="e87e8-112">Element</span><span class="sxs-lookup"><span data-stu-id="e87e8-112">Element</span></span>|<span data-ttu-id="e87e8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e87e8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e87e8-114">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e87e8-114">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="e87e8-115">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="e87e8-115">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e87e8-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e87e8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e87e8-117">Element</span><span class="sxs-lookup"><span data-stu-id="e87e8-117">Element</span></span>|<span data-ttu-id="e87e8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e87e8-118">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="e87e8-119">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e87e8-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e87e8-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e87e8-120">Remarks</span></span>  
 <span data-ttu-id="e87e8-121">Fügen Sie `<system.identityModel>` der Konfigurationsdatei einen Abschnitt hinzu, um einen Dienst oder eine Anwendung für die Verwendung von Windows Identity Foundation (WIF) zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e87e8-121">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="e87e8-122">Das `<system.identityModel>` -Element wird durch die <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e87e8-122">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e87e8-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e87e8-123">Example</span></span>  
 <span data-ttu-id="e87e8-124">Im folgenden Beispiel wird gezeigt, wie einer `<system.identityModel>` Konfigurationsdatei ein-Abschnitt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e87e8-124">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="e87e8-125">Sie müssen zunächst den Konfigurations Abschnitt und die Namespace Deklaration unter `<configSections>` dem-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e87e8-125">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="e87e8-126">Anschließend können Sie das- `<system.IdentityModel>` Element der Konfigurationsdatei hinzufügen, um eine oder mehrere Identitäts Konfigurationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e87e8-126">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e87e8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e87e8-127">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
