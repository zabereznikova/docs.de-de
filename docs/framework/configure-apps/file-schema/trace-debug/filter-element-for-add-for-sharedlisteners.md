---
title: <filter>Element <add> für für<sharedListeners>
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
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153452"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<Filtern> \<Elements für \<hinzufügen> für freigegebene Listen->
Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<hinzufügen>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Filter>**

## <a name="syntax"></a>Syntax  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|**Typ**|Erforderliches Attribut.<br /><br /> Gibt den Typ des Filters an. Sie können nur den vollständigen Namen des Typs <xref:System.Type.FullName%2A?displayProperty=nameWithType> (im Format der Eigenschaft) oder den vollqualifizierten Typnamen <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> einschließlich der Assemblyinformationen (im Format der Eigenschaft) verwenden. Informationen zum Erstellen eines vollqualifizierten Typnamens finden Sie unter [Angeben von vollqualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**Initializedata**|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wurde.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sharedListeners`|Eine Auflistung von Listenern, auf die jedes Quell- oder Ablaufverfolgungselement verweisen kann.|  
|`add`|Fügt der **sharedListeners-Auflistung** einen Listener hinzu.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn ein Listener in `<add>` einem `<sharedListeners>` Element des Elements definiert ist, sollte `<filter>` der Filter für diesen `<add>` Listener in einem Element definiert werden, das ein untergeordnetes Element des Elements ist.  
  
 Dieses Element kann in der Maschinenkonfigurationsdatei (Machine.config) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, `<filter>` wie Sie das Element verwenden, um dem Ablaufverfolgungslistener `console` in der `sharedListeners` Auflistung einen Filter hinzuzufügen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
