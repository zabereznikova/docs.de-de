---
title: <routing> von <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 0998f4fc61de7099879ba6e122eed1e64588baec
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397733"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="412fd-102">\<routing> von \<serviceBehavior></span><span class="sxs-lookup"><span data-stu-id="412fd-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="412fd-103">Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="412fd-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**  
  
## <a name="syntax"></a><span data-ttu-id="412fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="412fd-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="412fd-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="412fd-105">Attributes and Elements</span></span>  
 <span data-ttu-id="412fd-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="412fd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="412fd-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="412fd-107">Attributes</span></span>  
  
|<span data-ttu-id="412fd-108">attribute</span><span class="sxs-lookup"><span data-stu-id="412fd-108">Attribute</span></span>|<span data-ttu-id="412fd-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="412fd-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="412fd-110">filterTable</span><span class="sxs-lookup"><span data-stu-id="412fd-110">filterTable</span></span>|<span data-ttu-id="412fd-111">Eine Zeichenfolge, die den Namen der Routingtabelle angibt, die Filter enthält, die vom Routingdienst ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="412fd-111">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="412fd-112">Dieser Wert muss mit dem- `name` Attribut eines- [\<filterTable>](filtertable.md) Elements im-Abschnitt identisch sein [\<filterTables>](filtertables.md) .</span><span class="sxs-lookup"><span data-stu-id="412fd-112">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="412fd-113">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="412fd-113">routeOnHeaderOnly</span></span>|<span data-ttu-id="412fd-114">Ein boolescher Wert, der angibt, ob der Filter sowohl den Nachrichtentext als auch den Header oder nur den Header prüft.</span><span class="sxs-lookup"><span data-stu-id="412fd-114">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="412fd-115">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="412fd-115">The default is `true`.</span></span>|  
|<span data-ttu-id="412fd-116">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="412fd-116">soapProcessingEnabled</span></span>|<span data-ttu-id="412fd-117">Ein boolescher Wert, der angibt, ob SOAP-Verarbeitung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="412fd-117">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="412fd-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="412fd-118">Child Elements</span></span>  
 <span data-ttu-id="412fd-119">Keine</span><span class="sxs-lookup"><span data-stu-id="412fd-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="412fd-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="412fd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="412fd-121">Element</span><span class="sxs-lookup"><span data-stu-id="412fd-121">Element</span></span>|<span data-ttu-id="412fd-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="412fd-122">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="412fd-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="412fd-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="412fd-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="412fd-124">Remarks</span></span>  
 <span data-ttu-id="412fd-125">Wenn dieses Konfigurationselement der Verhaltenskonfiguration des Diensts hinzugefügt wird, aktiviert es Routing für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="412fd-125">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="412fd-126">Sie können die Routingtabelle angeben, die vom Dienst in diesem Element verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="412fd-126">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="412fd-127">Mit diesem Konfigurationsabschnitt können Sie die Routingeinstellungen dynamisch ändern, wenn sich das Bereitstellungsmuster ändert.</span><span class="sxs-lookup"><span data-stu-id="412fd-127">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="412fd-128">Zur Laufzeit können Sie eine eigene Routingerweiterung mit neuen Routingeinstellungen registrieren, und der Routingdienst verwendet die aktualisierten Konfigurationsinformationen für neue Nachrichten und Sitzungen, während die Regeln für Nachrichten/Sitzungen in Bearbeitung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="412fd-128">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="412fd-129">So erhalten Sie die Möglichkeit, den Routingdienst zur Laufzeit sitzungssicher neu zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="412fd-129">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
