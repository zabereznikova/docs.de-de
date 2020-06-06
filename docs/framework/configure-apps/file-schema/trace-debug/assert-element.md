---
title: <assert>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: f3c1a1670139a8262dea449bfff99c7c1c19f088
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088950"
---
# <a name="assert-element"></a>\<assert>-Element
Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**

## <a name="syntax"></a>Syntax  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`assertuienabled`|Optionales Attribut.<br /><br /> Gibt an, ob ein Meldungs Feld angezeigt werden soll, wenn die **Debug. Assert** -Methode als **false**ausgewertet wird.|  
|`logfilename`|Optionales Attribut.<br /><br /> Gibt den Namen der Datei an, in die die Nachricht geschrieben werden soll, wenn **Debug. Assert** als **false**ausgewertet wird.|  
  
## <a name="assertuienabled-attribute"></a>assertuiaktiviertes Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`true`|Zeigt das Meldungs Feld an. Dies ist die Standardeinstellung.|  
|`false`|Das Meldungs Feld wird nicht angezeigt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
  
## <a name="remarks"></a>Bemerkungen  
 Beide Attribute im- **\<assert>** Element sind optional. Sie können Meldungs Felder deaktivieren, ohne eine Datei anzugeben, in die die Nachrichten geschrieben werden sollen, oder Sie können eine Datei angeben, in die Nachrichten geschrieben werden, während die Nachrichten Felder aktiviert werden  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie das Anzeigen von Meldungs Feldern deaktivieren, wenn Sie **Debug. Assert** aufzurufen und die Nachrichten in schreiben `c:\log.txt` .  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Diagnostics.Debug>
- [Schema für Ablaufverfolgungs- und Debugeinstellungen](index.md)
