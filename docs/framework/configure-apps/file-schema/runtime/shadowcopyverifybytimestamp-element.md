---
title: <shadowCopyVerifyByTimestamp>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 160f14c856735e1ceac8635506aea52454faea43
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115725"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="59bf1-102">\<shadowCopyVerifyByTimestamp>-Element</span><span class="sxs-lookup"><span data-stu-id="59bf1-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="59bf1-103">Gibt an, ob beim Schatten kopieren das standardmäßige Startverhalten verwendet wird, das in der .NET Framework 4 eingeführt wurde, oder ob das Startverhalten früherer Versionen der .NET Framework wieder hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="59bf1-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**  
  
## <a name="syntax"></a><span data-ttu-id="59bf1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59bf1-104">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59bf1-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="59bf1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="59bf1-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59bf1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59bf1-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="59bf1-107">Attributes</span></span>  
  
|<span data-ttu-id="59bf1-108">attribute</span><span class="sxs-lookup"><span data-stu-id="59bf1-108">Attribute</span></span>|<span data-ttu-id="59bf1-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="59bf1-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59bf1-110">enabled</span><span class="sxs-lookup"><span data-stu-id="59bf1-110">enabled</span></span>|<span data-ttu-id="59bf1-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="59bf1-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="59bf1-112">Gibt an, ob Anwendungs Domänen, die die Schatten Kopien verwenden, beim Start assemblyzeit Stempel vergleichen, um zu bestimmen, ob eine Assembly vor dem Kopieren der Assembly aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="59bf1-112">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="59bf1-113">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="59bf1-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="59bf1-114">Wert</span><span class="sxs-lookup"><span data-stu-id="59bf1-114">Value</span></span>|<span data-ttu-id="59bf1-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="59bf1-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59bf1-116">true</span><span class="sxs-lookup"><span data-stu-id="59bf1-116">true</span></span>|<span data-ttu-id="59bf1-117">Beim Start von werden nur Assemblys kopiert, die aktualisiert wurden, seit Sie zuletzt in das schattenkopiesverzeichnis kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="59bf1-117">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="59bf1-118">Dies ist die Standardeinstellung für die .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="59bf1-118">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="59bf1-119">false</span><span class="sxs-lookup"><span data-stu-id="59bf1-119">false</span></span>|<span data-ttu-id="59bf1-120">Setzt auf das Startverhalten vorheriger Versionen der .NET Framework zurück, bei der alle Dateien beim Start kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="59bf1-120">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59bf1-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59bf1-121">Child Elements</span></span>  
 <span data-ttu-id="59bf1-122">Keine</span><span class="sxs-lookup"><span data-stu-id="59bf1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59bf1-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59bf1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="59bf1-124">Element</span><span class="sxs-lookup"><span data-stu-id="59bf1-124">Element</span></span>|<span data-ttu-id="59bf1-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59bf1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="59bf1-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="59bf1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="59bf1-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="59bf1-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59bf1-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="59bf1-128">Remarks</span></span>  
 <span data-ttu-id="59bf1-129">Beginnend mit dem .NET Framework 4 werden Assemblys nur dann als Schatten kopiert, wenn Ihre Zeitstempel darauf hindeuten, dass Sie geändert wurden, seit Sie zuletzt in das schattenkopieverzeichnis kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="59bf1-129">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="59bf1-130">Dies verbessert die Startzeiten für viele Anwendungen, die Schatten Kopien verwenden, wie in [Schatten Kopien](../../../app-domains/shadow-copy-assemblies.md)von Assemblys beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59bf1-130">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="59bf1-131">Anwendungen, die einen hohen Prozentsatz und eine Häufigkeit von Assemblyaktualisierungen aufweisen, profitieren möglicherweise nicht von dieser Änderung des Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="59bf1-131">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="59bf1-132">In diesem Fall können Sie dieses Element verwenden, um das Verhalten vorheriger Versionen des .NET Framework wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="59bf1-132">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59bf1-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="59bf1-133">Example</span></span>  
 <span data-ttu-id="59bf1-134">Im folgenden Beispiel wird gezeigt, wie Sie das Standard Startverhalten des schattenkopierens in .NET Framework 4 deaktivieren und das Startverhalten vorheriger Versionen der .NET Framework wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="59bf1-134">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59bf1-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59bf1-135">See also</span></span>

- [<span data-ttu-id="59bf1-136">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="59bf1-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="59bf1-137">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="59bf1-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="59bf1-138">Erstellen von Schattenkopien von Assemblys</span><span class="sxs-lookup"><span data-stu-id="59bf1-138">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
