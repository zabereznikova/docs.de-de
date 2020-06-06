---
title: <legacyCorruptedStateExceptionsPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116460"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy>-Element
Gibt an, ob durch den Common Language Runtime verwalteter Code Zugriffs Verletzungen und andere beschädigte Zustands Ausnahmen abfangen kann.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, dass die Anwendung beschädigte Zustands Ausnahme Fehler abfängt, wie z. b. Zugriffs Verletzungen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`false`|Die Anwendung fängt keine Beschädigung von Zustands Ausnahme Fehlern, z. b. Zugriffs Verletzungen, ab. Dies ist die Standardeinstellung.|  
|`true`|Die Anwendung fängt beschädigte Zustands Ausnahme Fehler wie z. b. Zugriffs Verletzungen auf.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 In der .NET Framework Version 3,5 und früher ermöglichte der Common Language Runtime verwalteten Code das Abfangen von Ausnahmen, die von beschädigten Prozesszuständen ausgelöst wurden. Eine Zugriffsverletzung ist ein Beispiel für diese Art von Ausnahme.  
  
 Ab .NET Framework 4 fängt der verwaltete Code diese Typen von Ausnahmen in-Blöcken nicht mehr ab `catch` . Sie können diese Änderung jedoch außer Kraft setzen und die Behandlung von beschädigten Zustands Ausnahmen auf zwei Arten beibehalten:  
  
- Legen `<legacyCorruptedStateExceptionsPolicy>` Sie das-Attribut des-Elements `enabled` auf fest `true` . Diese Konfigurationseinstellung wird Processwide angewendet und wirkt sich auf alle Methoden aus.  
  
 Oder  
  
- Wenden Sie das- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> Attribut auf die Methode an, die den Ausnahmen `catch` Block enthält.  
  
 Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Anwendung auf das Verhalten vor dem .NET Framework 4 zurückgesetzt werden soll, und alle Fehler bei der Beschädigung von Zustands Fehlern abgefangen werden.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
