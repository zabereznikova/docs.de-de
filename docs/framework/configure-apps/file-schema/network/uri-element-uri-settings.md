---
title: <uri>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697437"
---
# <a name="uri-element-uri-settings"></a>\<URI-> Element (URI-Einstellungen)
Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<-URI >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 None.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[idn](idn-element-uri-settings.md)|Gibt an, ob die Analyse für internationale Domänennamen (IDN) auf den Domänennamen angewendet wird.|  
|[iriParsing](iriparsing-element-uri-settings.md)|Gibt an, ob die IRI-Verarbeitung (International Resource Identifier) auf <xref:System.Uri> angewendet wird und ob IRI-Erteilungs Regeln angewendet werden sollen.|  
|[schemeSettings](schemesettings-element-uri-settings.md)|Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|Enthält Einstellungen für alle Namespaces.|  
  
## <a name="remarks"></a>Hinweise  
 Das `uri`-Element enthält Einstellungen für Member der <xref:System.Uri> Klasse, die von Klassen im <xref:System.Net>-Namespace verwendet werden. Die Einstellungen konfigurieren die Unterstützung für IRI und IDN.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse zur Unterstützung der IRI-Verarbeitung und IDN-Namen verwendet wird. Das Beispiel löscht außerdem alle Schema Einstellungen und fügt dann Unterstützung für die nicht-Escapezeichen für Prozent codierte Pfade für das http-Schema hinzu.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
