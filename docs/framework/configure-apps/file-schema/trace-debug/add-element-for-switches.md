---
title: <add>-Element für <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: db2de681227dfdb7420808963219b9f52381f8fe
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088960"
---
# <a name="add-element-for-switches"></a>\<> Element für \<Switches hinzufügen >
Gibt die Ebene an, für die ein Ablaufverfolgungsschalter festgelegt ist.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Switches**](switches-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Hinzufügen >**

## <a name="syntax"></a>Syntax  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**name**|Erforderliches Attribut.<br /><br /> Gibt den Namen des Schalters an. Der Wert dieses Attributs entspricht dem *DisplayName* -Parameter, der an den Switch-Konstruktor übergeben wird.|  
|**Wert**|Erforderliches Attribut.<br /><br /> Gibt die Ebene des Schalters an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`switches`|Enthält Ablaufverfolgungsschalter und die Ebene, für die diese festgelegt sind.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Ebene eines Ablauf Verfolgungs Schalters ändern, indem Sie ihn in eine Konfigurationsdatei einfügen. Wenn der Schalter ein <xref:System.Diagnostics.BooleanSwitch>ist, können Sie ihn aktivieren und deaktivieren. Wenn der Schalter ein <xref:System.Diagnostics.TraceSwitch>ist, können Sie ihm verschiedene Ebenen zuweisen, um die Typen der von der Anwendung ausgegebenen Ablauf Verfolgungs-oder Debugmeldungen anzugeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das **\<Add >** -Elements verwendet wird, um den `General` Trace-Schalter auf die <xref:System.Diagnostics.TraceLevel> Ebene festzulegen und den `Data` booleschen Ablauf Verfolgungs Schalter zu aktivieren.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
