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
ms.openlocfilehash: 012c2e70e66015bc317606a7eea07812b5df26e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183922"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="2891a-102">\<ThrowUnobservedTaskExceptions>-Element</span><span class="sxs-lookup"><span data-stu-id="2891a-102">\<ThrowUnobservedTaskExceptions> Element</span></span>

<span data-ttu-id="2891a-103">Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2891a-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a><span data-ttu-id="2891a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2891a-104">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2891a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2891a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2891a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2891a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2891a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="2891a-107">Attributes</span></span>  
  
|<span data-ttu-id="2891a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="2891a-108">Attribute</span></span>|<span data-ttu-id="2891a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2891a-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2891a-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2891a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="2891a-111">Gibt an, ob der laufende Prozess durch nicht behandelte Aufgaben Ausnahmen beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2891a-111">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2891a-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="2891a-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="2891a-113">Wert</span><span class="sxs-lookup"><span data-stu-id="2891a-113">Value</span></span>|<span data-ttu-id="2891a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2891a-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2891a-115">Beendet den laufenden Prozess für eine nicht behandelte Task Ausnahme nicht.</span><span class="sxs-lookup"><span data-stu-id="2891a-115">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="2891a-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="2891a-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2891a-117">Beendet den laufenden Prozess für eine nicht behandelte Task Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="2891a-117">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2891a-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2891a-118">Child Elements</span></span>  

 <span data-ttu-id="2891a-119">Keine</span><span class="sxs-lookup"><span data-stu-id="2891a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2891a-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2891a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2891a-121">Element</span><span class="sxs-lookup"><span data-stu-id="2891a-121">Element</span></span>|<span data-ttu-id="2891a-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2891a-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2891a-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2891a-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2891a-124">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="2891a-124">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="2891a-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2891a-125">Remarks</span></span>  

 <span data-ttu-id="2891a-126">Wenn eine Ausnahme, die einem zugeordnet ist <xref:System.Threading.Tasks.Task> , nicht beobachtet wurde, gibt es keinen <xref:System.Threading.Tasks.Task.Wait%2A> Vorgang, das übergeordnete Element ist nicht angefügt, und die <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> Eigenschaft wurde nicht gelesen. die Task Ausnahme wird als nicht beobachtet betrachtet.</span><span class="sxs-lookup"><span data-stu-id="2891a-126">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="2891a-127">Standardmäßig löst der Finalizer standardmäßig eine Ausnahme aus und beendet den Prozess, wenn in der .NET Framework 4 eine Garbage Collection mit einer <xref:System.Threading.Tasks.Task> nicht beobachteten Ausnahme erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2891a-127">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="2891a-128">Die Beendigung des Prozesses wird durch die zeitliche Steuerung von Garbage Collection und Finalisierung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="2891a-128">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="2891a-129">Um Entwicklern das Schreiben von asynchronem Code auf Grundlage von Aufgaben zu vereinfachen, ändert der .NET Framework 4,5 dieses Standardverhalten für nicht beobachtete Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="2891a-129">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="2891a-130">Nicht beobachtete Ausnahmen bewirken weiterhin <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> , dass das Ereignis ausgelöst wird. der Prozess wird jedoch standardmäßig nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="2891a-130">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="2891a-131">Stattdessen wird die Ausnahme ignoriert, nachdem das-Ereignis ausgelöst wurde, unabhängig davon, ob ein Ereignishandler die Ausnahme beobachtet.</span><span class="sxs-lookup"><span data-stu-id="2891a-131">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="2891a-132">Im .NET Framework 4,5 können Sie das- [ \<ThrowUnobservedTaskExceptions> Element](throwunobservedtaskexceptions-element.md) in einer Anwendungs Konfigurationsdatei verwenden, um das .NET Framework 4-Verhalten beim Auslösen einer Ausnahme zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2891a-132">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="2891a-133">Sie können das Ausnahme Verhalten auch auf eine der folgenden Arten angeben:</span><span class="sxs-lookup"><span data-stu-id="2891a-133">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="2891a-134">Durch Festlegen der Umgebungsvariablen `COMPlus_ThrowUnobservedTaskExceptions` ( `set COMPlus_ThrowUnobservedTaskExceptions=1` ).</span><span class="sxs-lookup"><span data-stu-id="2891a-134">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="2891a-135">Durch Festlegen des DWORD-Registrierungs Werts throwunobservedtaskexceptions = 1 im HKEY_LOCAL_MACHINE \Software\Microsoft \\ . NETFramework-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="2891a-135">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2891a-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2891a-136">Example</span></span>  

 <span data-ttu-id="2891a-137">Im folgenden Beispiel wird gezeigt, wie das Auslösen von Ausnahmen in Aufgaben mithilfe einer Anwendungs Konfigurationsdatei aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="2891a-137">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="2891a-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2891a-138">Example</span></span>  

 <span data-ttu-id="2891a-139">Im folgenden Beispiel wird veranschaulicht, wie eine nicht beobachtete Ausnahme von einem Task ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="2891a-139">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="2891a-140">Der Code muss als freigegebene Programm ausgeführt werden, damit er ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2891a-140">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2891a-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2891a-141">See also</span></span>

- [<span data-ttu-id="2891a-142">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="2891a-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2891a-143">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2891a-143">Configuration File Schema</span></span>](../index.md)
