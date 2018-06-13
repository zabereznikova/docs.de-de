---
title: '&lt;"generatePublisherEvidence"&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f56bbef6ed6decf6be4246f649665db4cf0f766
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746019"
---
# <a name="ltgeneratepublisherevidencegt-element"></a><span data-ttu-id="a03f9-102">&lt;"generatePublisherEvidence"&gt; Element</span><span class="sxs-lookup"><span data-stu-id="a03f9-102">&lt;generatePublisherEvidence&gt; Element</span></span>
<span data-ttu-id="a03f9-103">Gibt an, ob die Common Language Runtime erstellt <xref:System.Security.Policy.Publisher> Beweis für die Codezugriffssicherheit (CAS).</span><span class="sxs-lookup"><span data-stu-id="a03f9-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="a03f9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a03f9-104">\<configuration></span></span>  
<span data-ttu-id="a03f9-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="a03f9-105">\<runtime></span></span>  
<span data-ttu-id="a03f9-106">\<"generatePublisherEvidence" ></span><span class="sxs-lookup"><span data-stu-id="a03f9-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a03f9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a03f9-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a03f9-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a03f9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a03f9-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a03f9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a03f9-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a03f9-110">Attributes</span></span>  
  
|<span data-ttu-id="a03f9-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a03f9-111">Attribute</span></span>|<span data-ttu-id="a03f9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a03f9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a03f9-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a03f9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a03f9-114">Gibt an, ob die Common Language Runtime erstellt <xref:System.Security.Policy.Publisher> Beweis.</span><span class="sxs-lookup"><span data-stu-id="a03f9-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a03f9-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="a03f9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a03f9-116">Wert</span><span class="sxs-lookup"><span data-stu-id="a03f9-116">Value</span></span>|<span data-ttu-id="a03f9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a03f9-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a03f9-118">Erstellt keine <xref:System.Security.Policy.Publisher> Beweis.</span><span class="sxs-lookup"><span data-stu-id="a03f9-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="a03f9-119">Erstellt <xref:System.Security.Policy.Publisher> Beweis.</span><span class="sxs-lookup"><span data-stu-id="a03f9-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="a03f9-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a03f9-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a03f9-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a03f9-121">Child Elements</span></span>  
 <span data-ttu-id="a03f9-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a03f9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a03f9-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a03f9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a03f9-124">Element</span><span class="sxs-lookup"><span data-stu-id="a03f9-124">Element</span></span>|<span data-ttu-id="a03f9-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a03f9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a03f9-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a03f9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a03f9-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="a03f9-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a03f9-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a03f9-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a03f9-129">In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher, dieses Element hat keine Auswirkungen auf die Assembly Ladezeiten.</span><span class="sxs-lookup"><span data-stu-id="a03f9-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="a03f9-130">Weitere Informationen finden Sie im Abschnitt "Security Policy Vereinfachung" [Sicherheitsänderungen](../../../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="a03f9-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="a03f9-131">Die common Language Runtime (CLR) versucht, beim Überprüfen der Authenticode-Signatur zur Ladezeit erstellen <xref:System.Security.Policy.Publisher> Beweis für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="a03f9-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="a03f9-132">Allerdings wird standardmäßig die meisten Anwendungen müssen nicht <xref:System.Security.Policy.Publisher> Beweis.</span><span class="sxs-lookup"><span data-stu-id="a03f9-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="a03f9-133">Standard-CAS-Richtlinie nicht auf beruht die <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="a03f9-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="a03f9-134">Vermeiden Sie die Kosten für unnötige Start bei der Überprüfung der Signatur des Herausgebers, wenn Ihre Anwendung auf einem Computer mit benutzerdefinierten CAS-Richtlinie ausgeführt wird oder Forderungen nach erfüllen beabsichtigt ist <xref:System.Security.Permissions.PublisherIdentityPermission> in einer teilweise vertrauenswürdigen Umgebung.</span><span class="sxs-lookup"><span data-stu-id="a03f9-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="a03f9-135">(Anforderungen für Identitätsberechtigungen immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung ausgeführt.)</span><span class="sxs-lookup"><span data-stu-id="a03f9-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a03f9-136">Es wird empfohlen, dass Dienste verwenden die `<generatePublisherEvidence>` Element, um die startleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="a03f9-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="a03f9-137">Mit diesem Element können auch Verzögerungen zu vermeiden, die ein Timeout und den Abbruch des Dienststarts verursachen kann.</span><span class="sxs-lookup"><span data-stu-id="a03f9-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a03f9-138">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a03f9-138">Configuration File</span></span>  
 <span data-ttu-id="a03f9-139">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a03f9-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a03f9-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a03f9-140">Example</span></span>  
 <span data-ttu-id="a03f9-141">Das folgende Beispiel zeigt, wie Sie die `<generatePublisherEvidence>` -Element nach deaktivieren Verleger CAS-Richtlinie für eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a03f9-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a03f9-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a03f9-142">See Also</span></span>  
 [<span data-ttu-id="a03f9-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a03f9-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a03f9-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a03f9-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
