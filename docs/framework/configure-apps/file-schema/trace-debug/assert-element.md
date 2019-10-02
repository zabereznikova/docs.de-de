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
ms.openlocfilehash: 30ec24aefcf8c4d1e110238a2c60a958eded5545
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699386"
---
# <a name="assert-element"></a>\<assert >-Element
Gibt an, ob ein Meldungsfeld angezeigt wird, wenn Sie die <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>-Methode aufrufen. Außerdem wird der Name der Datei angegeben, in die die Meldung geschrieben werden soll.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. Diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<assert >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`assertuienabled`|Optionales Attribut.<br /><br /> Gibt an, ob ein Meldungs Feld angezeigt werden soll, wenn die **Debug. Assert** -Methode als **false**ausgewertet wird.|  
|`logfilename`|Optionales Attribut.<br /><br /> Gibt den Namen der Datei an, in die die Nachricht geschrieben werden soll, wenn **Debug. Assert** als **false**ausgewertet wird.|  
  
## <a name="assertuienabled-attribute"></a>assertuiaktiviertes Attribut  
  
|Wert|Beschreibung|  
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
  
## <a name="remarks"></a>Hinweise  
 Beide Attribute im **\<assert->** Element sind optional. Sie können Meldungs Felder deaktivieren, ohne eine Datei anzugeben, in die die Nachrichten geschrieben werden sollen, oder Sie können eine Datei angeben, in die Nachrichten geschrieben werden, während die Nachrichten Felder aktiviert werden  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die Anzeige von Meldungs Feldern beim Abrufen von **Debug. Assert** deaktiviert und die Nachrichten in `c:\log.txt` geschrieben werden.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Debug>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](index.md)
