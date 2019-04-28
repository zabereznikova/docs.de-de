---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 0b014a9d797ded61949a374486824ee3ebc34661
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673479"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="fda22-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="fda22-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="fda22-102">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="fda22-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="fda22-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fda22-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fda22-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fda22-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda22-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fda22-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fda22-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fda22-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fda22-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fda22-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fda22-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="fda22-108">Attributes</span></span>  
  
|<span data-ttu-id="fda22-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="fda22-109">Attribute</span></span>|<span data-ttu-id="fda22-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fda22-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fda22-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="fda22-111">discoveryEndpoint</span></span>|<span data-ttu-id="fda22-112">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fda22-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fda22-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fda22-113">Child Elements</span></span>  
  
|<span data-ttu-id="fda22-114">Element</span><span class="sxs-lookup"><span data-stu-id="fda22-114">Element</span></span>|<span data-ttu-id="fda22-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fda22-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fda22-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fda22-116">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fda22-117">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fda22-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="fda22-118">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden, für die) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).</span><span class="sxs-lookup"><span data-stu-id="fda22-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fda22-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fda22-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fda22-120">Element</span><span class="sxs-lookup"><span data-stu-id="fda22-120">Element</span></span>|<span data-ttu-id="fda22-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fda22-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fda22-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fda22-122">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fda22-123">Definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="fda22-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fda22-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fda22-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
