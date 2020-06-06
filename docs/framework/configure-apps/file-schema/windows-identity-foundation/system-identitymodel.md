---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251789"
---
# \<system.identityModel>
<span data-ttu-id="82150-102">Stellt die Konfiguration zum Aktivieren von WIF-Optionen (Windows Identity Foundation) in-Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="82150-102">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel>**  
  
## <a name="syntax"></a><span data-ttu-id="82150-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="82150-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82150-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="82150-104">Attributes and Elements</span></span>  
 <span data-ttu-id="82150-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82150-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82150-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="82150-106">Attributes</span></span>  
 <span data-ttu-id="82150-107">Keine</span><span class="sxs-lookup"><span data-stu-id="82150-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82150-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82150-108">Child Elements</span></span>  
  
|<span data-ttu-id="82150-109">Element</span><span class="sxs-lookup"><span data-stu-id="82150-109">Element</span></span>|<span data-ttu-id="82150-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="82150-110">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="82150-111">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="82150-111">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82150-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82150-112">Parent Elements</span></span>  
  
|<span data-ttu-id="82150-113">Element</span><span class="sxs-lookup"><span data-stu-id="82150-113">Element</span></span>|<span data-ttu-id="82150-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="82150-114">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="82150-115">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="82150-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82150-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="82150-116">Remarks</span></span>  
 <span data-ttu-id="82150-117">Fügen Sie `<system.identityModel>` der Konfigurationsdatei einen Abschnitt hinzu, um einen Dienst oder eine Anwendung für die Verwendung von Windows Identity Foundation (WIF) zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="82150-117">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="82150-118">Das- `<system.identityModel>` Element wird durch die- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="82150-118">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82150-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82150-119">Example</span></span>  
 <span data-ttu-id="82150-120">Im folgenden Beispiel wird gezeigt, wie einer Konfigurationsdatei ein-Abschnitt hinzugefügt wird `<system.identityModel>` .</span><span class="sxs-lookup"><span data-stu-id="82150-120">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="82150-121">Sie müssen zunächst den Konfigurations Abschnitt und die Namespace Deklaration unter dem-Element hinzufügen `<configSections>` .</span><span class="sxs-lookup"><span data-stu-id="82150-121">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="82150-122">Anschließend können Sie das- `<system.IdentityModel>` Element der Konfigurationsdatei hinzufügen, um eine oder mehrere Identitäts Konfigurationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="82150-122">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82150-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82150-123">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
