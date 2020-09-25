---
title: <add>-Element für <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: 5be39425363cb6d2a0eca6a0fa3f4154ce857bb5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173938"
---
# <a name="add-element-for-switches"></a>\<add>-Element für \<switches>

Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Syntax  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den Namen des Schalters an. Der Wert dieses Attributs entspricht dem *DisplayName* -Parameter, der an den Switch-Konstruktor übergeben wird.|  
|**value**|Erforderliches Attribut.<br /><br /> Gibt die Ebene des Schalters an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`switches`|Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
## <a name="remarks"></a>Bemerkungen  

 Sie können die Ebene eines Ablauf Verfolgungs Schalters ändern, indem Sie ihn in eine Konfigurationsdatei einfügen. Wenn der Schalter ein ist <xref:System.Diagnostics.BooleanSwitch> , können Sie ihn aktivieren und deaktivieren. Wenn der Schalter ein ist <xref:System.Diagnostics.TraceSwitch> , können Sie ihm verschiedene Ebenen zuweisen, um die Typen der Ablauf Verfolgungs-oder Debugmeldungen anzugeben, die die Anwendung ausgibt.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie das **\<add>** -Element verwendet wird, um den Ablauf `General` Verfolgungs Schalter auf die Ebene festzulegen <xref:System.Diagnostics.TraceLevel> und den `Data` booleschen Ablauf Verfolgungs Schalter zu aktivieren.  
  
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
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
