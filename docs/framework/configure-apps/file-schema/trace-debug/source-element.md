---
title: '&lt;Quelle&gt; Element'
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b7c2a71b129a0ad7d1c2a72b18b8a69a111f9495
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsourcegt-element"></a>&lt;Quelle&gt; Element
Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.  
  
 \<configuration>  
\<System.Diagnostics >  
\<Quellen >  
\<Quelle >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`name`|Optionales Attribut.<br /><br /> Gibt den Namen der Ablaufverfolgungsquelle.|  
|`switchName`|Optionales Attribut.<br /><br /> Gibt den Namen der Instanz ein Trace-Schalter in der Anwendung an. Wenn der Schalter nicht, in identifiziert wurde einem `<switches>` Element, der Wert gibt die Ebene für den Switch.|  
|`switchType`|Optionales Attribut.<br /><br /> Gibt den Typ der Trace-Schalter. Falls vorhanden, wird der Typ muss ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.|  
|`extraAttribute`|Optionales Attribut.<br /><br /> Gibt den Wert für ein Trace-datenquellenspezifische-Attribut identifiziert, indem die <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> Methode für die Ablaufverfolgungsquelle.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Enthält die Listener, mit die sammeln, speichern und Weiterleiten von Nachrichten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `<source>` Elemente für die Ablaufverfolgungsquelle `mySource` und zum Festlegen der Ebene für den Quellschalter mit dem Namen `sourceSwitch`. Ein Konsolen-Ablaufverfolgungslistener hinzugefügt wird, die Ablaufverfolgungsinformationen in die Konsole schreibt.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Ablaufverfolgungsschalter](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
