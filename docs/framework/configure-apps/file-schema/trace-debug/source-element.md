---
title: <source>-Element
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153294"
---
# <a name="source-element"></a>\<Quelle> Element
Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Quellen>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Quelle>**

## <a name="syntax"></a>Syntax  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`name`|Optionales Attribut.<br /><br /> Gibt den Namen der Ablaufverfolgungsquelle an.|  
|`switchName`|Optionales Attribut.<br /><br /> Gibt den Namen einer Ablaufverfolgungsschalterinstanz in der Anwendung an. Wenn der Schalter nicht `<switches>` in einem Element identifiziert wird, gibt der Wert die Ebene für den Switch an.|  
|`switchType`|Optionales Attribut.<br /><br /> Gibt den Typ des Ablaufverfolgungsschalters an. Wenn vorhanden, muss der Typ ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.|  
|`extraAttribute`|Optionales Attribut.<br /><br /> Gibt den Wert für ein Trace-Source-spezifisches Attribut an, das von der <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> Methode für diese Ablaufverfolgungsquelle identifiziert wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Hörer>](listeners-element-for-source.md)|Enthält Listener, die Nachrichten sammeln, speichern und weiterleiten.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
  
## <a name="remarks"></a>Bemerkungen  
 Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, `<source>` wie sie das `mySource` Element verwenden, um die `sourceSwitch`Ablaufverfolgungsquelle hinzuzufügen und die Ebene für den Quellschalter mit dem Namen festzulegen. Ein Konsolenablaufverfolgungslistener wird hinzugefügt, der Ablaufverfolgungsinformationen in die Konsole schreibt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
- [Ablaufverfolgungsschalter](../../../debug-trace-profile/trace-switches.md)
