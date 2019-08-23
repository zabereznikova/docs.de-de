---
title: <routing> von <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 73a610056f94efe144705968eaf97c8314c1ae0d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934199"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="c09fd-102">\<Routing > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="c09fd-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="c09fd-103">Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c09fd-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="c09fd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c09fd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c09fd-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c09fd-105">\<behaviors></span></span>  
<span data-ttu-id="c09fd-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c09fd-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c09fd-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c09fd-107">\<behavior></span></span>  
<span data-ttu-id="c09fd-108">\<routing></span><span class="sxs-lookup"><span data-stu-id="c09fd-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c09fd-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c09fd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c09fd-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c09fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c09fd-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c09fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c09fd-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c09fd-112">Attributes</span></span>  
  
|<span data-ttu-id="c09fd-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c09fd-113">Attribute</span></span>|<span data-ttu-id="c09fd-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c09fd-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c09fd-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="c09fd-115">filterTable</span></span>|<span data-ttu-id="c09fd-116">Eine Zeichenfolge, die den Namen der Routingtabelle angibt, die Filter enthält, die vom Routingdienst ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c09fd-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="c09fd-117">Dieser Wert muss mit dem `name` -Attribut [ \<eines Filter Table >](filtertable.md) -Elements im [ \<> Abschnitt "filtertables](filtertables.md) " identisch sein.</span><span class="sxs-lookup"><span data-stu-id="c09fd-117">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="c09fd-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="c09fd-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="c09fd-119">Ein boolescher Wert, der angibt, ob der Filter sowohl den Nachrichtentext als auch den Header oder nur den Header prüft.</span><span class="sxs-lookup"><span data-stu-id="c09fd-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="c09fd-120">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="c09fd-120">The default is `true`.</span></span>|  
|<span data-ttu-id="c09fd-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="c09fd-121">soapProcessingEnabled</span></span>|<span data-ttu-id="c09fd-122">Ein boolescher Wert, der angibt, ob SOAP-Verarbeitung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="c09fd-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c09fd-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c09fd-123">Child Elements</span></span>  
 <span data-ttu-id="c09fd-124">Keine</span><span class="sxs-lookup"><span data-stu-id="c09fd-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c09fd-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c09fd-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c09fd-126">Element</span><span class="sxs-lookup"><span data-stu-id="c09fd-126">Element</span></span>|<span data-ttu-id="c09fd-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c09fd-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c09fd-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c09fd-128">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c09fd-129">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="c09fd-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c09fd-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c09fd-130">Remarks</span></span>  
 <span data-ttu-id="c09fd-131">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Diensts hinzugefügt wird, aktiviert es Routing für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="c09fd-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="c09fd-132">Sie können die Routingtabelle angeben, die vom Dienst in diesem Element verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c09fd-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="c09fd-133">Mit diesem Konfigurationsabschnitt können Sie die Routingeinstellungen dynamisch ändern, wenn sich das Bereitstellungsmuster ändert.</span><span class="sxs-lookup"><span data-stu-id="c09fd-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="c09fd-134">Zur Laufzeit können Sie eine eigene Routingerweiterung mit neuen Routingeinstellungen registrieren, und der Routingdienst verwendet die aktualisierten Konfigurationsinformationen für neue Nachrichten und Sitzungen, während die Regeln für Nachrichten/Sitzungen in Bearbeitung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c09fd-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="c09fd-135">So erhalten Sie die Möglichkeit, den Routingdienst zur Laufzeit sitzungssicher neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c09fd-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
