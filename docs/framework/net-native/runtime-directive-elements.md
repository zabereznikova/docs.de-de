---
title: Elemente der Laufzeitanweisung
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: 96bce89c02ad17d1b30eda66237f69a15123dcd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250800"
---
# <a name="runtime-directive-elements"></a>Elemente der Laufzeitanweisung

Das Dateiformat der Laufzeitanweisungen (rd.xml) unterstützt die folgenden Laufzeitanweisungselemente. Eine hierarchische Darstellung finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [\<Application>](application-element-net-native.md)  
 Wendet die Laufzeitreflektionsrichtlinie auf alle von der Anwendung verwendeten Typen an und dient als Container für anwendungsweite Typen und Typmember, deren Metadaten für die Reflektion zur Laufzeit verfügbar sind. Dies ist ein untergeordnetes Element des- [\<Directives>](directives-element-net-native.md) Elements.  
  
 [\<Assembly>](assembly-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an. Dies ist ein untergeordnetes [\<Application>](application-element-net-native.md) Element des-Elements und des- [\<Library>](library-element-net-native.md) Elements.  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 Wenn die enthaltende [\<Type>](type-element-net-native.md) Direktive ein Attribut ist, wendet eine Lauf Zeit Richtlinie auf Code Elemente an, auf die dieses Attribut angewendet wird.  
  
 [\<Directives>](directives-element-net-native.md)  
 Das Stamm Element in jeder laufzeitdirektivendatei für .net Native. Die untergeordneten Elemente sind [\<Application>](application-element-net-native.md) und [\<Library>](library-element-net-native.md) .  
  
 [\<Event>](event-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf ein Ereignis an. Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.  
  
 [\<Field>](field-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf ein Feld an. Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.  
  
 [\<Library>](library-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an. Dies ist ein untergeordnetes [\<Application>](application-element-net-native.md) Element des-Elements und des- [\<Library>](library-element-net-native.md) Elements.  
  
 [\<Method>](method-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf eine Methode an. Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf eine konstruierte generische Methode an. Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.  
  
 [\<Namespace>](namespace-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf alle Typen in einem Namespace an.  
  
 [\<Parameter>](parameter-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.  
  
 [\<Property>](property-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf eine Eigenschaft an. Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.  
  
 [\<Type>](type-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf einen Typ an.  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf einen konstruierten generischen Typ an.  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf den Typ an, der durch ein <xref:System.Type>-Argument, das an eine Methode übergeben wird, dargestellt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [„rd.xml“-Konfigurationsdateireferenz](runtime-directives-rd-xml-configuration-file-reference.md)
