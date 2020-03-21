---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154113"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="95b95-102">\<generatePublisherEvidence> Element</span><span class="sxs-lookup"><span data-stu-id="95b95-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="95b95-103">Gibt an, ob <xref:System.Security.Policy.Publisher> die Laufzeit Beweise für die Codezugriffssicherheit (Code Access Security, CAS) erstellt.</span><span class="sxs-lookup"><span data-stu-id="95b95-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="95b95-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="95b95-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="95b95-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="95b95-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="95b95-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span><span class="sxs-lookup"><span data-stu-id="95b95-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95b95-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="95b95-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95b95-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="95b95-108">Attributes and Elements</span></span>  
 <span data-ttu-id="95b95-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95b95-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95b95-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="95b95-110">Attributes</span></span>  
  
|<span data-ttu-id="95b95-111">attribute</span><span class="sxs-lookup"><span data-stu-id="95b95-111">Attribute</span></span>|<span data-ttu-id="95b95-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95b95-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="95b95-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="95b95-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="95b95-114">Gibt an, ob <xref:System.Security.Policy.Publisher> die Laufzeit Beweise erstellt.</span><span class="sxs-lookup"><span data-stu-id="95b95-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="95b95-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="95b95-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="95b95-116">value</span><span class="sxs-lookup"><span data-stu-id="95b95-116">Value</span></span>|<span data-ttu-id="95b95-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95b95-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="95b95-118">Erstellt keine <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="95b95-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="95b95-119">Erstellt <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="95b95-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="95b95-120">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="95b95-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95b95-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95b95-121">Child Elements</span></span>  
 <span data-ttu-id="95b95-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="95b95-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95b95-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="95b95-123">Parent Elements</span></span>  
  
|<span data-ttu-id="95b95-124">Element</span><span class="sxs-lookup"><span data-stu-id="95b95-124">Element</span></span>|<span data-ttu-id="95b95-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95b95-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="95b95-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="95b95-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="95b95-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="95b95-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95b95-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="95b95-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95b95-129">In .NET Framework 4 und höher hat dieses Element keine Auswirkungen auf die Ladezeiten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="95b95-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="95b95-130">Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinien" unter [Sicherheitsänderungen](../../../security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="95b95-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="95b95-131">Die Common Language Runtime (CLR) versucht, die Authenticode-Signatur zum Zeitpunkt des Ladens zu überprüfen, um Beweise für die Assembly zu erstellen. <xref:System.Security.Policy.Publisher></span><span class="sxs-lookup"><span data-stu-id="95b95-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="95b95-132">Standardmäßig benötigen <xref:System.Security.Policy.Publisher> die meisten Anwendungen jedoch keine Beweise.</span><span class="sxs-lookup"><span data-stu-id="95b95-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="95b95-133">Die Standard-CAS-Richtlinie <xref:System.Security.Policy.PublisherMembershipCondition>verlässt sich nicht auf die .</span><span class="sxs-lookup"><span data-stu-id="95b95-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="95b95-134">Sie sollten die unnötigen Startkosten vermeiden, die mit der Überprüfung der Herausgebersignatur verbunden sind, es <xref:System.Security.Permissions.PublisherIdentityPermission> sei denn, Die Anwendung wird auf einem Computer mit benutzerdefinierten CAS-Richtlinien ausgeführt oder beabsichtigt, Anforderungen für eine umgebung mit teilweisem Vertrauen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="95b95-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="95b95-135">(Anforderungen an Identitätsberechtigungen sind in einer Umgebung mit voller Vertrauenswürdigkeit immer erfolgreich.)</span><span class="sxs-lookup"><span data-stu-id="95b95-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95b95-136">Es wird empfohlen, `<generatePublisherEvidence>` dass Dienste das Element verwenden, um die Startleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="95b95-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="95b95-137">Die Verwendung dieses Elements kann auch dazu beitragen, Verzögerungen zu vermeiden, die zu einem Timeout und zum Abbruch des Dienststarts führen können.</span><span class="sxs-lookup"><span data-stu-id="95b95-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="95b95-138">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="95b95-138">Configuration File</span></span>  
 <span data-ttu-id="95b95-139">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95b95-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95b95-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="95b95-140">Example</span></span>  
 <span data-ttu-id="95b95-141">Das folgende Beispiel zeigt, `<generatePublisherEvidence>` wie sie das Element verwenden, um die Überprüfung auf CAS-Herausgeberrichtlinie für eine Anwendung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="95b95-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95b95-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95b95-142">See also</span></span>

- [<span data-ttu-id="95b95-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="95b95-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="95b95-144">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="95b95-144">Configuration File Schema</span></span>](../index.md)
