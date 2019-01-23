---
title: '&lt;MethodInstantiation&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2d05f9c727672c4f249e388a32b1101aaafd2f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538259"
---
# <a name="ltmethodinstantiationgt-element-net-native"></a>&lt;MethodInstantiation&gt; Element (.NET Native)
Wendet eine Laufzeitreflektionsrichtlinie auf eine konstruierte generische Methode an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Namen der Methode an.|  
|`Signature`|Allgemein|Optionales Attribut. Gibt benannte Parameter der Methode an. Mehrere benannte Parameter werden durch Kommas getrennt. Das `Signature`-Attribut wird dazu verwendet, überladene Methoden zu unterscheiden.|  
|`Arguments`|Allgemein|Erforderliches Attribut. Gibt die generischen Typargumente an. Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen nach Informationen über eine Methode oder das Auflisten einer Methode, ermöglicht jedoch keinen dynamischen Aufruf zur Laufzeit.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf einen Konstruktor oder eine Methode, um die dynamische Programmierung zu ermöglichen. Diese Richtlinie stellt sicher, dass ein Member dynamisch zur Laufzeit aufgerufen werden kann.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*method_name*|Der Methodenname. Der Typ der Methode wird durch das übergeordnete Element [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) definiert.|  
  
## <a name="signature-attribute"></a>Signature-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*method_signature*|Gibt die benannten Parameter der Methode an. Wenn mehrere Parameter vorhanden sind, werden sie durch Kommas getrennt.|  
  
## <a name="arguments-attribute"></a>Arguments-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*method_arguments*|Gibt die generischen Typargumente an. Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt. Jedes Argument muss aus dem vollqualifizierten Typnamen bestehen.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für die Methode angewendet werden soll. Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<MethodInstantiation>`-Element überschreibt die Laufzeitreflektionsrichtlinie der entsprechenden offenen generischen Methode.  
  
## <a name="see-also"></a>Siehe auch
- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [\<Method> Element (Element <Method>)](../../../docs/framework/net-native/method-element-net-native.md)
