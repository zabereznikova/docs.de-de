---
title: '&lt;Filter&gt; -Element für &lt;hinzufügen&gt; für &lt;SharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3bbba1c805c6b300f7cf7b3d9112cde9df7607a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a>&lt;Filter&gt; -Element für &lt;hinzufügen&gt; für &lt;SharedListeners&gt;
Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.  
  
 \<configuration>  
\<System.Diagnostics >  
\<SharedListeners >-Element  
\<add>  
\<Filter >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**Typ**|Erforderliches Attribut.<br /><br /> Gibt den Typ des Filters. Können Sie nur den vollständigen Namen des Typs (im Format der <xref:System.Type.FullName%2A?displayProperty=nameWithType> Eigenschaft), oder Sie können den vollqualifizierten Typnamen einschließlich der Assemblyinformationen (im Format der <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> Eigenschaft). Informationen zum Erstellen eines voll qualifizierten Typnamen finden Sie unter [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Optionales Attribut.<br /><br /> Die Zeichenfolge, die für die angegebene Klasse an den Konstruktor übergeben werden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sharedListeners`|Eine Auflistung von Listenern, die jeder Quelle oder das Trace-Element verweisen können.|  
|`add`|Fügt einen Listener, damit die **SharedListeners** Auflistung.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein Listener in definiert ist ein `<add>` Element von der `<sharedListeners>` Element, der Filter für diesen Listener definiert werden eine `<filter>` Element, das ein untergeordnetes Element des der `<add>` Element.  
  
 Dieses Element kann in der Computerkonfigurationsdatei ("Machine.config") und der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `<filter>` Element zum Hinzufügen eines Filters, der Ablaufverfolgungslistener `console` in der `sharedListeners` Auflistung.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.TraceFilter>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceSource>  
 [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
