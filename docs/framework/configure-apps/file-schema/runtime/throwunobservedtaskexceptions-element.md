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
ms.locfileid: "32749425"
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a>&lt;ThrowUnobservedTaskExceptions&gt; Element
Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.  
  
 \<configuration>  
\<Common Language Runtime >  
\<ThrowUnobservedTaskExceptions >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob der Task nicht behandelten Ausnahmen den ausgeführten Prozess beendet werden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Den ausgeführten Prozess für eine behandelte Ausnahme einer Aufgabe wird nicht beendet werden. Dies ist die Standardeinstellung.|  
|`true`|Beendet den ausgeführten Prozess für eine Aufgabe nicht behandelte Ausnahme.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
|||  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Ausnahme, die mit zugeordnetem eine <xref:System.Threading.Tasks.Task> nicht festgestellt wurde, besteht keine <xref:System.Threading.Tasks.Task.Wait%2A> Vorgang, der das übergeordnete Element ist nicht angefügt, und die <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> Eigenschaft wurde nicht gelesen, gilt die Ausnahme einer Aufgabe nicht beachtet werden.  
  
 In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], von Standard, falls ein <xref:System.Threading.Tasks.Task> , besitzt eine nicht überwachte Ausnahme ist die Garbage Collection, der Finalizer löst eine Ausnahme aus und beendet den Prozess. Die Beendigung des Prozesses wird durch die zeitliche Abfolge der Garbagecollection und Finalisierung bestimmt.  
  
 Für Entwickler zum Schreiben von asynchronem Code auf Grundlage der Aufgaben, erleichtern die [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] ändert dieses Standardverhalten für nicht überwachte Ausnahmen. Nicht überwachte Ausnahmen, die dazu führen, dass immer noch die <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> Ereignis ausgelöst wurde, wird standardmäßig der Prozess beendet jedoch nicht. Stattdessen wird die Ausnahme ignoriert, nachdem das Ereignis ausgelöst wird, unabhängig davon, ob ein Ereignishandler für die Ausnahme berücksichtigt.  
  
 In der [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], können Sie die [ \<ThrowUnobservedTaskExceptions >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in einer Anwendungskonfigurationsdatei zu aktivieren die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Verhalten eine Ausnahme auszulösen.  
  
 Sie können auch das Ausnahmeverhalten in einem der folgenden Arten angeben:  
  
-   Durch Festlegen der Umgebungsvariablen `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
-   Durch Festlegen der Registrierungs DWORD-Wert ThrowUnobservedTaskExceptions = 1 in der HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework Schlüssel.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Auslösen von Ausnahmen in Aufgaben, die mithilfe einer Anwendungskonfigurationsdatei zu aktivieren.  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie eine nicht überwachte Ausnahme aus einer Aufgabe ausgelöst wird. Der Code muss als freigegebene Programm einwandfrei ausgeführt werden.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
