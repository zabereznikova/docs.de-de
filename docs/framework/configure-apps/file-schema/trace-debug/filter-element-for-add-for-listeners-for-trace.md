---
title: <filter>Element <add> für <listeners> für für<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153465"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>\<Filter> \<Element zum \<Hinzufügen \<von> für Listener> für Ablaufverfolgungs>
Fügt einem Listener in `Listeners` der Auflistung einen Filter für eine Ablaufverfolgung hinzu.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Spur>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Hörer>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<hinzufügen>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Filter>**

## <a name="syntax"></a>Syntax  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typ des Filters an, der <xref:System.Diagnostics.TraceFilter> von der Klasse erben soll. Sie können den Namespace-qualifizierten Namen des Typs verwenden, <xref:System.Type.FullName%2A> der der Eigenschaft des Typs entspricht, oder Sie können <xref:System.Type.AssemblyQualifiedName%2A> den vollqualifizierten Typnamen einschließlich der Assemblyinformationen verwenden, der der Eigenschaft entspricht. Informationen zu vollqualifizierten Typnamen finden Sie unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Filterklasse übergeben wurde.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
|`listeners`|Enthält Listener, die Nachrichten sammeln, speichern und weiterleiten. Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel weiter.|  
|`add`|Fügt einen Listener zu der `Listeners`-Sammlung hinzu.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `<filter>` Element muss in `<add>` einem Element für einen Ablaufverfolgungslistener enthalten sein, der den Typ des Listeners angibt, nicht nur den Namen eines Listeners, der in einem [ \<freigegebenen Listeners>](sharedlisteners-element.md)definiert ist. Wenn der Listener in einem [ \<freigegebenen Listeners>](sharedlisteners-element.md)definiert ist, muss der Filter für diesen Listener in diesem Element definiert werden.  
  
 Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, `<filter>` wie Sie das Element `console` verwenden, `Listeners` um dem Listener in der `Error`Auflistung für die Ablaufverfolgung einen Filter hinzuzufügen, und geben die Filterereignisebene als an.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
