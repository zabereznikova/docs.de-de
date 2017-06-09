---
title: "&lt;Typ&gt; Element (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
caps.latest.revision: 33
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 33
---
# &lt;Typ&gt; Element (.NET Native)
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
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Typnamen an.|  
|`Activate`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.|  
|`Serialize`|Serialisierung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.|  
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die mithilfe der <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> Klasse.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung verwendet die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> Klasse.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die verwendet die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Klasse.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*TYPE_NAME*|Der Typname. Wenn diese `<Type>` Element ist das untergeordnete ein [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) Elements oder eines anderen `<Type>` Element *Type_name* zählen der Name des Typs ohne den Namespace. Andernfalls *Type_name* muss den vollqualifizierten Typnamen enthalten.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Laufzeitrichtlinieneinstellungen der Richtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|Wenn der enthaltende Typ ein Attribut ist, wird die Laufzeitrichtlinie für Codeelemente definiert, auf die das Attribut angewendet wird.|  
|[<>\>](../../../docs/framework/net-native/event-element-net-native.md)|Wendet die Reflektionsrichtlinie auf ein Ereignis dieses Typs an.|  
|[<>\>](../../../docs/framework/net-native/field-element-net-native.md)|Wendet die Reflektionsrichtlinie auf ein Feld dieses Typs an.|  
|[<>\>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|Wendet eine Richtlinie auf den Parametertyp eines generischen Typs an.|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Wendet eine Richtlinie auf einen Typ an, wenn diese Richtlinie an den Typ angewendet wurde, der vom enthaltenden `<Type>`-Element dargestellt wird.|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Methode dieses Typs an.|  
|[<>\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine konstruierte generische Methode dieses Typs an.|  
|[<>\>](../../../docs/framework/net-native/property-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Eigenschaft dieses Typs an.|  
|[<>\>](../../../docs/framework/net-native/subtypes-element-net-native.md)|Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.|  
|`<Type>`|Wendet die Reflektionsrichtlinie auf einen geschachtelten Typ an.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einer angegebenen Assembly an.|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.|  
|[<>\>](../../../docs/framework/net-native/namespace-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einem Namespace an.|  
|`<Type>`|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Reflektions-, Serialisierungs- und Interop-Attribute sind optional. Wenn keine vorhanden sind, dient das `<Type>`-Element als Container, dessen untergeordneten Typen Richtlinie für einzelne Member definieren.  
  
 Wenn ein `<Type>` Element ist das untergeordnete Element ein [ <> \</> \> ](../../../docs/framework/net-native/assembly-element-net-native.md), [ <> \</> \> ](../../../docs/framework/net-native/namespace-element-net-native.md), `<Type>`, oder [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) Elements ist, überschreibt es die vom übergeordneten Element definierten Richtlinieneinstellungen.  
  
 Ein `<Type>`-Element eines generischen Typs wendet seine Richtlinie auf alle Instanziierungen an, die keine eigene Richtlinie haben. Die Richtlinie der konstruierten generischen Typen wird definiert, indem die [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) Element.  
  
 Wenn der Typ ein generischer Typ ist, wird der Name durch ein Symbol Gravis-Akzent ergänzt ("") gefolgt von der Anzahl der generischen Parameter. Z. B. die `Name` -Attribut des ein `<Type>` -Element für die <xref:System.Collections.Generic.List%601?displayProperty=fullName> Klasse wird als `Name="System.Collections.Generic.List`1"".  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird Reflektion zum Anzeigen von Informationen über die Felder, Eigenschaften und Methoden der <xref:System.Collections.Generic.List%601?displayProperty=fullName> Klasse. Die Variable `b` in diesem Beispiel ist ein [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) Steuerelement. Da im Beispiel einfach Typinformationen abgerufen werden, wird die Verfügbarkeit von Metadaten über die `Browse`-Richtlinieneinstellung gesteuert.  
  
 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]  
  
 Da Metadaten für die <xref:System.Collections.Generic.List%601> Klasse nicht automatisch enthalten, durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)] -toolkette im Beispiel keine angeforderten Memberinformationen zur Laufzeit anzuzeigen. Um die erforderlichen Metadaten bereitzustellen, fügen Sie das folgende `<Type>`-Element der Laufzeitdirektivendatei hinzu. Beachten Sie, dass, da wir ein übergeordnetes Element angegeben haben [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) Element, wir brauchen Geben Sie einen vollständig qualifizierten Typnamen in der `<Type>` Element.  
  
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
 Im folgenden Beispiel wird Reflektion zum Abrufen einer <xref:System.Reflection.PropertyInfo> -Objekt, das darstellt, die <xref:System.String.Chars%2A?displayProperty=fullName> Eigenschaft. Anschließend wird mithilfe der [PropertyInfo.GetValue (Object, Object\<xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=fullName> -Methode zum Abrufen des Werts des siebten Zeichens in einer Zeichenfolge, und alle Zeichen in der Zeichenfolge angezeigt. Die Variable `b` in diesem Beispiel ist ein [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) Steuerelement.  
  
 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]  
  
 Da Metadaten für die <xref:System.String> Objekt ist nicht verfügbar, den Aufruf der [PropertyInfo.GetValue (Object, Object\<xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=fullName> -Methode löst eine <xref:System.NullReferenceException> Ausnahme zur Laufzeit Zeit bei der Kompilierung mit der [!INCLUDE[net_native](../../../includes/net-native-md.md)] -toolkette. Fügen Sie folgendes `<Type>`-Element zur Laufzeitdirektivendatei hinzu, um die Ausnahme zu eliminieren und die erforderlichen Metadaten bereitzustellen:  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
    <Type Name="System.String" Dynamic="Required Public"/> -->  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeit-Konfigurationsdatei Laufzeitdirektiven (rd.xml) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elemente der Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Richtlinie für die Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md)