---
title: '&lt;routing&gt; von &lt;serviceBehavior&gt;'
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 5fb7febe365f73acf09ba74b07215fe9cc659efb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750751"
---
# <a name="ltroutinggt-of-ltservicebehaviorgt"></a><span data-ttu-id="f8c52-102">&lt;routing&gt; von &lt;serviceBehavior&gt;</span><span class="sxs-lookup"><span data-stu-id="f8c52-102">&lt;routing&gt; of &lt;serviceBehavior&gt;</span></span>
<span data-ttu-id="f8c52-103">Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f8c52-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="f8c52-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f8c52-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f8c52-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f8c52-105">\<behaviors></span></span>  
<span data-ttu-id="f8c52-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f8c52-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f8c52-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="f8c52-107">\<behavior></span></span>  
<span data-ttu-id="f8c52-108">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="f8c52-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8c52-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8c52-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8c52-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f8c52-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f8c52-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f8c52-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8c52-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f8c52-112">Attributes</span></span>  
  
|<span data-ttu-id="f8c52-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f8c52-113">Attribute</span></span>|<span data-ttu-id="f8c52-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8c52-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8c52-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="f8c52-115">filterTable</span></span>|<span data-ttu-id="f8c52-116">Eine Zeichenfolge, die den Namen der Routingtabelle angibt, die Filter enthält, die vom Routingdienst ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f8c52-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="f8c52-117">Dieser Wert übereinstimmen der `name` Attribut eine [ \<FilterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) Element in der [ \<FilterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="f8c52-117">This value must match the `name` attribute of a [\<filterTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element in the [\<filterTables>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) section.</span></span>|  
|<span data-ttu-id="f8c52-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="f8c52-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="f8c52-119">Ein boolescher Wert, der angibt, ob der Filter sowohl den Nachrichtentext als auch den Header oder nur den Header prüft.</span><span class="sxs-lookup"><span data-stu-id="f8c52-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="f8c52-120">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="f8c52-120">The default is `true`.</span></span>|  
|<span data-ttu-id="f8c52-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="f8c52-121">soapProcessingEnabled</span></span>|<span data-ttu-id="f8c52-122">Ein boolescher Wert, der angibt, ob SOAP-Verarbeitung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="f8c52-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8c52-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8c52-123">Child Elements</span></span>  
 <span data-ttu-id="f8c52-124">Keine</span><span class="sxs-lookup"><span data-stu-id="f8c52-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8c52-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8c52-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f8c52-126">Element</span><span class="sxs-lookup"><span data-stu-id="f8c52-126">Element</span></span>|<span data-ttu-id="f8c52-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8c52-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8c52-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f8c52-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f8c52-129">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="f8c52-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8c52-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8c52-130">Remarks</span></span>  
 <span data-ttu-id="f8c52-131">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Diensts hinzugefügt wird, aktiviert es Routing für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="f8c52-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="f8c52-132">Sie können die Routingtabelle angeben, die vom Dienst in diesem Element verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f8c52-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="f8c52-133">Mit diesem Konfigurationsabschnitt können Sie die Routingeinstellungen dynamisch ändern, wenn sich das Bereitstellungsmuster ändert.</span><span class="sxs-lookup"><span data-stu-id="f8c52-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="f8c52-134">Zur Laufzeit können Sie eine eigene Routingerweiterung mit neuen Routingeinstellungen registrieren, und der Routingdienst verwendet die aktualisierten Konfigurationsinformationen für neue Nachrichten und Sitzungen, während die Regeln für Nachrichten/Sitzungen in Bearbeitung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f8c52-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="f8c52-135">So erhalten Sie die Möglichkeit, den Routingdienst zur Laufzeit sitzungssicher neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f8c52-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
  
