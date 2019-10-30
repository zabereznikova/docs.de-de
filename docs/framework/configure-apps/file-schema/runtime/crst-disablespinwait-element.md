---
title: < Crst_DisableSpinWait >-Element
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117639"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="40580-102">\<Crst_DisableSpinWait >-Element</span><span class="sxs-lookup"><span data-stu-id="40580-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="40580-103">Gibt an, ob das warten auf einen kritischen Abschnitt beim Konflikten deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="40580-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
<span data-ttu-id="40580-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="40580-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="40580-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="40580-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="40580-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Crst_DisableSpinWait >**</span><span class="sxs-lookup"><span data-stu-id="40580-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40580-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="40580-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40580-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="40580-108">Attributes and Elements</span></span>

<span data-ttu-id="40580-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="40580-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40580-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="40580-110">Attributes</span></span>  
  
|<span data-ttu-id="40580-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="40580-111">Attribute</span></span>|<span data-ttu-id="40580-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40580-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40580-113">**wodurch**</span><span class="sxs-lookup"><span data-stu-id="40580-113">**enabled**</span></span>|<span data-ttu-id="40580-114">Gibt an, ob das Drehfeld für kritische Abschnitte, bei denen ein Konflikt besteht, deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="40580-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="40580-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="40580-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="40580-116">Wert</span><span class="sxs-lookup"><span data-stu-id="40580-116">Value</span></span>|<span data-ttu-id="40580-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40580-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40580-118">1</span><span class="sxs-lookup"><span data-stu-id="40580-118">1</span></span>|<span data-ttu-id="40580-119">Die Drehung wird deaktiviert, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="40580-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="40580-120">0</span><span class="sxs-lookup"><span data-stu-id="40580-120">0</span></span>|<span data-ttu-id="40580-121">"Spin-warten" nicht deaktivieren, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="40580-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="40580-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="40580-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40580-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40580-123">Child Elements</span></span>  
 <span data-ttu-id="40580-124">Keine</span><span class="sxs-lookup"><span data-stu-id="40580-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40580-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="40580-125">Parent Elements</span></span>  
  
|<span data-ttu-id="40580-126">Element</span><span class="sxs-lookup"><span data-stu-id="40580-126">Element</span></span>|<span data-ttu-id="40580-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40580-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="40580-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="40580-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="40580-129">Enthält Informationen zu verschiedenen Lauf Zeit Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="40580-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="40580-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40580-130">Example</span></span>  

<span data-ttu-id="40580-131">Im folgenden Beispiel wird die Drehung beim Konflikt in kritischen Abschnitten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="40580-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40580-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40580-132">See also</span></span>

- [<span data-ttu-id="40580-133">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="40580-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="40580-134">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="40580-134">Configuration File Schema</span></span>](../index.md)
