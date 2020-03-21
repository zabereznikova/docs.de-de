---
title: <schemeSettings>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154646"
---
# <a name="schemesettings-element-uri-settings"></a>\<schemeSettings>-Element (URI-Einstellungen)
Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.  
  
[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeEinstellungen>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Hinzufügen](add-element-for-schemesettings-uri-settings.md)|Fügt eine Schemaeinstellung für einen Schemanamen hinzu.|  
|[Klar](clear-element-for-schemesettings-uri-settings.md)|Löscht alle vorhandenen Schemaeinstellungen.|  
|[Entfernen](remove-element-for-schemesettings-uri-settings.md)|Entfernt eine Schemaeinstellung für einen Schemanamen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Uri](uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie .NET Framework Webadressen verarbeitet, die mithilfe einheitlicher Ressourcenbezeichner (URIs) ausgedrückt werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Standardmäßig entweicht <xref:System.Uri?displayProperty=nameWithType> die Klasse prozentweise codierte Pfadtrennzeichen, bevor die Pfadkomprimierung ausgeführt wird. Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgenden implementiert:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Wenn dieser URI an Module weitergegeben wird, die prozentisch codierte Zeichen nicht korrekt verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Aus diesem <xref:System.Uri?displayProperty=nameWithType> Grund werden Pfadtrennzeichen der Klasse zuerst nicht entweichen und dann die Pfadkomprimierung angewendet. Das Ergebnis der Übergabe der <xref:System.Uri?displayProperty=nameWithType> schädlichen URL oben an den Klassenkonstruktor führt zu folgendem URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Dieses Standardverhalten kann mithilfe der Konfigurationsoption schemeSettings für ein bestimmtes Schema geändert werden, um nicht das Escape-Prozent-codierte Pfadtrennzeichen zu entführen.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine <xref:System.Uri> Konfiguration, die von der Klasse verwendet wird, um nicht aus percentcodierte Pfadtrennzeichen für das http-Schema zu entkommen.  
  
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
|Name des Schemas||  
|Validierungsdatei||  
|Kann leer sein||  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Netzwerkeinstellungsschema](index.md)
