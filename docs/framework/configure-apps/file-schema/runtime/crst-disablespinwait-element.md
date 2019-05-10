---
title: < Crst_DisableSpinWait >-element
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f89f0558c11e229fef2ca3cd619e3c033f12c858
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754678"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="d9470-102">\<Crst_DisableSpinWait >-Element</span><span class="sxs-lookup"><span data-stu-id="d9470-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="d9470-103">Gibt an, ob die Spin-warten auf einen kritischen Abschnitt bei Konflikten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d9470-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="d9470-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d9470-104">\<configuration></span></span>  
<span data-ttu-id="d9470-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d9470-105">\<runtime></span></span>  
<span data-ttu-id="d9470-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="d9470-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9470-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9470-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9470-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d9470-108">Attributes and Elements</span></span>

<span data-ttu-id="d9470-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9470-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9470-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d9470-110">Attributes</span></span>  
  
|<span data-ttu-id="d9470-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="d9470-111">Attribute</span></span>|<span data-ttu-id="d9470-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9470-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9470-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="d9470-113">**enabled**</span></span>|<span data-ttu-id="d9470-114">Gibt an, ob Spin-warten auf kritische Abschnitte, wenn diese Anzahl von Konflikten vorliegt deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d9470-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d9470-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="d9470-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d9470-116">Wert</span><span class="sxs-lookup"><span data-stu-id="d9470-116">Value</span></span>|<span data-ttu-id="d9470-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9470-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d9470-118">1</span><span class="sxs-lookup"><span data-stu-id="d9470-118">1</span></span>|<span data-ttu-id="d9470-119">Deaktivieren Sie Spin-Waiting aus, wenn ein Kritischer Abschnitt kann nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d9470-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="d9470-120">0</span><span class="sxs-lookup"><span data-stu-id="d9470-120">0</span></span>|<span data-ttu-id="d9470-121">Drehfeld-Waiting kann nicht deaktiviert werden, wenn ein Kritischer Abschnitt kann nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d9470-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="d9470-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="d9470-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9470-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9470-123">Child Elements</span></span>  
 <span data-ttu-id="d9470-124">Keine</span><span class="sxs-lookup"><span data-stu-id="d9470-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9470-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9470-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d9470-126">Element</span><span class="sxs-lookup"><span data-stu-id="d9470-126">Element</span></span>|<span data-ttu-id="d9470-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9470-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d9470-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d9470-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d9470-129">Enthält Informationen über verschiedene Konfigurationseinstellungen für die Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d9470-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d9470-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9470-130">Example</span></span>  

<span data-ttu-id="d9470-131">Das folgende Beispiel deaktiviert die Spin-Waiting in kritischen Abschnitten bei Konflikten.</span><span class="sxs-lookup"><span data-stu-id="d9470-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9470-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9470-132">See also</span></span>

- [<span data-ttu-id="d9470-133">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="d9470-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d9470-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="d9470-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
