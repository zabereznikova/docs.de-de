---
title: <Type>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
ms.openlocfilehash: 4e88b49b82513079ddcf6f0bafe02d44235a406a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73091855"
---
# <a name="type-element-net-native"></a>\<Type>-Element (.net Native)

Wendet eine Laufzeitrichtlinie auf einen bestimmten Typ an, z. B. eine Klasse oder Struktur.

## <a name="syntax"></a>Syntax

```xml
<Type Name="type_name"
      Activate="policy_type"
      Browse="policy_type"
      Dynamic="policy_type"
      Serialize="policy_type"
      DataContractSerializer="policy_setting"
      DataContractJsonSerializer="policy_setting"
      XmlSerializer="policy_setting"
      MarshalObject="policy_setting"
      MarshalDelegate="policy_setting"
      MarshalStructure="policy_setting" />
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|Attributtyp|BESCHREIBUNG|
|---------------|--------------------|-----------------|
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Namen des Typs an|
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
|*type_name*|Der Typname. Wenn dieses `<Type>` Element das untergeordnete Element eines- [\<Namespace>](namespace-element-net-native.md) Elements oder eines anderen- `<Type>` Elements ist, kann *TYPE_NAME* den Namen des Typs ohne seinen Namespace einschließen. Andernfalls muss *type_name* den vollqualifizierten Typnamen enthalten.|

## <a name="all-other-attributes"></a>Alle anderen Attribute

|Wert|BESCHREIBUNG|
|-----------|-----------------|
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[\<AttributeImplies>](attributeimplies-element-net-native.md)|Wenn der enthaltende Typ ein Attribut ist, wird die Laufzeitrichtlinie für Codeelemente definiert, auf die das Attribut angewendet wird.|
|[\<Event>](event-element-net-native.md)|Wendet die Reflektionsrichtlinie auf ein Ereignis dieses Typs an.|
|[\<Field>](field-element-net-native.md)|Wendet die Reflektionsrichtlinie auf ein Feld dieses Typs an.|
|[\<GenericParameter>](genericparameter-element-net-native.md)|Wendet eine Richtlinie auf den Parametertyp eines generischen Typs an.|
|[\<ImpliesType>](impliestype-element-net-native.md)|Wendet eine Richtlinie auf einen Typ an, wenn diese Richtlinie an den Typ angewendet wurde, der vom enthaltenden `<Type>`-Element dargestellt wird.|
|[\<Method>](method-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Methode dieses Typs an.|
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine konstruierte generische Methode dieses Typs an.|
|[\<Property>](property-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Eigenschaft dieses Typs an.|
|[\<Subtypes>](subtypes-element-net-native.md)|Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.|
|`<Type>`|Wendet die Reflektionsrichtlinie auf einen geschachtelten Typ an.|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ an.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[\<Application>](application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.|
|[\<Assembly>](assembly-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einer angegebenen Assembly an.|
|[\<Library>](library-element-net-native.md)|Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.|
|[\<Namespace>](namespace-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einem Namespace an.|
|`<Type>`|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|

## <a name="remarks"></a>Bemerkungen

Die Reflektions-, Serialisierungs- und Interop-Attribute sind optional. Wenn keine vorhanden sind, dient das `<Type>`-Element als Container, dessen untergeordneten Typen Richtlinie für einzelne Member definieren.

Wenn ein-Element ein untergeordnetes Element eines-,-,- `<Type>` [\<Assembly>](assembly-element-net-native.md) oder-Elements ist [\<Namespace>](namespace-element-net-native.md) `<Type>` [\<TypeInstantiation>](typeinstantiation-element-net-native.md) , überschreibt es die vom übergeordneten Element definierten Richtlinien Einstellungen.

Ein `<Type>`-Element eines generischen Typs wendet seine Richtlinie auf alle Instanziierungen an, die keine eigene Richtlinie haben. Die Richtlinie der konstruierten generischen Typen wird durch das- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.

Wenn der Typ ein generischer Typ ist, wird sein Name mit einem Gravis-Akzentsymbol (\`) gefolgt von der Anzahl der generischen Parameter versehen. Das `Name`-Attribut eines `<Type>`-Elements wird für die <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Klasse beispielsweise als ``Name="System.Collections.Generic.List`1"`` angezeigt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird Reflektion zum Anzeigen von Informationen zu den Feldern, Eigenschaften und Methoden der <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Klasse verwendet. Die Variable `b` im Beispiel ist ein- <xref:Windows.UI.Xaml.Controls.TextBlock> Steuerelement. Da im Beispiel einfach Typinformationen abgerufen werden, wird die Verfügbarkeit von Metadaten über die `Browse`-Richtlinieneinstellung gesteuert.

 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]

 Da Metadaten für die- <xref:System.Collections.Generic.List%601> Klasse nicht automatisch von der .net Native-Toolkette eingeschlossen werden, kann im Beispiel die angeforderten Element Informationen zur Laufzeit nicht angezeigt werden. Um die erforderlichen Metadaten bereitzustellen, fügen Sie das folgende `<Type>`-Element der Laufzeitanweisungsdatei hinzu. Beachten Sie, dass wir, da wir ein übergeordnetes [<Namespace\>](namespace-element-net-native.md)-Element bereitgestellt haben, keinen vollqualifizierten Typnamen im `<Type>`-Element bereitstellen müssen.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="*Application*" Dynamic="Required All" />
      <Namespace Name ="System.Collections.Generic" >
        <Type Name="List`1" Browse="Required All" />
     </Namespace>
   </Application>
</Directives>
```

## <a name="example"></a>Beispiel
 Im folgenden Beispiel wird Reflektion zum Abrufen eines <xref:System.Reflection.PropertyInfo>-Objekts verwendet, das die <xref:System.String.Chars%2A?displayProperty=nameWithType>-Eigenschaft darstellt. Anschließend wird mithilfe der <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methode der Wert des siebten Zeichens in einer Zeichenfolge abgerufen, und alle Zeichen in der Zeichenfolge werden angezeigt. Die Variable `b` im Beispiel ist ein- <xref:Windows.UI.Xaml.Controls.TextBlock> Steuerelement.

 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]

 Da Metadaten für das- <xref:System.String> Objekt nicht verfügbar sind, löst der Aufruf der- <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> Methode zur Laufzeit eine-Ausnahme aus, wenn Sie <xref:System.NullReferenceException> mit der .net Native-Toolkette kompiliert wird. Fügen Sie folgendes `<Type>`-Element zur Laufzeitanweisungsdatei hinzu, um die Ausnahme zu eliminieren und die erforderlichen Metadaten bereitzustellen:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Assembly Name="*Application*" Dynamic="Required All" />
    <Type Name="System.String" Dynamic="Required Public"/> -->
  </Application>
</Directives>
```

## <a name="see-also"></a>Weitere Informationen

- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md)
