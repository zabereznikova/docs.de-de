---
title: "&lt;Hinzufügen&gt; -Element für &lt;Switches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: de1acb37f3236598e9d8a74a188033d18b65ac8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-ltswitchesgt"></a>&lt;Hinzufügen&gt; -Element für &lt;Switches&gt;
Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.  
  
 \<configuration>  
\<System.Diagnostics >  
\<Switches >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den Namen des Schalters. Der Wert dieses Attributs entspricht dem *DisplayName* Parameter, der übergeben wird, um den Konstruktor zu wechseln.|  
|**value**|Erforderliches Attribut.<br /><br /> Gibt die Ebene des Schalters.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`switches`|Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können das Maß an einen Ablaufverfolgungsschalter ändern, indem Sie diese in einer Konfigurationsdatei zur Verfügung stellen. Wenn der Schalter ist eine <xref:System.Diagnostics.BooleanSwitch>, Sie können Sie aktivieren und deaktivieren. Wenn der Schalter ist eine <xref:System.Diagnostics.TraceSwitch>, können Sie verschiedene Ebenen hinzu, um die Typen von Ablaufverfolgung angeben zuweisen oder Debug Nachrichten, die Ausgaben der Anwendung.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die  **\<hinzufügen >** festzulegenden Elements der `General` Trace-Schalter, um die <xref:System.Diagnostics.TraceLevel> Ebene, und aktivieren Sie die `Data` booleschen Ablaufverfolgungsschalter.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
