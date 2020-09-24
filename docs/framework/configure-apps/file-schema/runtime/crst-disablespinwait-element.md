---
title: <Crst_DisableSpinWait>-Element
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 45052d99bb297ac39d058fa405fe57a7c991f738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151349"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="43d21-102">\<Crst_DisableSpinWait>-Element</span><span class="sxs-lookup"><span data-stu-id="43d21-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="43d21-103">Gibt an, ob das warten auf einen kritischen Abschnitt beim Konflikten deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d21-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="43d21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43d21-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43d21-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="43d21-105">Attributes and Elements</span></span>

<span data-ttu-id="43d21-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="43d21-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43d21-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="43d21-107">Attributes</span></span>  
  
|<span data-ttu-id="43d21-108">attribute</span><span class="sxs-lookup"><span data-stu-id="43d21-108">Attribute</span></span>|<span data-ttu-id="43d21-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43d21-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43d21-110">**enabled**</span><span class="sxs-lookup"><span data-stu-id="43d21-110">**enabled**</span></span>|<span data-ttu-id="43d21-111">Gibt an, ob das Drehfeld für kritische Abschnitte, bei denen ein Konflikt besteht, deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="43d21-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="43d21-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="43d21-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="43d21-113">Wert</span><span class="sxs-lookup"><span data-stu-id="43d21-113">Value</span></span>|<span data-ttu-id="43d21-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43d21-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="43d21-115">1</span><span class="sxs-lookup"><span data-stu-id="43d21-115">1</span></span>|<span data-ttu-id="43d21-116">Die Drehung wird deaktiviert, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="43d21-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="43d21-117">0</span><span class="sxs-lookup"><span data-stu-id="43d21-117">0</span></span>|<span data-ttu-id="43d21-118">"Spin-warten" nicht deaktivieren, wenn ein kritischer Abschnitt nicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="43d21-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="43d21-119">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="43d21-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43d21-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43d21-120">Child Elements</span></span>  

 <span data-ttu-id="43d21-121">Keine</span><span class="sxs-lookup"><span data-stu-id="43d21-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43d21-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43d21-122">Parent Elements</span></span>  
  
|<span data-ttu-id="43d21-123">Element</span><span class="sxs-lookup"><span data-stu-id="43d21-123">Element</span></span>|<span data-ttu-id="43d21-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43d21-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="43d21-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="43d21-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="43d21-126">Enthält Informationen zu verschiedenen Lauf Zeit Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="43d21-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="43d21-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43d21-127">Example</span></span>  

<span data-ttu-id="43d21-128">Im folgenden Beispiel wird die Drehung beim Konflikt in kritischen Abschnitten deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="43d21-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43d21-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43d21-129">See also</span></span>

- [<span data-ttu-id="43d21-130">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="43d21-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="43d21-131">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="43d21-131">Configuration File Schema</span></span>](../index.md)
