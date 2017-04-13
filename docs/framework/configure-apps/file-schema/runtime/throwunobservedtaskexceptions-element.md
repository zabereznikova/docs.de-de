---
title: "&lt;ThrowUnobservedTaskExceptions&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<ThrowUnobservedTaskExceptions>-Element"
  - "ThrowUnobservedTaskExceptions-Element"
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# &lt;ThrowUnobservedTaskExceptions&gt;-Element
Gibt an, ob nicht behandelte Aufgabenausnahmen einen laufenden Prozess beenden sollten.  
  
## Syntax  
  
```vb  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob nicht behandelte Aufgabenausnahmen den laufenden Prozess beenden sollten.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Beendet nicht den aktuellen Prozess für eine nicht behandelte Aufgabenausnahme.  Dies ist der Standardwert.|  
|`true`|Beendet den aktuellen Vorgang für eine nicht behandelte Aufgabenausnahme.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
|||  
  
## Hinweise  
 Wenn auf eine Ausnahme, die <xref:System.Threading.Tasks.Task> zugeordnet ist, nicht überwacht wurde, ist kein <xref:System.Threading.Tasks.Task.Wait%2A> Vorgang, ist das übergeordnete Element nicht angefügt, und die <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=fullName>\-Eigenschaft wurde nicht die Aufgabenausnahme betrachtet wird als unbeobachtet gelesen.  
  
 In [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] standardmäßig beim <xref:System.Threading.Tasks.Task>, die eine nicht überwachte Ausnahme hat, der eine Garbage Collection durchgeführt wurde, wird der Finalizer eine Ausnahme aus und beendet den Prozess.  Die Beendigung des Prozesses wird durch die Zeitplanung der Garbage Collection und des Abschlusses bestimmt.  
  
 Um sie zu vereinfachen ändert damit Entwickler asynchronen Code auf Grundlage Aufgaben, [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] für dieses Standardverhalten nicht überwachte Ausnahmen schreiben.  Nicht überwachte Ausnahmen führen noch das <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>\-Ereignis ausgelöst wird, jedoch standardmäßig, endet der Prozess nicht.  Stattdessen wird die Ausnahme ignoriert, nachdem das Ereignis ausgelöst wird, unabhängig davon, ob ein Ereignishandler auf die Ausnahme achtet.  
  
 In [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] können Sie [\<ThrowUnobservedTaskExceptions\>\-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in einer Anwendungskonfigurationsdatei können, um das [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Verhalten zum Aufrufen eine Ausnahme zu aktivieren.  
  
 Sie können das Ausnahmeverhalten in einer der folgenden Methoden auch angeben:  
  
-   Durch Festlegen der Umgebungsvariable `COMPlus_ThrowUnobservedTaskExceptions` \(`set COMPlus_ThrowUnobservedTaskExceptions=1`\).  
  
-   Durch Festlegen des DWORD\-Werts Registrierung ThrowUnobservedTaskExceptions \= 1 der HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework Schlüssel.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie das Auslösen von Ausnahmen in Aufgaben mithilfe einer Anwendungskonfigurationsdatei kann.  
  
```  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
  
```  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine nicht überwachte Ausnahme von einer Aufgabe ausgelöst wird.  Der Code muss als freigegebenes Programm ausgeführt werden, um ordnungsgemäß zu arbeiten.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)