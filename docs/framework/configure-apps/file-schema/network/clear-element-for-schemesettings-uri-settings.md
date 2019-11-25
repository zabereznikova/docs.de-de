---
title: <clear>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087445"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a>\<Clear >-Element für SchemeSettings (URI-Einstellungen)
Löscht alle vorhandenen Schema Einstellungen.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<URI->** ](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<SchemeSettings >** ](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Löschen** >

## <a name="syntax"></a>Syntax  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<schemeSettings>-Element (URI-Einstellungen)](schemesettings-element-uri-settings.md)|Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig wird die <xref:System.Uri?displayProperty=nameWithType>-Klasse vor dem Ausführen der Pfad Komprimierung in Prozent codierte Pfad Trennzeichen aufheben. Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Aus diesem Grund werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse zunächst Pfad Trennzeichen aufgehoben, und dann wird die Pfad Komprimierung angewendet. Das Ergebnis der Übergabe der obigen bösartigen URL an <xref:System.Uri?displayProperty=nameWithType> Klassenkonstruktor führt zum folgenden URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse verwendet wird, die alle Schema Einstellungen löscht und dann Unterstützung für das Aufheben der Escapezeichen für Prozent codierte Pfad Trennzeichen für das http-Schema hinzufügt.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
