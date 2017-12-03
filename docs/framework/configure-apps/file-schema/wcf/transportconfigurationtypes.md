---
title: '&lt;transportConfigurationTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa136f75fda4a87171a8ca3e369e7cb8621ac398
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="529ac-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="529ac-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="529ac-103">Stellt eine Auflistung von Konfigurationselementen dar, die den Typ eines bestimmten Transports identifizieren.</span><span class="sxs-lookup"><span data-stu-id="529ac-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="529ac-104">Diese kann verwendet werden, um benutzerdefinierte WAS-Protokolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="529ac-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="529ac-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="529ac-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="529ac-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="529ac-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="529ac-107">\<TransportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="529ac-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="529ac-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="529ac-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="529ac-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="529ac-109">Attributes and Elements</span></span>  
 <span data-ttu-id="529ac-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="529ac-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="529ac-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="529ac-111">Attributes</span></span>  
  
|<span data-ttu-id="529ac-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="529ac-112">Attribute</span></span>|<span data-ttu-id="529ac-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="529ac-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="529ac-114">Name</span><span class="sxs-lookup"><span data-stu-id="529ac-114">name</span></span>|<span data-ttu-id="529ac-115">Der Name des Transports.</span><span class="sxs-lookup"><span data-stu-id="529ac-115">The name of the transport</span></span>|  
|<span data-ttu-id="529ac-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="529ac-116">transportConfigurationType</span></span>|<span data-ttu-id="529ac-117">Der Typ, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="529ac-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="529ac-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="529ac-118">Child Elements</span></span>  
  
|<span data-ttu-id="529ac-119">Element</span><span class="sxs-lookup"><span data-stu-id="529ac-119">Element</span></span>|<span data-ttu-id="529ac-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="529ac-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="529ac-121">\<add></span><span class="sxs-lookup"><span data-stu-id="529ac-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="529ac-122">Fügt ein Konfigurationselement hinzu, mit dem der Typ eines bestimmten Transports identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="529ac-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="529ac-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="529ac-123">Parent Elements</span></span>  
  
|<span data-ttu-id="529ac-124">Element</span><span class="sxs-lookup"><span data-stu-id="529ac-124">Element</span></span>|<span data-ttu-id="529ac-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="529ac-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="529ac-126">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="529ac-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="529ac-127">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="529ac-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="529ac-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="529ac-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="529ac-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="529ac-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
