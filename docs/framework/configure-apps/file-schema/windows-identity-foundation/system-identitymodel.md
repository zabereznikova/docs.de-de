---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 286ae88946692e6894ca3c7ee9e1348415c84ade
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943600"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="cf5d9-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="cf5d9-102">\<system.identityModel></span></span>
<span data-ttu-id="cf5d9-103">Stellt die Konfiguration zum Aktivieren von WIF-Optionen (Windows Identity Foundation) in-Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="cf5d9-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="cf5d9-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf5d9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf5d9-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf5d9-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cf5d9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cf5d9-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf5d9-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="cf5d9-108">Attributes</span></span>  
 <span data-ttu-id="cf5d9-109">None</span><span class="sxs-lookup"><span data-stu-id="cf5d9-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf5d9-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf5d9-110">Child Elements</span></span>  
  
|<span data-ttu-id="cf5d9-111">Element</span><span class="sxs-lookup"><span data-stu-id="cf5d9-111">Element</span></span>|<span data-ttu-id="cf5d9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf5d9-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf5d9-113">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="cf5d9-113">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="cf5d9-114">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf5d9-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf5d9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="cf5d9-116">Element</span><span class="sxs-lookup"><span data-stu-id="cf5d9-116">Element</span></span>|<span data-ttu-id="cf5d9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf5d9-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="cf5d9-118">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf5d9-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf5d9-119">Remarks</span></span>  
 <span data-ttu-id="cf5d9-120">Fügen Sie `<system.identityModel>` der Konfigurationsdatei einen Abschnitt hinzu, um einen Dienst oder eine Anwendung für die Verwendung von Windows Identity Foundation (WIF) zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="cf5d9-121">Das `<system.identityModel>` -Element wird durch die <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf5d9-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf5d9-122">Example</span></span>  
 <span data-ttu-id="cf5d9-123">Im folgenden Beispiel wird gezeigt, wie einer `<system.identityModel>` Konfigurationsdatei ein-Abschnitt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="cf5d9-124">Sie müssen zunächst den Konfigurations Abschnitt und die Namespace Deklaration unter `<configSections>` dem-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="cf5d9-125">Anschließend können Sie das- `<system.IdentityModel>` Element der Konfigurationsdatei hinzufügen, um eine oder mehrere Identitäts Konfigurationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cf5d9-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cf5d9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf5d9-126">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
