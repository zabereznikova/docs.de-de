---
title: '&lt;ThrowUnobservedTaskExceptions&gt; Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f72bedbaaf0b15ade7ff6b7b8c3edcdfd3fda6d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a><span data-ttu-id="8f206-102">&lt;ThrowUnobservedTaskExceptions&gt; Element</span><span class="sxs-lookup"><span data-stu-id="8f206-102">&lt;ThrowUnobservedTaskExceptions&gt; Element</span></span>
<span data-ttu-id="8f206-103">Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f206-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="8f206-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8f206-104">\<configuration></span></span>  
<span data-ttu-id="8f206-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="8f206-105">\<runtime></span></span>  
<span data-ttu-id="8f206-106">\<ThrowUnobservedTaskExceptions ></span><span class="sxs-lookup"><span data-stu-id="8f206-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f206-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f206-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f206-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8f206-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8f206-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f206-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f206-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8f206-110">Attributes</span></span>  
  
|<span data-ttu-id="8f206-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="8f206-111">Attribute</span></span>|<span data-ttu-id="8f206-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f206-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8f206-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8f206-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8f206-114">Gibt an, ob der Task nicht behandelten Ausnahmen den ausgeführten Prozess beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f206-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8f206-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="8f206-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8f206-116">Wert</span><span class="sxs-lookup"><span data-stu-id="8f206-116">Value</span></span>|<span data-ttu-id="8f206-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f206-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8f206-118">Den ausgeführten Prozess für eine behandelte Ausnahme einer Aufgabe wird nicht beendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f206-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="8f206-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="8f206-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8f206-120">Beendet den ausgeführten Prozess für eine Aufgabe nicht behandelte Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="8f206-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f206-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f206-121">Child Elements</span></span>  
 <span data-ttu-id="8f206-122">Keine</span><span class="sxs-lookup"><span data-stu-id="8f206-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f206-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f206-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8f206-124">Element</span><span class="sxs-lookup"><span data-stu-id="8f206-124">Element</span></span>|<span data-ttu-id="8f206-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f206-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8f206-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8f206-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8f206-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="8f206-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="8f206-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f206-128">Remarks</span></span>  
 <span data-ttu-id="8f206-129">Wenn eine Ausnahme, die mit zugeordnetem eine <xref:System.Threading.Tasks.Task> nicht festgestellt wurde, besteht keine <xref:System.Threading.Tasks.Task.Wait%2A> Vorgang, der das übergeordnete Element ist nicht angefügt, und die <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> Eigenschaft wurde nicht gelesen, gilt die Ausnahme einer Aufgabe nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="8f206-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="8f206-130">In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], von Standard, falls ein <xref:System.Threading.Tasks.Task> , besitzt eine nicht überwachte Ausnahme ist die Garbage Collection, der Finalizer löst eine Ausnahme aus und beendet den Prozess.</span><span class="sxs-lookup"><span data-stu-id="8f206-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="8f206-131">Die Beendigung des Prozesses wird durch die zeitliche Abfolge der Garbagecollection und Finalisierung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="8f206-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="8f206-132">Für Entwickler zum Schreiben von asynchronem Code auf Grundlage der Aufgaben, erleichtern die [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] ändert dieses Standardverhalten für nicht überwachte Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="8f206-132">To make it easier for developers to write asynchronous code based on tasks, the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="8f206-133">Nicht überwachte Ausnahmen, die dazu führen, dass immer noch die <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> Ereignis ausgelöst wurde, wird standardmäßig der Prozess beendet jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="8f206-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="8f206-134">Stattdessen wird die Ausnahme ignoriert, nachdem das Ereignis ausgelöst wird, unabhängig davon, ob ein Ereignishandler für die Ausnahme berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="8f206-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="8f206-135">In der [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], können Sie die [ \<ThrowUnobservedTaskExceptions >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in einer Anwendungskonfigurationsdatei zu aktivieren die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Verhalten eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="8f206-135">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], you can use the [\<ThrowUnobservedTaskExceptions> element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in an application configuration file to enable the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="8f206-136">Sie können auch das Ausnahmeverhalten in einem der folgenden Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="8f206-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
-   <span data-ttu-id="8f206-137">Durch Festlegen der Umgebungsvariablen `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="8f206-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
-   <span data-ttu-id="8f206-138">Durch Festlegen der Registrierungs DWORD-Wert ThrowUnobservedTaskExceptions = 1 in der HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="8f206-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f206-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f206-139">Example</span></span>  
 <span data-ttu-id="8f206-140">Das folgende Beispiel veranschaulicht das Auslösen von Ausnahmen in Aufgaben, die mithilfe einer Anwendungskonfigurationsdatei zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f206-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="8f206-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f206-141">Example</span></span>  
 <span data-ttu-id="8f206-142">Im folgende Beispiel wird veranschaulicht, wie eine nicht überwachte Ausnahme aus einer Aufgabe ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="8f206-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="8f206-143">Der Code muss als freigegebene Programm einwandfrei ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8f206-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8f206-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f206-144">See Also</span></span>  
 [<span data-ttu-id="8f206-145">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="8f206-145">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="8f206-146">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="8f206-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
