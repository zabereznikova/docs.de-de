---
title: <Crst_DisableSpinWait>-Element
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117639"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="5c2fb-102">\<Crst_DisableSpinWait>-Element</span><span class="sxs-lookup"><span data-stu-id="5c2fb-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="5c2fb-103">Gibt an, ob das warten auf einen kritischen Abschnitt beim Konflikten deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="5c2fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c2fb-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c2fb-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5c2fb-105">Attributes and Elements</span></span>

<span data-ttu-id="5c2fb-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c2fb-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="5c2fb-107">Attributes</span></span>  
  
|<span data-ttu-id="5c2fb-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5c2fb-108">Attribute</span></span>|<span data-ttu-id="5c2fb-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c2fb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c2fb-110">**wodurch**</span><span class="sxs-lookup"><span data-stu-id="5c2fb-110">**enabled**</span></span>|<span data-ttu-id="5c2fb-111">Gibt an, ob das Drehfeld für kritische Abschnitte, bei denen ein Konflikt besteht, deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5c2fb-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="5c2fb-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="5c2fb-113">Wert</span><span class="sxs-lookup"><span data-stu-id="5c2fb-113">Value</span></span>|<span data-ttu-id="5c2fb-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c2fb-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c2fb-115">1</span><span class="sxs-lookup"><span data-stu-id="5c2fb-115">1</span></span>|<span data-ttu-id="5c2fb-116">Die Drehung wird deaktiviert, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="5c2fb-117">0</span><span class="sxs-lookup"><span data-stu-id="5c2fb-117">0</span></span>|<span data-ttu-id="5c2fb-118">"Spin-warten" nicht deaktivieren, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="5c2fb-119">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c2fb-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c2fb-120">Child Elements</span></span>  
 <span data-ttu-id="5c2fb-121">Keine</span><span class="sxs-lookup"><span data-stu-id="5c2fb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c2fb-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c2fb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5c2fb-123">Element</span><span class="sxs-lookup"><span data-stu-id="5c2fb-123">Element</span></span>|<span data-ttu-id="5c2fb-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c2fb-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5c2fb-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5c2fb-126">Enthält Informationen zu verschiedenen Lauf Zeit Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5c2fb-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c2fb-127">Example</span></span>  

<span data-ttu-id="5c2fb-128">Im folgenden Beispiel wird die Drehung beim Konflikt in kritischen Abschnitten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5c2fb-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c2fb-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c2fb-129">See also</span></span>

- [<span data-ttu-id="5c2fb-130">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="5c2fb-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5c2fb-131">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="5c2fb-131">Configuration File Schema</span></span>](../index.md)
