---
title: <ThrowUnobservedTaskExceptions>-Element
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
ms.openlocfilehash: cb6cfc8e1c3f0409d99d31efa0a645476b47e45e
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456255"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="1b971-102">\<ThrowUnobservedTaskExceptions> Element</span><span class="sxs-lookup"><span data-stu-id="1b971-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="1b971-103">Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b971-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="1b971-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1b971-104">\<configuration></span></span>  
<span data-ttu-id="1b971-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="1b971-105">\<runtime></span></span>  
<span data-ttu-id="1b971-106">\<ThrowUnobservedTaskExceptions></span><span class="sxs-lookup"><span data-stu-id="1b971-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b971-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b971-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b971-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1b971-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1b971-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1b971-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b971-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="1b971-110">Attributes</span></span>  
  
|<span data-ttu-id="1b971-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="1b971-111">Attribute</span></span>|<span data-ttu-id="1b971-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b971-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1b971-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="1b971-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1b971-114">Gibt an, ob den ausgeführten Prozess nicht behandelte aufgabenausnahmen beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b971-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1b971-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="1b971-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1b971-116">Wert</span><span class="sxs-lookup"><span data-stu-id="1b971-116">Value</span></span>|<span data-ttu-id="1b971-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b971-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1b971-118">Den ausgeführten Prozess für eine nicht behandelte aufgabenausnahme wird nicht beendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b971-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="1b971-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1b971-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1b971-120">Beendet den ausgeführten Prozess für eine nicht behandelte Task-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="1b971-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b971-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b971-121">Child Elements</span></span>  
 <span data-ttu-id="1b971-122">Keine</span><span class="sxs-lookup"><span data-stu-id="1b971-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b971-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b971-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1b971-124">Element</span><span class="sxs-lookup"><span data-stu-id="1b971-124">Element</span></span>|<span data-ttu-id="1b971-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b971-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1b971-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1b971-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1b971-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="1b971-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="1b971-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b971-128">Remarks</span></span>  
 <span data-ttu-id="1b971-129">Wenn eine Ausnahme, die zugeordnet ist eine <xref:System.Threading.Tasks.Task> nicht festgestellt wurde, gibt es keine <xref:System.Threading.Tasks.Task.Wait%2A> Vorgang, der das übergeordnete Element ist nicht angefügt, und die <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> Eigenschaft wurde nicht gelesen, die aufgabenausnahme gilt als nicht überwachte.</span><span class="sxs-lookup"><span data-stu-id="1b971-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="1b971-130">In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], Standard, falls ein <xref:System.Threading.Tasks.Task> , bei dem eine nicht überwachte Ausnahme ist die Garbage Collection, der Finalizer löst eine Ausnahme aus und beendet den Prozess.</span><span class="sxs-lookup"><span data-stu-id="1b971-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="1b971-131">Die Beendigung des Prozesses wird durch die zeitplanung für die Garbagecollection und Finalization bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1b971-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="1b971-132">Um Entwicklern das Schreiben von asynchronen Codes basierend auf Aufgaben zu vereinfachen, ändert sich die .NET Framework 4.5 dieses Standardverhalten für nicht überwachte Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="1b971-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="1b971-133">Nicht überwachte Ausnahmen, die noch dazu führen, dass die <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> Ereignis ausgelöst wird, wird standardmäßig der Prozess beendet jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="1b971-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="1b971-134">Stattdessen wird die Ausnahme ignoriert, nachdem das Ereignis ausgelöst wird, unabhängig davon, ob ein Ereignishandler für die Ausnahme beobachtet.</span><span class="sxs-lookup"><span data-stu-id="1b971-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="1b971-135">In .NET Framework 4.5, können Sie mithilfe der [ \<ThrowUnobservedTaskExceptions >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in einer Anwendungskonfigurationsdatei So aktivieren Sie das .NET Framework 4 Verhalten optional eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1b971-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="1b971-136">Sie können auch das Verhalten in einem der folgenden Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="1b971-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="1b971-137">Durch Festlegen der Umgebungsvariablen `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="1b971-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="1b971-138">Durch Festlegen der Registrierung mit einem DWORD-Wert ThrowUnobservedTaskExceptions = 1 in der HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="1b971-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b971-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b971-139">Example</span></span>  
 <span data-ttu-id="1b971-140">Das folgende Beispiel zeigt, wie Sie das Auslösen von Ausnahmen in Aufgaben, die mithilfe einer Anwendungskonfigurationsdatei zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1b971-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="1b971-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b971-141">Example</span></span>  
 <span data-ttu-id="1b971-142">Im folgende Beispiel wird veranschaulicht, wie eine nicht überwachte Ausnahme aus einem Task ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="1b971-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="1b971-143">Der Code muss als veröffentlichte Programm ordnungsgemäß funktioniert, ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1b971-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1b971-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b971-144">See also</span></span>

- [<span data-ttu-id="1b971-145">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="1b971-145">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1b971-146">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="1b971-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
