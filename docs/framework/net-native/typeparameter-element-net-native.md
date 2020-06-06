---
title: <TypeParameter>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
ms.openlocfilehash: c69b535f3a01c287d30189138130066fc10a77e2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128927"
---
# <a name="typeparameter-element-net-native"></a>\<TypeParameter>-Element (.net Native)
Wendet eine Richtlinie auf den Typ an, der durch ein an eine Methode übergebenes Typargument dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Attributtyp|BESCHREIBUNG|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Der Name des Parameters vom Typ <xref:System.Type>. Z. B. lautet für die Methodensignatur `Type.GetInterfaceMap(Type interfaceType)` der Wert des `Name`-Attributs "InterfaceType".|  
|`Activate`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.|  
|`Serialize`|Serialisierung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.|  
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*parameter_name*|Der Name des Parameters vom Typ <xref:System.Type>. Z. B. lautet für die Methodensignatur `Type.GetInterfaceMap(Type interfaceType)` der Wert des `Name`-Attributs "InterfaceType".|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das- `<TypeParameter>` Element ähnelt dem- [\<Parameter>](parameter-element-net-native.md) Element, mit dem Unterschied, dass es nur auf Parameter vom Typ angewendet werden kann <xref:System.Type> . Es wendet die Richtlinie auf den Typ an, der zur Laufzeit durch das vom `Name`-Attribut angegebenen Typargument dargestellt wird.  
  
 Das NewtonSoft JSON-Serialisierungsprogramm enthält z. B. eine statische `JsonConvert.DeserializeObject(String value, Type type)`-Methode. Die folgenden Reflektionsanweisungen:  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 geben an, dass Metadaten für den Laufzeittyp, der durch das `type`-Argument dargestellt wird, für die Serialisierung verfügbar gemacht werden sollen. Wenn diese Laufzeitdirektiven für ein Projekt, das den folgenden Quellcode enthält, gelten:  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 machen die Reflektionsdirektiven die Metadaten für den `StockQuote`-Typ zur Laufzeit für das NewtonSoft JSON-Serialisierungsprogramm verfügbar.  
  
## <a name="see-also"></a>Weitere Informationen

- [\<Method>Gewisses](method-element-net-native.md)
- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
