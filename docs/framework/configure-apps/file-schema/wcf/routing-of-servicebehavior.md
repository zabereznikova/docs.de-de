---
title: <routing> von <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: cd53b720bad5752189f1c30d9e4acd3a66830396
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150881"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="84247-102">\<routing> von \<serviceBehavior></span><span class="sxs-lookup"><span data-stu-id="84247-102">\<routing> of \<serviceBehavior></span></span>

<span data-ttu-id="84247-103">Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="84247-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**  
  
## <a name="syntax"></a><span data-ttu-id="84247-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84247-104">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84247-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="84247-105">Attributes and Elements</span></span>  

 <span data-ttu-id="84247-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="84247-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84247-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="84247-107">Attributes</span></span>  
  
|<span data-ttu-id="84247-108">attribute</span><span class="sxs-lookup"><span data-stu-id="84247-108">Attribute</span></span>|<span data-ttu-id="84247-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84247-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84247-110">filterTable</span><span class="sxs-lookup"><span data-stu-id="84247-110">filterTable</span></span>|<span data-ttu-id="84247-111">Eine Zeichenfolge, die den Namen der Routingtabelle angibt, die Filter enthält, die vom Routingdienst ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="84247-111">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="84247-112">Dieser Wert muss mit dem- `name` Attribut eines- [\<filterTable>](filtertable.md) Elements im-Abschnitt identisch sein [\<filterTables>](filtertables.md) .</span><span class="sxs-lookup"><span data-stu-id="84247-112">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="84247-113">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="84247-113">routeOnHeaderOnly</span></span>|<span data-ttu-id="84247-114">Ein boolescher Wert, der angibt, ob der Filter sowohl den Nachrichtentext als auch den Header oder nur den Header prüft.</span><span class="sxs-lookup"><span data-stu-id="84247-114">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="84247-115">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="84247-115">The default is `true`.</span></span>|  
|<span data-ttu-id="84247-116">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="84247-116">soapProcessingEnabled</span></span>|<span data-ttu-id="84247-117">Ein boolescher Wert, der angibt, ob SOAP-Verarbeitung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="84247-117">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84247-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84247-118">Child Elements</span></span>  

 <span data-ttu-id="84247-119">Keine</span><span class="sxs-lookup"><span data-stu-id="84247-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84247-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="84247-120">Parent Elements</span></span>  
  
|<span data-ttu-id="84247-121">Element</span><span class="sxs-lookup"><span data-stu-id="84247-121">Element</span></span>|<span data-ttu-id="84247-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84247-122">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="84247-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="84247-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84247-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="84247-124">Remarks</span></span>  

 <span data-ttu-id="84247-125">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Diensts hinzugefügt wird, aktiviert es Routing für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="84247-125">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="84247-126">Sie können die Routingtabelle angeben, die vom Dienst in diesem Element verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="84247-126">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="84247-127">Mit diesem Konfigurationsabschnitt können Sie die Routingeinstellungen dynamisch ändern, wenn sich das Bereitstellungsmuster ändert.</span><span class="sxs-lookup"><span data-stu-id="84247-127">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="84247-128">Zur Laufzeit können Sie eine eigene Routingerweiterung mit neuen Routingeinstellungen registrieren, und der Routingdienst verwendet die aktualisierten Konfigurationsinformationen für neue Nachrichten und Sitzungen, während die Regeln für Nachrichten/Sitzungen in Bearbeitung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="84247-128">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="84247-129">So erhalten Sie die Möglichkeit, den Routingdienst zur Laufzeit sitzungssicher neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="84247-129">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
