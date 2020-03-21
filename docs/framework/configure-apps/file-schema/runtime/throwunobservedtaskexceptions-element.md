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
ms.openlocfilehash: de5a686bcbd88fc52173b488103f033575623d62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153814"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="c99c7-102">\<ThrowUnobservedTaskExceptions> Element</span><span class="sxs-lookup"><span data-stu-id="c99c7-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="c99c7-103">Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c99c7-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
<span data-ttu-id="c99c7-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c99c7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c99c7-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="c99c7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c99c7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span><span class="sxs-lookup"><span data-stu-id="c99c7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c99c7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c99c7-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c99c7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c99c7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c99c7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c99c7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c99c7-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="c99c7-110">Attributes</span></span>  
  
|<span data-ttu-id="c99c7-111">attribute</span><span class="sxs-lookup"><span data-stu-id="c99c7-111">Attribute</span></span>|<span data-ttu-id="c99c7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c99c7-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c99c7-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c99c7-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c99c7-114">Gibt an, ob nicht behandelte Taskausnahmen den laufenden Prozess beenden sollen.</span><span class="sxs-lookup"><span data-stu-id="c99c7-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c99c7-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="c99c7-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c99c7-116">value</span><span class="sxs-lookup"><span data-stu-id="c99c7-116">Value</span></span>|<span data-ttu-id="c99c7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c99c7-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c99c7-118">Beendet den laufenden Prozess für eine nicht behandelte Taskausnahme nicht.</span><span class="sxs-lookup"><span data-stu-id="c99c7-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="c99c7-119">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="c99c7-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c99c7-120">Beendet den laufenden Prozess für eine nicht behandelte Taskausnahme.</span><span class="sxs-lookup"><span data-stu-id="c99c7-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c99c7-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c99c7-121">Child Elements</span></span>  
 <span data-ttu-id="c99c7-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="c99c7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c99c7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c99c7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c99c7-124">Element</span><span class="sxs-lookup"><span data-stu-id="c99c7-124">Element</span></span>|<span data-ttu-id="c99c7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c99c7-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c99c7-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c99c7-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c99c7-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="c99c7-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="c99c7-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c99c7-128">Remarks</span></span>  
 <span data-ttu-id="c99c7-129">Wenn eine Ausnahme, die <xref:System.Threading.Tasks.Task> einem zugeordnet ist, <xref:System.Threading.Tasks.Task.Wait%2A> nicht beobachtet wurde, gibt es <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> keinen Vorgang, das übergeordnete Element ist nicht angefügt, und die Eigenschaft wurde nicht gelesen, die Aufgabenausnahme wird als nicht beobachtet betrachtet.</span><span class="sxs-lookup"><span data-stu-id="c99c7-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="c99c7-130">Wenn in .NET Framework 4 standardmäßig <xref:System.Threading.Tasks.Task> eine, die eine unbeobachtete Ausnahme enthält, Garbage Collection ist, löst der Finalizer standardmäßig eine Ausnahme aus und beendet den Prozess.</span><span class="sxs-lookup"><span data-stu-id="c99c7-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="c99c7-131">Die Beendigung des Prozesses wird durch den Zeitpunkt der Garbage Collection und Finalisierung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="c99c7-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="c99c7-132">Um Entwicklern das Schreiben von asynchronem Code basierend auf Aufgaben zu erleichtern, ändert .NET Framework 4.5 dieses Standardverhalten für nicht beobachtete Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="c99c7-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="c99c7-133">Unbeobachtete Ausnahmen führen <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> weiterhin dazu, dass das Ereignis ausgelöst wird, aber standardmäßig wird der Prozess nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="c99c7-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="c99c7-134">Stattdessen wird die Ausnahme ignoriert, nachdem das Ereignis ausgelöst wurde, unabhängig davon, ob ein Ereignishandler die Ausnahme beachtet.</span><span class="sxs-lookup"><span data-stu-id="c99c7-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="c99c7-135">In .NET Framework 4.5 können Sie das [ \<>-Element throwUnobservedTaskExceptions](throwunobservedtaskexceptions-element.md) in einer Anwendungskonfigurationsdatei verwenden, um das .NET Framework 4-Verhalten beim Auslösen einer Ausnahme zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c99c7-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="c99c7-136">Sie können das Ausnahmeverhalten auch auf eine der folgenden Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="c99c7-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="c99c7-137">Durch Festlegen der `COMPlus_ThrowUnobservedTaskExceptions` `set COMPlus_ThrowUnobservedTaskExceptions=1`Umgebungsvariablen ( ).</span><span class="sxs-lookup"><span data-stu-id="c99c7-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="c99c7-138">Durch Festlegen des Registrierungs-DWORD-Werts throwUnobservedTaskExceptions =\\1 in der HKEY_LOCAL_MACHINE-SOFTWARE-Microsoft . NETFramework-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c99c7-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c99c7-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c99c7-139">Example</span></span>  
 <span data-ttu-id="c99c7-140">Das folgende Beispiel zeigt, wie Sie das Auslösen von Ausnahmen in Aufgaben mithilfe einer Anwendungskonfigurationsdatei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c99c7-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="c99c7-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c99c7-141">Example</span></span>  
 <span data-ttu-id="c99c7-142">Das folgende Beispiel veranschaulicht, wie eine unbeobachtete Ausnahme von einer Aufgabe ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c99c7-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="c99c7-143">Der Code muss als freigegebenes Programm ausgeführt werden, damit es ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c99c7-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c99c7-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c99c7-144">See also</span></span>

- [<span data-ttu-id="c99c7-145">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c99c7-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c99c7-146">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="c99c7-146">Configuration File Schema</span></span>](../index.md)
