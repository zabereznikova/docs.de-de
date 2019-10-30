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
ms.openlocfilehash: 99eef6b8c264e21df7f4ecf9fc79dc607d484a0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115418"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="56601-102">\<throwunobservedtaskexceptions > Element</span><span class="sxs-lookup"><span data-stu-id="56601-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="56601-103">Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="56601-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
<span data-ttu-id="56601-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="56601-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="56601-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="56601-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="56601-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<throwunobservedtaskexceptions >**</span><span class="sxs-lookup"><span data-stu-id="56601-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56601-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="56601-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56601-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56601-108">Attributes and Elements</span></span>  
 <span data-ttu-id="56601-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56601-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56601-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="56601-110">Attributes</span></span>  
  
|<span data-ttu-id="56601-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="56601-111">Attribute</span></span>|<span data-ttu-id="56601-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56601-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="56601-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="56601-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="56601-114">Gibt an, ob der laufende Prozess durch nicht behandelte Aufgaben Ausnahmen beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="56601-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="56601-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="56601-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="56601-116">Wert</span><span class="sxs-lookup"><span data-stu-id="56601-116">Value</span></span>|<span data-ttu-id="56601-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56601-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="56601-118">Beendet den laufenden Prozess für eine nicht behandelte Task Ausnahme nicht.</span><span class="sxs-lookup"><span data-stu-id="56601-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="56601-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="56601-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="56601-120">Beendet den laufenden Prozess für eine nicht behandelte Task Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="56601-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56601-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56601-121">Child Elements</span></span>  
 <span data-ttu-id="56601-122">Keine</span><span class="sxs-lookup"><span data-stu-id="56601-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56601-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56601-123">Parent Elements</span></span>  
  
|<span data-ttu-id="56601-124">Element</span><span class="sxs-lookup"><span data-stu-id="56601-124">Element</span></span>|<span data-ttu-id="56601-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56601-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="56601-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="56601-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="56601-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="56601-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="56601-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56601-128">Remarks</span></span>  
 <span data-ttu-id="56601-129">Wenn eine Ausnahme, die einem <xref:System.Threading.Tasks.Task> zugeordnet ist, nicht beobachtet wurde, gibt es keinen <xref:System.Threading.Tasks.Task.Wait%2A> Vorgang, das übergeordnete Element ist nicht angefügt, und die <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType>-Eigenschaft wurde nicht gelesen. die Task Ausnahme wird als nicht beobachtet betrachtet.</span><span class="sxs-lookup"><span data-stu-id="56601-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="56601-130">Standardmäßig löst der Finalizer standardmäßig eine Ausnahme aus und beendet den Prozess, wenn eine <xref:System.Threading.Tasks.Task>, für die eine nicht beobachtete Ausnahme aufgetreten ist, standardmäßig in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="56601-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="56601-131">Die Beendigung des Prozesses wird durch die zeitliche Steuerung von Garbage Collection und Finalisierung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="56601-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="56601-132">Um Entwicklern das Schreiben von asynchronem Code auf Grundlage von Aufgaben zu vereinfachen, ändert der .NET Framework 4,5 dieses Standardverhalten für nicht beobachtete Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="56601-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="56601-133">Nicht überwachte Ausnahmen bewirken weiterhin, dass das <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>-Ereignis ausgelöst wird. der Prozess wird jedoch standardmäßig nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="56601-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="56601-134">Stattdessen wird die Ausnahme ignoriert, nachdem das-Ereignis ausgelöst wurde, unabhängig davon, ob ein Ereignishandler die Ausnahme beobachtet.</span><span class="sxs-lookup"><span data-stu-id="56601-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="56601-135">In der .NET Framework 4,5 können Sie das [\<throwunobservedtaskexceptions >-Element](throwunobservedtaskexceptions-element.md) in einer Anwendungs Konfigurationsdatei verwenden, um das .NET Framework 4-Verhalten beim Auslösen einer Ausnahme zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="56601-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="56601-136">Sie können das Ausnahme Verhalten auch auf eine der folgenden Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="56601-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="56601-137">Durch Festlegen der Umgebungsvariablen `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="56601-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="56601-138">Durch Festlegen des DWORD-Registrierungs Werts throwunobservedtaskexceptions = 1 im HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft-\\. NETFramework-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="56601-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56601-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56601-139">Example</span></span>  
 <span data-ttu-id="56601-140">Im folgenden Beispiel wird gezeigt, wie das Auslösen von Ausnahmen in Aufgaben mithilfe einer Anwendungs Konfigurationsdatei aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="56601-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="56601-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56601-141">Example</span></span>  
 <span data-ttu-id="56601-142">Im folgenden Beispiel wird veranschaulicht, wie eine nicht beobachtete Ausnahme von einem Task ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="56601-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="56601-143">Der Code muss als freigegebene Programm ausgeführt werden, damit er ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="56601-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="56601-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56601-144">See also</span></span>

- [<span data-ttu-id="56601-145">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="56601-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="56601-146">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="56601-146">Configuration File Schema</span></span>](../index.md)
