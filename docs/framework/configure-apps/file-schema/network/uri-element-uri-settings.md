---
title: <uri>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697437"
---
# <a name="uri-element-uri-settings"></a>\<uri>-Element (URI-Einstellungen)
Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[IDN](idn-element-uri-settings.md)|Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.|  
|[IriParsing](iriparsing-element-uri-settings.md)|Gibt an, ob die IRI-Verarbeitung (International Resource Identifier) auf angewendet wird <xref:System.Uri> und ob IRI-Erteilungs Regeln angewendet werden sollen.|  
|[schemeSettings](schemesettings-element-uri-settings.md)|Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|Enthält Einstellungen für alle Namespaces.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `uri` Element enthält Einstellungen für Member der-Klasse, die <xref:System.Uri> von Klassen im- <xref:System.Net> Namespace verwendet werden. Die Einstellungen konfigurieren die Unterstützung für IRI und IDN.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>BESCHREIBUNG  
 Das folgende Beispiel zeigt eine Konfiguration, die von der- <xref:System.Uri> Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird. Das Beispiel löscht außerdem alle Schema Einstellungen und fügt dann Unterstützung für die nicht-Escapezeichen für Prozent codierte Pfade für das http-Schema hinzu.  
  
### <a name="code"></a>Code  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Netzwerkeinstellungsschema](index.md)
