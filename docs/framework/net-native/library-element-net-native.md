---
title: <Library> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
ms.openlocfilehash: aeaa6b1a9c3c4ceebdd0eab3f331a044971398bf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287916"
---
# <a name="library-element-net-native"></a>\<Library> -Element (.net Native)

Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.  
  
 \<Directives>-Element  
\<Library>-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`Name`|Erforderliches Attribut. Gibt den Namen einer Assembly an. Untergeordnete Elemente dieses `<Library>`-Elements definieren die Laufzeitreflektionsrichtlinie für Typen und Typmember in dieser Assembly.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*assembly_name*|Der einfache Name der Assembly ohne Dateierweiterung. Dieses Attribut entspricht der <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>-Eigenschaft. Der Name einer Assembly namens Extensions.dll lautet beispielsweise "Extensions". Im Abschnitt „Hinweise“ ist eine besondere Form von *assembly_name* beschrieben, die den bedingten Einschluss von Metadaten aus der Assembly unterstützt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|Wendet die Richtlinie auf alle Typen in einer bestimmten Assembly an.|  
|[\<Namespace>](namespace-element-net-native.md)|Wendet die Richtlinie auf alle Typen in einem bestimmten Namespace an.|  
|[\<Type>](type-element-net-native.md)|Wendet die Richtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Wendet die Richtlinie auf einen konstruierten generischen Typ an. Beispielsweise kann ein- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element verwendet werden, um Richtlinien für einen Typ zu definieren `List<String>` .|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|Das Stammelement einer Laufzeitanweisungsdatei.|  
  
## <a name="remarks"></a>Hinweise  

 Das- [\<Directives>](directives-element-net-native.md) Element kann NULL, ein oder mehrere- `<Library>` Elemente enthalten.  
  
 Das `<Library>`-Element dient als Container für die Definition der Programmelemente, deren Metadaten zur Laufzeit benötigt werden. Dieses Element drückt keine Richtlinie aus. Zur Kompilierzeit durchsuchen die Compilertools nur die im `<Library>`-Element bezeichnete Bibliothek nach Programmelementen, die durch seine untergeordneten Elemente identifiziert werden. Im Gegensatz dazu durchsuchen Compilertools alle Bibliotheken, including.NET Framework-Kernbibliotheken, nach Programmelementen, die durch untergeordnete Elemente des-Elements identifiziert werden [\<Application>](application-element-net-native.md) .  
  
 `<Library>`-Direktiven können bedingt verwendet werden. Wenn der Name des `<Library>` Elements mit einem Sternchen () beginnt und endet \* , wirkt sich die `<Library>` Direktive nur dann aus, wenn die APP auf die zwischen den Sternchen angegebene Assembly verweist. Beispielsweise gilt die folgende Lauf Zeit Direktive nur, wenn von der APP auf die Utilities.dll-Assembly verwiesen wird.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a>Siehe auch

- [\<Application>-Element](application-element-net-native.md)
- [\<Directives>-Element](directives-element-net-native.md)
- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
