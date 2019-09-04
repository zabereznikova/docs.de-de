---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd3105e573d40ae234ba7e122f20566911124d4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252540"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="ff2d8-102">\<generatePublisherEvidence > Element</span><span class="sxs-lookup"><span data-stu-id="ff2d8-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="ff2d8-103">Gibt an, ob die <xref:System.Security.Policy.Publisher> Laufzeit Beweise für Code Zugriffssicherheit (CAS) erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="ff2d8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff2d8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ff2d8-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff2d8-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ff2d8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence>**</span><span class="sxs-lookup"><span data-stu-id="ff2d8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff2d8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff2d8-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff2d8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ff2d8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ff2d8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff2d8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ff2d8-110">Attributes</span></span>  
  
|<span data-ttu-id="ff2d8-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ff2d8-111">Attribute</span></span>|<span data-ttu-id="ff2d8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff2d8-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ff2d8-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ff2d8-114">Gibt an, ob die <xref:System.Security.Policy.Publisher> Laufzeit Beweise erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ff2d8-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="ff2d8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ff2d8-116">Wert</span><span class="sxs-lookup"><span data-stu-id="ff2d8-116">Value</span></span>|<span data-ttu-id="ff2d8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff2d8-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ff2d8-118">Erstellt <xref:System.Security.Policy.Publisher> keine Beweise.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="ff2d8-119">Erstellt <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="ff2d8-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff2d8-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff2d8-121">Child Elements</span></span>  
 <span data-ttu-id="ff2d8-122">Keine</span><span class="sxs-lookup"><span data-stu-id="ff2d8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff2d8-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff2d8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ff2d8-124">Element</span><span class="sxs-lookup"><span data-stu-id="ff2d8-124">Element</span></span>|<span data-ttu-id="ff2d8-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff2d8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ff2d8-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ff2d8-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff2d8-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff2d8-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff2d8-129">In der .NET Framework 4 und höher hat dieses Element keine Auswirkung auf die assemblyladezeiten.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="ff2d8-130">Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinie" unter " [Sicherheitsänderungen](../../../security/security-changes.md)".</span><span class="sxs-lookup"><span data-stu-id="ff2d8-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="ff2d8-131">Der Common Language Runtime (CLR) versucht, die Authenticode-Signatur zur Ladezeit zu über <xref:System.Security.Policy.Publisher> prüfen, um einen Beweis für die Assembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="ff2d8-132">Die meisten Anwendungen benötigen <xref:System.Security.Policy.Publisher> jedoch standardmäßig keine Beweise.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="ff2d8-133">Die Standard-CAS-Richtlinie beruht <xref:System.Security.Policy.PublisherMembershipCondition>nicht auf dem.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="ff2d8-134">Vermeiden Sie unnötige Startkosten im Zusammenhang mit der Überprüfung der Herausgeber Signatur, es sei denn, Ihre Anwendung wird auf einem Computer mit einer benutzerdefinierten <xref:System.Security.Permissions.PublisherIdentityPermission> CAS-Richtlinie ausgeführt oder beabsichtigt, Anforderungen für in einer teilweise vertrauenswürdigen Umgebung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="ff2d8-135">(Ansprüche für Identitäts Berechtigungen sind immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung.)</span><span class="sxs-lookup"><span data-stu-id="ff2d8-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff2d8-136">Wir empfehlen, dass Dienste das `<generatePublisherEvidence>` -Element verwenden, um die Startleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="ff2d8-137">Mithilfe dieses Elements können auch Verzögerungen vermieden werden, die einen Timeout und den Abbruch des Dienst Starts verursachen können.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ff2d8-138">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ff2d8-138">Configuration File</span></span>  
 <span data-ttu-id="ff2d8-139">Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff2d8-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff2d8-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff2d8-140">Example</span></span>  
 <span data-ttu-id="ff2d8-141">Das folgende Beispiel zeigt, wie das- `<generatePublisherEvidence>` Element verwendet wird, um die Überprüfung der CAS-Herausgeber Richtlinie für eine Anwendung zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="ff2d8-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff2d8-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff2d8-142">See also</span></span>

- [<span data-ttu-id="ff2d8-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ff2d8-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ff2d8-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ff2d8-144">Configuration File Schema</span></span>](../index.md)
