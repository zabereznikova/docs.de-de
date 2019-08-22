---
title: < Crst_DisableSpinWait >-Element
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52dd671f1fbf6fda5bdc92c0935784181eb4b03
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663837"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="229f9-102">\<Crst_DisableSpinWait >-Element</span><span class="sxs-lookup"><span data-stu-id="229f9-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="229f9-103">Gibt an, ob das warten auf einen kritischen Abschnitt beim Konflikten deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="229f9-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="229f9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="229f9-104">\<configuration></span></span>  
<span data-ttu-id="229f9-105">\<Lauf Zeit ></span><span class="sxs-lookup"><span data-stu-id="229f9-105">\<runtime></span></span>  
<span data-ttu-id="229f9-106">\<Crst_DisableSpinWait ></span><span class="sxs-lookup"><span data-stu-id="229f9-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="229f9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="229f9-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="229f9-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="229f9-108">Attributes and Elements</span></span>

<span data-ttu-id="229f9-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="229f9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="229f9-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="229f9-110">Attributes</span></span>  
  
|<span data-ttu-id="229f9-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="229f9-111">Attribute</span></span>|<span data-ttu-id="229f9-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229f9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="229f9-113">**wodurch**</span><span class="sxs-lookup"><span data-stu-id="229f9-113">**enabled**</span></span>|<span data-ttu-id="229f9-114">Gibt an, ob das Drehfeld für kritische Abschnitte, bei denen ein Konflikt besteht, deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="229f9-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="229f9-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="229f9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="229f9-116">Wert</span><span class="sxs-lookup"><span data-stu-id="229f9-116">Value</span></span>|<span data-ttu-id="229f9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229f9-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="229f9-118">1</span><span class="sxs-lookup"><span data-stu-id="229f9-118">1</span></span>|<span data-ttu-id="229f9-119">Die Drehung wird deaktiviert, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="229f9-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="229f9-120">0</span><span class="sxs-lookup"><span data-stu-id="229f9-120">0</span></span>|<span data-ttu-id="229f9-121">"Spin-warten" nicht deaktivieren, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="229f9-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="229f9-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="229f9-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="229f9-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="229f9-123">Child Elements</span></span>  
 <span data-ttu-id="229f9-124">Keine</span><span class="sxs-lookup"><span data-stu-id="229f9-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="229f9-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="229f9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="229f9-126">Element</span><span class="sxs-lookup"><span data-stu-id="229f9-126">Element</span></span>|<span data-ttu-id="229f9-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="229f9-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="229f9-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="229f9-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="229f9-129">Enthält Informationen zu verschiedenen Lauf Zeit Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="229f9-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="229f9-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="229f9-130">Example</span></span>  

<span data-ttu-id="229f9-131">Im folgenden Beispiel wird die Drehung beim Konflikt in kritischen Abschnitten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="229f9-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="229f9-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="229f9-132">See also</span></span>

- [<span data-ttu-id="229f9-133">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="229f9-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="229f9-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="229f9-134">Configuration File Schema</span></span>](../index.md)
