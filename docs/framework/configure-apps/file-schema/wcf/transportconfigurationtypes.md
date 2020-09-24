---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 6545e1f1be2695d165b89a38c7218e0acdc88bfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162022"
---
# \<transportConfigurationTypes>

<span data-ttu-id="3a14e-101">Stellt eine Auflistung von Konfigurationselementen dar, die den Typ eines bestimmten Transports identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3a14e-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="3a14e-102">Diese kann verwendet werden, um benutzerdefinierte WAS-Protokolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3a14e-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="3a14e-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a14e-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a14e-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a14e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3a14e-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a14e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a14e-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a14e-106">Attributes</span></span>  
  
|<span data-ttu-id="3a14e-107">attribute</span><span class="sxs-lookup"><span data-stu-id="3a14e-107">Attribute</span></span>|<span data-ttu-id="3a14e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a14e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a14e-109">name</span><span class="sxs-lookup"><span data-stu-id="3a14e-109">name</span></span>|<span data-ttu-id="3a14e-110">Der Name des Transports.</span><span class="sxs-lookup"><span data-stu-id="3a14e-110">The name of the transport</span></span>|  
|<span data-ttu-id="3a14e-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="3a14e-111">transportConfigurationType</span></span>|<span data-ttu-id="3a14e-112">Der Typ, mit dem der Transport implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="3a14e-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a14e-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a14e-113">Child Elements</span></span>  
  
|<span data-ttu-id="3a14e-114">Element</span><span class="sxs-lookup"><span data-stu-id="3a14e-114">Element</span></span>|<span data-ttu-id="3a14e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a14e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="3a14e-116">Fügt ein Konfigurationselement hinzu, mit dem der Typ eines bestimmten Transports identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="3a14e-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a14e-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a14e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3a14e-118">Element</span><span class="sxs-lookup"><span data-stu-id="3a14e-118">Element</span></span>|<span data-ttu-id="3a14e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a14e-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="3a14e-120">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="3a14e-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a14e-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a14e-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="3a14e-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="3a14e-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
