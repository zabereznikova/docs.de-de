---
title: <source>-Element
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 8860f5d3ed7ee0c04d1e8afd7614f3f73b470808
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673705"
---
# <a name="source-element"></a>\<Quelle >-Element
Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.  
  
 \<configuration>  
\<system.diagnostics>  
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
|`switchName`|Optionales Attribut.<br /><br /> Gibt den Namen einer Instanz der Trace-Schalter in der Anwendung an. Wenn der Schalter nicht, in erkannt wird einem `<switches>` -Element wird der Wert gibt die Ebene für den Switch.|  
|`switchType`|Optionales Attribut.<br /><br /> Gibt den Typ, der den Ablaufverfolgungsschalter. Falls vorhanden, wird der Typ muss ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.|  
|`extraAttribute`|Optionales Attribut.<br /><br /> Gibt den Wert für eine Ablaufverfolgung datenquellenspezifische Attributs, identifiziert durch den <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> Methode für die Ablaufverfolgungsquelle.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Enthält Listener, die sammeln, speichern und Weiterleiten von Nachrichten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der `<source>` Ablaufverfolgungsquelle hinzuzufügenden Elements `mySource` und legen Sie die Ebene für den Quellschalter namens `sourceSwitch`. Dass, die Ablaufverfolgungsinformationen in die Konsole schreibt, wird ein Konsolen-Ablaufverfolgungslistener hinzugefügt.  
  
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

- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [Ablaufverfolgungsschalter](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
