---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854929"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="138c2-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="138c2-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="138c2-102">Stellt eine Auflistung von Konfigurationselementen dar, die den Typ eines bestimmten Transports identifizieren.</span><span class="sxs-lookup"><span data-stu-id="138c2-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="138c2-103">Diese kann verwendet werden, um benutzerdefinierte WAS-Protokolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="138c2-103">This can be used to add custom WAS protocols.</span></span>  
  
<span data-ttu-id="138c2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="138c2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="138c2-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="138c2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="138c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicehoststingenvironment->** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="138c2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="138c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transportconfigurationtypes->**</span><span class="sxs-lookup"><span data-stu-id="138c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="138c2-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="138c2-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="138c2-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="138c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="138c2-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="138c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="138c2-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="138c2-111">Attributes</span></span>  
  
|<span data-ttu-id="138c2-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="138c2-112">Attribute</span></span>|<span data-ttu-id="138c2-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138c2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="138c2-114">NAME</span><span class="sxs-lookup"><span data-stu-id="138c2-114">name</span></span>|<span data-ttu-id="138c2-115">Der Name des Transports.</span><span class="sxs-lookup"><span data-stu-id="138c2-115">The name of the transport</span></span>|  
|<span data-ttu-id="138c2-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="138c2-116">transportConfigurationType</span></span>|<span data-ttu-id="138c2-117">Der Typ, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="138c2-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="138c2-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="138c2-118">Child Elements</span></span>  
  
|<span data-ttu-id="138c2-119">Element</span><span class="sxs-lookup"><span data-stu-id="138c2-119">Element</span></span>|<span data-ttu-id="138c2-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138c2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="138c2-121">\<add></span><span class="sxs-lookup"><span data-stu-id="138c2-121">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="138c2-122">Fügt ein Konfigurationselement hinzu, mit dem der Typ eines bestimmten Transports identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="138c2-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="138c2-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="138c2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="138c2-124">Element</span><span class="sxs-lookup"><span data-stu-id="138c2-124">Element</span></span>|<span data-ttu-id="138c2-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="138c2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="138c2-126">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="138c2-126">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="138c2-127">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="138c2-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="138c2-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="138c2-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="138c2-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="138c2-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
