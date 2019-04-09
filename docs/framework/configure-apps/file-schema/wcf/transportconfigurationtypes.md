---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083646"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="29b2c-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="29b2c-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="29b2c-102">Stellt eine Auflistung von Konfigurationselementen dar, die den Typ eines bestimmten Transports identifizieren.</span><span class="sxs-lookup"><span data-stu-id="29b2c-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="29b2c-103">Diese kann verwendet werden, um benutzerdefinierte WAS-Protokolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="29b2c-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="29b2c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="29b2c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="29b2c-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="29b2c-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="29b2c-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="29b2c-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29b2c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="29b2c-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29b2c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="29b2c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="29b2c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29b2c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29b2c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="29b2c-110">Attributes</span></span>  
  
|<span data-ttu-id="29b2c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="29b2c-111">Attribute</span></span>|<span data-ttu-id="29b2c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29b2c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29b2c-113">Name</span><span class="sxs-lookup"><span data-stu-id="29b2c-113">name</span></span>|<span data-ttu-id="29b2c-114">Der Name des Transports.</span><span class="sxs-lookup"><span data-stu-id="29b2c-114">The name of the transport</span></span>|  
|<span data-ttu-id="29b2c-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="29b2c-115">transportConfigurationType</span></span>|<span data-ttu-id="29b2c-116">Der Typ, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="29b2c-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29b2c-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29b2c-117">Child Elements</span></span>  
  
|<span data-ttu-id="29b2c-118">Element</span><span class="sxs-lookup"><span data-stu-id="29b2c-118">Element</span></span>|<span data-ttu-id="29b2c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29b2c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29b2c-120">\<add></span><span class="sxs-lookup"><span data-stu-id="29b2c-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="29b2c-121">Fügt ein Konfigurationselement hinzu, mit dem der Typ eines bestimmten Transports identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="29b2c-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29b2c-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29b2c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="29b2c-123">Element</span><span class="sxs-lookup"><span data-stu-id="29b2c-123">Element</span></span>|<span data-ttu-id="29b2c-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29b2c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29b2c-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="29b2c-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="29b2c-126">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="29b2c-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29b2c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29b2c-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="29b2c-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="29b2c-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
