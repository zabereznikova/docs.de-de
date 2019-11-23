---
title: < System. Diagnostics >-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: dc05c46cb1ba74baceaaeadc2959a6889faf19c9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699192"
---
# <a name="systemdiagnostics-element"></a>\<System. Diagnostics >-Element
Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<System. Diagnostics >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 None.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.|  
|[\<performanceCounters>](performancecounters-element.md)|Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.|  
|[\<sharedListeners>](sharedlisteners-element.md)|Enthält Listener, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann. Listener, die als freigegebene Listener identifiziert werden, können Quellen oder Ablauf Verfolgungen anhand des Namens hinzugefügt werden.|  
|[\<sources>](sources-element.md)|Gibt Ablauf Verfolgungs Quellen an, die Ablauf Verfolgungs Meldungen initiieren.|  
|[\<switches>](switches-element.md)|Enthält Ablauf Verfolgungs Schalter und die Ebenen, auf denen die Ablauf Verfolgungs Schalter festgelegt sind.|  
|[\<trace>](trace-element.md)|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Ablauf Verfolgungs Schalter und ein Ablaufverfolgungslistener in das **\<System. Diagnostics->** Element eingebettet werden. Der Schalter für die `General` Ablauf Verfolgung ist auf <xref:System.Diagnostics.TraceLevel> Ebene festgelegt. Der Ablaufverfolgungslistener `myListener` erstellt eine Datei mit dem Namen `MyListener.log` und schreibt die Ausgabe in die Datei.  
  
> [!NOTE]
> In .NET Framework 2.0 können Sie Text verwenden, um den Wert eines Schalters anzugeben. Sie können z. b. `true` für eine <xref:System.Diagnostics.BooleanSwitch> angeben oder den Text verwenden, der einen Enumerationswert darstellt, z. b. `Error` für einen <xref:System.Diagnostics.TraceSwitch>. Die Zeile `<add name="myTraceSwitch" value="Error" />` ist gleichbedeutend mit `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
