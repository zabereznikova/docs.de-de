---
title: <clear>-Element für <listeners> für<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153580"
---
# <a name="clear-element-for-listeners-for-source"></a>\<clear>-Element für \<listeners> für\<source>
Löscht die `Listeners`-Sammlung für eine Ablaufverfolgungsquelle.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a>Syntax  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sources`|Enthält die Ablaufverfolgungsquellen, die die Ablaufverfolgungsmeldungen initiieren.|  
|`source`|Gibt eine Ablaufverfolgungsquelle an, die die Ablaufverfolgungsmeldungen initiiert.|  
|`listeners`|Gibt Listener an, die Nachrichten erfassen, speichern und weiterleiten.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `<clear>` Element entfernt alle Listener aus der-Auflistung `Listeners` für eine Ablauf Verfolgungs Quelle, einschließlich der <xref:System.Diagnostics.DefaultTraceListener> . Sie können das- `<clear>` Element verwenden, bevor Sie das- `<add>` Element verwenden, um sicher zu sein, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das `<clear>` -Element verwendet wird, bevor die `<add>` -Elemente zum Hinzufügen der Listener `console` und der-Auflistung `textListener` `Listeners` für die Ablauf Verfolgungs Quelle `TraceSourceApp` verwendet werden.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
- [Ablaufverfolgungslistener](../../../debug-trace-profile/trace-listeners.md)
