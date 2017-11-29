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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b048b160f337897765fa4fcff73a4906534ab08b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="31418-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="31418-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="31418-103">Stellt eine Auflistung von Konfigurationselementen dar, die den Typ eines bestimmten Transports identifizieren.</span><span class="sxs-lookup"><span data-stu-id="31418-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="31418-104">Diese kann verwendet werden, um benutzerdefinierte WAS-Protokolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="31418-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="31418-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="31418-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="31418-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="31418-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="31418-107">\<TransportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="31418-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31418-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="31418-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31418-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="31418-109">Attributes and Elements</span></span>  
 <span data-ttu-id="31418-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31418-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31418-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="31418-111">Attributes</span></span>  
  
|<span data-ttu-id="31418-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="31418-112">Attribute</span></span>|<span data-ttu-id="31418-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31418-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31418-114">Name</span><span class="sxs-lookup"><span data-stu-id="31418-114">name</span></span>|<span data-ttu-id="31418-115">Der Name des Transports.</span><span class="sxs-lookup"><span data-stu-id="31418-115">The name of the transport</span></span>|  
|<span data-ttu-id="31418-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="31418-116">transportConfigurationType</span></span>|<span data-ttu-id="31418-117">Der Typ, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="31418-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31418-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31418-118">Child Elements</span></span>  
  
|<span data-ttu-id="31418-119">Element</span><span class="sxs-lookup"><span data-stu-id="31418-119">Element</span></span>|<span data-ttu-id="31418-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31418-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31418-121">\<add></span><span class="sxs-lookup"><span data-stu-id="31418-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="31418-122">Fügt ein Konfigurationselement hinzu, mit dem der Typ eines bestimmten Transports identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="31418-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31418-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31418-123">Parent Elements</span></span>  
  
|<span data-ttu-id="31418-124">Element</span><span class="sxs-lookup"><span data-stu-id="31418-124">Element</span></span>|<span data-ttu-id="31418-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31418-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31418-126">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="31418-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="31418-127">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="31418-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31418-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31418-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="31418-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="31418-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
