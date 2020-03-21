---
title: <switches>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153229"
---
# <a name="switches-element"></a>\<Schalter> Element
Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.  

[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Switches>**

## <a name="syntax"></a>Syntax  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<hinzufügen>](add-element-for-switches.md)|Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`System.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
## <a name="remarks"></a>Bemerkungen  
 Sie können die Ebene eines Ablaufverfolgungsschalters ändern, indem Sie ihn in eine Konfigurationsdatei einteilen. Wenn es sich <xref:System.Diagnostics.BooleanSwitch>bei dem Schalter um einen handelt, können Sie ihn ein- und ausschalten. Wenn es sich <xref:System.Diagnostics.TraceSwitch>bei dem Switch um einen handelt, können Sie ihm verschiedene Ebenen zuweisen, um die Typen von Ablaufverfolgungs- oder Debugmeldungen anzugeben, die die Anwendung ausgibt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie den `General` <xref:System.Diagnostics.TraceLevel> ** \<Switch>-Element** verwenden, `Data` um den Ablaufverfolgungsschalter auf die Ebene zu setzen, und den booleschen Ablaufverfolgungsschalter aktivieren.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [Ablaufverfolgungs- und Debugeinstellungsschema](index.md)
