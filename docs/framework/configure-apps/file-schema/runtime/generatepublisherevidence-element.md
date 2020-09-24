---
title: <generatePublisherEvidence>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 506e7873fab8e41fce121587c22d85600a8b1760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158772"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="af1e2-102">\<generatePublisherEvidence>-Element</span><span class="sxs-lookup"><span data-stu-id="af1e2-102">\<generatePublisherEvidence> Element</span></span>

<span data-ttu-id="af1e2-103">Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher> Beweise für Code Zugriffssicherheit (CAS) erstellt.</span><span class="sxs-lookup"><span data-stu-id="af1e2-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="af1e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af1e2-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af1e2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af1e2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="af1e2-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af1e2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af1e2-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="af1e2-107">Attributes</span></span>  
  
|<span data-ttu-id="af1e2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="af1e2-108">Attribute</span></span>|<span data-ttu-id="af1e2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af1e2-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="af1e2-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="af1e2-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="af1e2-111">Gibt an, ob die Laufzeit <xref:System.Security.Policy.Publisher> Beweise erstellt.</span><span class="sxs-lookup"><span data-stu-id="af1e2-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="af1e2-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="af1e2-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="af1e2-113">Wert</span><span class="sxs-lookup"><span data-stu-id="af1e2-113">Value</span></span>|<span data-ttu-id="af1e2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af1e2-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="af1e2-115">Erstellt keine <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="af1e2-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="af1e2-116">Erstellt <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="af1e2-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="af1e2-117">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="af1e2-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af1e2-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af1e2-118">Child Elements</span></span>  

 <span data-ttu-id="af1e2-119">Keine</span><span class="sxs-lookup"><span data-stu-id="af1e2-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af1e2-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af1e2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="af1e2-121">Element</span><span class="sxs-lookup"><span data-stu-id="af1e2-121">Element</span></span>|<span data-ttu-id="af1e2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af1e2-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="af1e2-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="af1e2-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="af1e2-124">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="af1e2-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af1e2-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="af1e2-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af1e2-126">In der .NET Framework 4 und höher hat dieses Element keine Auswirkung auf die assemblyladezeiten.</span><span class="sxs-lookup"><span data-stu-id="af1e2-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="af1e2-127">Weitere Informationen finden Sie im Abschnitt "Vereinfachung der Sicherheitsrichtlinie" unter " [Sicherheitsänderungen](/previous-versions/dotnet/framework/security/security-changes)".</span><span class="sxs-lookup"><span data-stu-id="af1e2-127">For more information, see the "Security Policy Simplification" section in [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="af1e2-128">Der Common Language Runtime (CLR) versucht, die Authenticode-Signatur zur Ladezeit zu überprüfen, um einen <xref:System.Security.Policy.Publisher> Beweis für die Assembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af1e2-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="af1e2-129">Die meisten Anwendungen benötigen jedoch standardmäßig keine <xref:System.Security.Policy.Publisher> Beweise.</span><span class="sxs-lookup"><span data-stu-id="af1e2-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="af1e2-130">Die Standard-CAS-Richtlinie beruht nicht auf dem <xref:System.Security.Policy.PublisherMembershipCondition> .</span><span class="sxs-lookup"><span data-stu-id="af1e2-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="af1e2-131">Vermeiden Sie unnötige Startkosten im Zusammenhang mit der Überprüfung der Herausgeber Signatur, es sei denn, Ihre Anwendung wird auf einem Computer mit einer benutzerdefinierten CAS-Richtlinie ausgeführt oder beabsichtigt, Anforderungen für <xref:System.Security.Permissions.PublisherIdentityPermission> in einer teilweise vertrauenswürdigen Umgebung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="af1e2-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="af1e2-132">(Ansprüche für Identitäts Berechtigungen sind immer erfolgreich in einer vollständig vertrauenswürdigen Umgebung.)</span><span class="sxs-lookup"><span data-stu-id="af1e2-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af1e2-133">Wir empfehlen, dass Dienste das- `<generatePublisherEvidence>` Element verwenden, um die Startleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="af1e2-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="af1e2-134">Mithilfe dieses Elements können auch Verzögerungen vermieden werden, die einen Timeout und den Abbruch des Dienst Starts verursachen können.</span><span class="sxs-lookup"><span data-stu-id="af1e2-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="af1e2-135">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="af1e2-135">Configuration File</span></span>  

 <span data-ttu-id="af1e2-136">Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af1e2-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af1e2-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af1e2-137">Example</span></span>  

 <span data-ttu-id="af1e2-138">Das folgende Beispiel zeigt, wie das- `<generatePublisherEvidence>` Element verwendet wird, um die Überprüfung der CAS-Herausgeber Richtlinie für eine Anwendung zu deaktivieren</span><span class="sxs-lookup"><span data-stu-id="af1e2-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af1e2-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af1e2-139">See also</span></span>

- [<span data-ttu-id="af1e2-140">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="af1e2-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="af1e2-141">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="af1e2-141">Configuration File Schema</span></span>](../index.md)
