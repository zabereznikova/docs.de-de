---
title: <routing> von <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 0998f4fc61de7099879ba6e122eed1e64588baec
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397733"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="2f10b-102">\<Routing > von \<ServiceBehavior ></span><span class="sxs-lookup"><span data-stu-id="2f10b-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="2f10b-103">Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2f10b-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
<span data-ttu-id="2f10b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f10b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f10b-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f10b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2f10b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f10b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2f10b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f10b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="2f10b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2f10b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="2f10b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="2f10b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f10b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f10b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f10b-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2f10b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2f10b-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f10b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f10b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="2f10b-113">Attributes</span></span>  
  
|<span data-ttu-id="2f10b-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="2f10b-114">Attribute</span></span>|<span data-ttu-id="2f10b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f10b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f10b-116">filterTable</span><span class="sxs-lookup"><span data-stu-id="2f10b-116">filterTable</span></span>|<span data-ttu-id="2f10b-117">Eine Zeichenfolge, die den Namen der Routingtabelle angibt, die Filter enthält, die vom Routingdienst ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2f10b-117">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="2f10b-118">Dieser Wert muss mit dem `name` -Attribut [ \<eines Filter Table >](filtertable.md) -Elements im [ \<> Abschnitt "filtertables](filtertables.md) " identisch sein.</span><span class="sxs-lookup"><span data-stu-id="2f10b-118">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="2f10b-119">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="2f10b-119">routeOnHeaderOnly</span></span>|<span data-ttu-id="2f10b-120">Ein boolescher Wert, der angibt, ob der Filter sowohl den Nachrichtentext als auch den Header oder nur den Header prüft.</span><span class="sxs-lookup"><span data-stu-id="2f10b-120">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="2f10b-121">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="2f10b-121">The default is `true`.</span></span>|  
|<span data-ttu-id="2f10b-122">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="2f10b-122">soapProcessingEnabled</span></span>|<span data-ttu-id="2f10b-123">Ein boolescher Wert, der angibt, ob SOAP-Verarbeitung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="2f10b-123">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f10b-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f10b-124">Child Elements</span></span>  
 <span data-ttu-id="2f10b-125">Keine</span><span class="sxs-lookup"><span data-stu-id="2f10b-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f10b-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f10b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2f10b-127">Element</span><span class="sxs-lookup"><span data-stu-id="2f10b-127">Element</span></span>|<span data-ttu-id="2f10b-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f10b-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f10b-129">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2f10b-129">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2f10b-130">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="2f10b-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f10b-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f10b-131">Remarks</span></span>  
 <span data-ttu-id="2f10b-132">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Diensts hinzugefügt wird, aktiviert es Routing für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="2f10b-132">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="2f10b-133">Sie können die Routingtabelle angeben, die vom Dienst in diesem Element verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f10b-133">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="2f10b-134">Mit diesem Konfigurationsabschnitt können Sie die Routingeinstellungen dynamisch ändern, wenn sich das Bereitstellungsmuster ändert.</span><span class="sxs-lookup"><span data-stu-id="2f10b-134">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="2f10b-135">Zur Laufzeit können Sie eine eigene Routingerweiterung mit neuen Routingeinstellungen registrieren, und der Routingdienst verwendet die aktualisierten Konfigurationsinformationen für neue Nachrichten und Sitzungen, während die Regeln für Nachrichten/Sitzungen in Bearbeitung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2f10b-135">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="2f10b-136">So erhalten Sie die Möglichkeit, den Routingdienst zur Laufzeit sitzungssicher neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2f10b-136">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
