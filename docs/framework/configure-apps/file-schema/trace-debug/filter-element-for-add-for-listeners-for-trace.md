---
title: <filter> Element für <add> für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: cc970240ac07ad3ea72be50d1e9af452da638fa9
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088892"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>\<> Element filtern, \<um > für \<Listener > für \<Ablauf Verfolgung hinzuzufügen >
Fügt einen Filter zu einem Listener in der `Listeners`-Auflistung für eine Ablauf Verfolgung hinzu.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Ablauf Verfolgungs**](trace-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<Listener >\** ](listeners-element-for-trace.md)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> hinzufügen**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Filter >**

## <a name="syntax"></a>Syntax  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`type`|Erforderliches Attribut.<br /><br /> Gibt den Typ des Filters an, der von der <xref:System.Diagnostics.TraceFilter> Klasse erben soll. Sie können den mit dem Namespace qualifizierten Namen des Typs verwenden, der der <xref:System.Type.FullName%2A>-Eigenschaft des Typs entspricht, oder Sie können den voll qualifizierten Typnamen einschließlich der Assemblyinformationen verwenden, die der <xref:System.Type.AssemblyQualifiedName%2A>-Eigenschaft entsprechen. Informationen zu voll qualifizierten Typnamen finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Filterklasse übergeben wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
|`listeners`|Enthält Listener, die Nachrichten erfassen, speichern und weiterleiten. Listener leiten die Ablauf Verfolgungs Ausgabe an ein entsprechendes Ziel weiter.|  
|`add`|Fügt einen Listener zu der `Listeners`-Sammlung hinzu.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<filter>`-Element muss in einem `<add>`-Element für einen Ablaufverfolgungslistener enthalten sein, der den Typ des Listener angibt, nicht nur den Namen eines Listener, der in einem [\<sharedlistener->](sharedlisteners-element.md)definiert ist. Wenn der Listener in einem [\<sharedlistener->](sharedlisteners-element.md)definiert ist, muss der Filter für diesen Listener in diesem Element definiert werden.  
  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine. config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das `<filter>`-Element verwendet wird, um dem Listener `console` in der `Listeners`-Auflistung für die Ablauf Verfolgung einen Filter hinzuzufügen, wobei die Filter Ereignis Ebene als `Error`angegeben wird.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
