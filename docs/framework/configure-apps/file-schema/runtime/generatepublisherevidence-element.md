---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116576"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="b9550-102">\<generatePublisherEvidence > Element</span><span class="sxs-lookup"><span data-stu-id="b9550-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="b9550-103">Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher> Beweise für Code Zugriffssicherheit (CAS) erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9550-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="b9550-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9550-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b9550-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="b9550-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b9550-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**</span><span class="sxs-lookup"><span data-stu-id="b9550-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9550-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9550-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9550-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b9550-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b9550-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9550-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9550-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b9550-110">Attributes</span></span>  
  
|<span data-ttu-id="b9550-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="b9550-111">Attribute</span></span>|<span data-ttu-id="b9550-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9550-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b9550-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9550-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b9550-114">Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher> Beweis erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9550-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b9550-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="b9550-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b9550-116">Wert</span><span class="sxs-lookup"><span data-stu-id="b9550-116">Value</span></span>|<span data-ttu-id="b9550-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9550-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b9550-118">Erstellt keine <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="b9550-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="b9550-119">Erstellt <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="b9550-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="b9550-120">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="b9550-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9550-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9550-121">Child Elements</span></span>  
 <span data-ttu-id="b9550-122">Keine</span><span class="sxs-lookup"><span data-stu-id="b9550-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9550-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9550-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b9550-124">Element</span><span class="sxs-lookup"><span data-stu-id="b9550-124">Element</span></span>|<span data-ttu-id="b9550-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9550-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b9550-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b9550-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b9550-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="b9550-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9550-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9550-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9550-129">In der .NET Framework 4 und höher hat dieses Element keine Auswirkung auf die assemblyladezeiten.</span><span class="sxs-lookup"><span data-stu-id="b9550-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="b9550-130">Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinie" unter " [Sicherheitsänderungen](../../../security/security-changes.md)".</span><span class="sxs-lookup"><span data-stu-id="b9550-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="b9550-131">Der Common Language Runtime (CLR) versucht, die Authenticode-Signatur zur Ladezeit zu überprüfen, um <xref:System.Security.Policy.Publisher> Beweise für die Assembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9550-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="b9550-132">Die meisten Anwendungen benötigen jedoch standardmäßig keine <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="b9550-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="b9550-133">Die Standard-CAS-Richtlinie beruht nicht auf der <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="b9550-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="b9550-134">Vermeiden Sie unnötige Startkosten im Zusammenhang mit der Überprüfung der Herausgeber Signatur, es sei denn, Ihre Anwendung wird auf einem Computer mit einer benutzerdefinierten CAS-Richtlinie ausgeführt oder beabsichtigt, Anforderungen für <xref:System.Security.Permissions.PublisherIdentityPermission> in einer teilweise vertrauenswürdigen Umgebung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b9550-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="b9550-135">(Ansprüche für Identitäts Berechtigungen sind immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung.)</span><span class="sxs-lookup"><span data-stu-id="b9550-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9550-136">Wir empfehlen, dass Dienste das `<generatePublisherEvidence>`-Element verwenden, um die Startleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b9550-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="b9550-137">Mithilfe dieses Elements können auch Verzögerungen vermieden werden, die einen Timeout und den Abbruch des Dienst Starts verursachen können.</span><span class="sxs-lookup"><span data-stu-id="b9550-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b9550-138">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="b9550-138">Configuration File</span></span>  
 <span data-ttu-id="b9550-139">Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9550-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9550-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9550-140">Example</span></span>  
 <span data-ttu-id="b9550-141">Im folgenden Beispiel wird gezeigt, wie das `<generatePublisherEvidence>`-Element verwendet wird, um die Prüfung der CAS-Herausgeber Richtlinie für eine Anwendung zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="b9550-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9550-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9550-142">See also</span></span>

- [<span data-ttu-id="b9550-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b9550-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b9550-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b9550-144">Configuration File Schema</span></span>](../index.md)
