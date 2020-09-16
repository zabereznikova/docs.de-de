---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 11592b055641c0fa2d2b968547dcc5aa40c94600
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541783"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="5a47d-102">\<generatePublisherEvidence>-Element</span><span class="sxs-lookup"><span data-stu-id="5a47d-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="5a47d-103">Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher> Beweise für Code Zugriffssicherheit (CAS) erstellt.</span><span class="sxs-lookup"><span data-stu-id="5a47d-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="5a47d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a47d-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a47d-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5a47d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5a47d-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a47d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a47d-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a47d-107">Attributes</span></span>  
  
|<span data-ttu-id="5a47d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5a47d-108">Attribute</span></span>|<span data-ttu-id="5a47d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a47d-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5a47d-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="5a47d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="5a47d-111">Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher> Beweise erstellt.</span><span class="sxs-lookup"><span data-stu-id="5a47d-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5a47d-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="5a47d-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="5a47d-113">Wert</span><span class="sxs-lookup"><span data-stu-id="5a47d-113">Value</span></span>|<span data-ttu-id="5a47d-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a47d-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5a47d-115">Erstellt keine <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="5a47d-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="5a47d-116">Erstellt <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="5a47d-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="5a47d-117">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="5a47d-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a47d-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a47d-118">Child Elements</span></span>  
 <span data-ttu-id="5a47d-119">Keine</span><span class="sxs-lookup"><span data-stu-id="5a47d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a47d-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a47d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5a47d-121">Element</span><span class="sxs-lookup"><span data-stu-id="5a47d-121">Element</span></span>|<span data-ttu-id="5a47d-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a47d-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5a47d-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5a47d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5a47d-124">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="5a47d-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a47d-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a47d-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a47d-126">In der .NET Framework 4 und höher hat dieses Element keine Auswirkung auf die assemblyladezeiten.</span><span class="sxs-lookup"><span data-stu-id="5a47d-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="5a47d-127">Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinie" unter " [Sicherheitsänderungen](/previous-versions/dotnet/framework/security/security-changes)".</span><span class="sxs-lookup"><span data-stu-id="5a47d-127">For more information, see the "Security Policy Simplification" section in [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="5a47d-128">Der Common Language Runtime (CLR) versucht, die Authenticode-Signatur zur Ladezeit zu überprüfen, um einen <xref:System.Security.Policy.Publisher> Beweis für die Assembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a47d-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="5a47d-129">Die meisten Anwendungen benötigen jedoch standardmäßig keine <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="5a47d-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="5a47d-130">Die Standard-CAS-Richtlinie beruht nicht auf dem <xref:System.Security.Policy.PublisherMembershipCondition> .</span><span class="sxs-lookup"><span data-stu-id="5a47d-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="5a47d-131">Vermeiden Sie unnötige Startkosten im Zusammenhang mit der Überprüfung der Herausgeber Signatur, es sei denn, Ihre Anwendung wird auf einem Computer mit einer benutzerdefinierten CAS-Richtlinie ausgeführt oder beabsichtigt, Anforderungen für <xref:System.Security.Permissions.PublisherIdentityPermission> in einer teilweise vertrauenswürdigen Umgebung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5a47d-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="5a47d-132">(Ansprüche für Identitäts Berechtigungen sind immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung.)</span><span class="sxs-lookup"><span data-stu-id="5a47d-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a47d-133">Wir empfehlen, dass Dienste das- `<generatePublisherEvidence>` Element verwenden, um die Startleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="5a47d-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="5a47d-134">Mithilfe dieses Elements können auch Verzögerungen vermieden werden, die einen Timeout und den Abbruch des Dienst Starts verursachen können.</span><span class="sxs-lookup"><span data-stu-id="5a47d-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="5a47d-135">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="5a47d-135">Configuration File</span></span>  
 <span data-ttu-id="5a47d-136">Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a47d-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a47d-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a47d-137">Example</span></span>  
 <span data-ttu-id="5a47d-138">Das folgende Beispiel zeigt, wie das- `<generatePublisherEvidence>` Element verwendet wird, um die Überprüfung der CAS-Herausgeber Richtlinie für eine Anwendung zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="5a47d-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a47d-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a47d-139">See also</span></span>

- [<span data-ttu-id="5a47d-140">Lauf Zeit Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="5a47d-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5a47d-141">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="5a47d-141">Configuration File Schema</span></span>](../index.md)
