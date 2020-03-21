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
# <a name="throwunobservedtaskexceptions-element"></a>\<ThrowUnobservedTaskExceptions> Element
Gibt an, ob ein laufender Prozess durch Aufgabenausnahmefehler beendet werden soll.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob nicht behandelte Taskausnahmen den laufenden Prozess beenden sollen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|Beendet den laufenden Prozess für eine nicht behandelte Taskausnahme nicht. Dies ist die Standardoption.|  
|`true`|Beendet den laufenden Prozess für eine nicht behandelte Taskausnahme.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
|||  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn eine Ausnahme, die <xref:System.Threading.Tasks.Task> einem zugeordnet ist, <xref:System.Threading.Tasks.Task.Wait%2A> nicht beobachtet wurde, gibt es <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> keinen Vorgang, das übergeordnete Element ist nicht angefügt, und die Eigenschaft wurde nicht gelesen, die Aufgabenausnahme wird als nicht beobachtet betrachtet.  
  
 Wenn in .NET Framework 4 standardmäßig <xref:System.Threading.Tasks.Task> eine, die eine unbeobachtete Ausnahme enthält, Garbage Collection ist, löst der Finalizer standardmäßig eine Ausnahme aus und beendet den Prozess. Die Beendigung des Prozesses wird durch den Zeitpunkt der Garbage Collection und Finalisierung bestimmt.  
  
 Um Entwicklern das Schreiben von asynchronem Code basierend auf Aufgaben zu erleichtern, ändert .NET Framework 4.5 dieses Standardverhalten für nicht beobachtete Ausnahmen. Unbeobachtete Ausnahmen führen <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> weiterhin dazu, dass das Ereignis ausgelöst wird, aber standardmäßig wird der Prozess nicht beendet. Stattdessen wird die Ausnahme ignoriert, nachdem das Ereignis ausgelöst wurde, unabhängig davon, ob ein Ereignishandler die Ausnahme beachtet.  
  
 In .NET Framework 4.5 können Sie das [ \<>-Element throwUnobservedTaskExceptions](throwunobservedtaskexceptions-element.md) in einer Anwendungskonfigurationsdatei verwenden, um das .NET Framework 4-Verhalten beim Auslösen einer Ausnahme zu aktivieren.  
  
 Sie können das Ausnahmeverhalten auch auf eine der folgenden Arten angeben:  
  
- Durch Festlegen der `COMPlus_ThrowUnobservedTaskExceptions` `set COMPlus_ThrowUnobservedTaskExceptions=1`Umgebungsvariablen ( ).  
  
- Durch Festlegen des Registrierungs-DWORD-Werts throwUnobservedTaskExceptions =\\1 in der HKEY_LOCAL_MACHINE-SOFTWARE-Microsoft . NETFramework-Schlüssel.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie das Auslösen von Ausnahmen in Aufgaben mithilfe einer Anwendungskonfigurationsdatei aktivieren.  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, wie eine unbeobachtete Ausnahme von einer Aufgabe ausgelöst wird. Der Code muss als freigegebenes Programm ausgeführt werden, damit es ordnungsgemäß funktioniert.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
