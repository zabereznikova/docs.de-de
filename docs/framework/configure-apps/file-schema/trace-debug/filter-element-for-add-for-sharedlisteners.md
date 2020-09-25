---
title: <filter> -Element für <add> für <sharedListeners>
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
ms.openlocfilehash: e140148a342e31d6ade7def8849d8a7738301704
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173925"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<filter> -Element für \<add> für \<sharedListeners>

Fügt einen Filter zu einem Listener in der `sharedListeners`-Sammlung hinzu.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a>Syntax  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|**type**|Erforderliches Attribut.<br /><br /> Gibt den Filtertyp an. Sie können nur den vollständigen Namen des Typs (im Format der- <xref:System.Type.FullName%2A?displayProperty=nameWithType> Eigenschaft) verwenden, oder Sie können den voll qualifizierten Typnamen verwenden, einschließlich der Assemblyinformationen (im Format der- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> Eigenschaft). Weitere Informationen zum Erstellen eines voll qualifizierten Typnamens finden Sie unter [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Optionales Attribut.<br /><br /> Die Zeichenfolge, die an den Konstruktor für die angegebene Klasse übergeben wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`sharedListeners`|Eine Auflistung von Listenern, auf die beliebige Quell-oder Ablauf Verfolgungs Elemente verweisen können.|  
|`add`|Fügt der **sharedlistener** -Auflistung einen Listener hinzu.|  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn ein Listener in einem `<add>` Element des-Elements definiert ist `<sharedListeners>` , sollte der Filter für diesen Listener in einem-Element definiert werden `<filter>` , das ein untergeordnetes Element des- `<add>` Elements ist.  
  
 Dieses Element kann in der Computer Konfigurationsdatei (Machine.config) und in der Anwendungs Konfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt, wie das-Element verwendet wird, um dem Ablaufverfolgungslistener `<filter>` in der-Auflistung einen Filter hinzuzufügen `console` `sharedListeners`  
  
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
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
