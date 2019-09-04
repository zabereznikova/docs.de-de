---
title: < Crst_DisableSpinWait >-Element
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a91e21120ecebbe7af2fb93798bc68d274fa92c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252717"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="82cc6-102">\<Crst_DisableSpinWait >-Element</span><span class="sxs-lookup"><span data-stu-id="82cc6-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="82cc6-103">Gibt an, ob das warten auf einen kritischen Abschnitt beim Konflikten deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="82cc6-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
<span data-ttu-id="82cc6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="82cc6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="82cc6-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="82cc6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="82cc6-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Crst_DisableSpinWait >**</span><span class="sxs-lookup"><span data-stu-id="82cc6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82cc6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="82cc6-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82cc6-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="82cc6-108">Attributes and Elements</span></span>

<span data-ttu-id="82cc6-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82cc6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82cc6-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="82cc6-110">Attributes</span></span>  
  
|<span data-ttu-id="82cc6-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="82cc6-111">Attribute</span></span>|<span data-ttu-id="82cc6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82cc6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82cc6-113">**wodurch**</span><span class="sxs-lookup"><span data-stu-id="82cc6-113">**enabled**</span></span>|<span data-ttu-id="82cc6-114">Gibt an, ob das Drehfeld für kritische Abschnitte, bei denen ein Konflikt besteht, deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="82cc6-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="82cc6-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="82cc6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="82cc6-116">Wert</span><span class="sxs-lookup"><span data-stu-id="82cc6-116">Value</span></span>|<span data-ttu-id="82cc6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82cc6-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82cc6-118">1</span><span class="sxs-lookup"><span data-stu-id="82cc6-118">1</span></span>|<span data-ttu-id="82cc6-119">Die Drehung wird deaktiviert, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="82cc6-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="82cc6-120">0</span><span class="sxs-lookup"><span data-stu-id="82cc6-120">0</span></span>|<span data-ttu-id="82cc6-121">"Spin-warten" nicht deaktivieren, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="82cc6-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="82cc6-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="82cc6-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82cc6-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82cc6-123">Child Elements</span></span>  
 <span data-ttu-id="82cc6-124">Keine</span><span class="sxs-lookup"><span data-stu-id="82cc6-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82cc6-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82cc6-125">Parent Elements</span></span>  
  
|<span data-ttu-id="82cc6-126">Element</span><span class="sxs-lookup"><span data-stu-id="82cc6-126">Element</span></span>|<span data-ttu-id="82cc6-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82cc6-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="82cc6-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="82cc6-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="82cc6-129">Enthält Informationen zu verschiedenen Lauf Zeit Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="82cc6-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="82cc6-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82cc6-130">Example</span></span>  

<span data-ttu-id="82cc6-131">Im folgenden Beispiel wird die Drehung beim Konflikt in kritischen Abschnitten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="82cc6-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="82cc6-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82cc6-132">See also</span></span>

- [<span data-ttu-id="82cc6-133">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="82cc6-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="82cc6-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="82cc6-134">Configuration File Schema</span></span>](../index.md)
