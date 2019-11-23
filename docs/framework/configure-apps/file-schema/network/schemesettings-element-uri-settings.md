---
title: <schemeSettings>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697768"
---
# <a name="schemesettings-element-uri-settings"></a>\<SchemeSettings > Element (URI-Einstellungen)
Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<-URI >** ](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<SchemeSettings >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[add](add-element-for-schemesettings-uri-settings.md)|Fügt eine Schema Einstellung für einen Schema Namen hinzu.|  
|[clear](clear-element-for-schemesettings-uri-settings.md)|Löscht alle vorhandenen Schema Einstellungen.|  
|[remove](remove-element-for-schemesettings-uri-settings.md)|Entfernt eine Schema Einstellung für einen Schema Namen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.|  
  
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
 Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse verwendet wird, um das Escapezeichen für Prozent codierte Pfade für das http-Schema zu unterstützen.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a>Elementinformationen  
  
|||
|-|-|  
|Namespace|System|  
|Schemaname||  
|Validierungsdatei||  
|Kann leer sein||  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
