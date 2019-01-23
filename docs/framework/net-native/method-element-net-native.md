---
title: '&lt;Methode&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdfec7ce93dd3954af03f6f4822ac00576a7e043
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562929"
---
# <a name="ltmethodgt-element-net-native"></a>&lt;Methode&gt; Element (.NET Native)
Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Namen der Methode an.|  
|`Signature`|Allgemein|Optionales Attribut. Gibt die Methodensignatur an. Wenn mehrere Parameter vorhanden sind, werden sie durch Kommas getrennt. Das folgende `<Method>`-Element definiert beispielsweise die Richtlinie für die <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29>-Methode.<br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> Wenn das Attribut nicht vorhanden ist, gilt die Laufzeitanweisung für alle Überladungen der Methode.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen nach Informationen über eine Methode oder das Auflisten einer Methode, ermöglicht jedoch keinen dynamischen Aufruf zur Laufzeit.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf einen Konstruktor oder eine Methode, um die dynamische Programmierung zu ermöglichen. Diese Richtlinie stellt sicher, dass ein Member dynamisch zur Laufzeit aufgerufen werden kann.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*method_name*|Der Methodenname. Der Typ der Methode wird durch das übergeordnete Element [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) definiert.|  
  
## <a name="signature-attribute"></a>Signature-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*method_signature*|Die Parametertypen, die die Signatur der Methode bilden. Mehrere Parameter werden durch Kommas getrennt, z. B. `"System.String,System.Int32,System.Int32)"`. Parametertypnamen müssen vollqualifiziert sein.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md)|Wendet die Richtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.|  
|[\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|Wendet die Richtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.|  
|[\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Wendet die Richtlinie auf einen Typ an, wenn diese Richtlinie auf die Methode angewendet wurde, die vom enthaltenden `<Method>`-Element dargestellt wird.|  
|[\<TypeParameter>](../../../docs/framework/net-native/typeparameter-element-net-native.md)|Wendet die Richtlinie auf den Typ an, der von einem <xref:System.Type>-Argument dargestellt wird, dass an eine Methode übergeben wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `<Method>`-Element einer generischen Methode wendet seine Richtlinie für alle Instanziierungen an, die keine eigene Richtlinie haben.  
  
 Sie können das `Signature`-Attribut zum Angeben einer Richtlinie für eine bestimmte Methodenüberladung verwenden. Wenn das `Signature`-Attribut aber nicht vorhanden ist, gilt die Laufzeitrichtlinie für alle Überladungen der Methode.  
  
 Sie können die Laufzeitreflektionsrichtlinie für einen Konstruktor nicht mit dem `<Method>`-Element definieren. Verwenden Sie stattdessen das `Activate`-Attribut des Elements [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md), [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md), [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).  
  
## <a name="example"></a>Beispiel  
 Die `Stringify`-Methode im folgenden Beispiel ist eine allgemeine Formatierungsmethode, die Reflektion verwendet, um ein Objekt in seine Zeichenfolgendarstellung zu konvertieren. Zusätzlich zum Aufrufen der Standard-`ToString`-Methode des Objekts kann die Methode eine formatierte Ergebniszeichenfolge durch Übergeben der `ToString`-Methode eines Objekts an eine Formatzeichenfolge, eine <xref:System.IFormatProvider>-Implementierung oder beides erzeugen. Sie kann auch eine der <xref:System.Convert.ToString%2A?displayProperty=nameWithType>-Überladungen aufrufen, die eine Zahl in die binäre, oktale oder hexadezimale Zeichenfolgendarstellung konvertiert.  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Die `Stringify`-Methode kann durch Code wie dem folgenden aufgerufen werden:  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Bei der Kompilierung mit .NET Native kann das Beispiel allerdings zur Laufzeit einige Ausnahmen auslösen, einschließlich der <xref:System.NullReferenceException>- und [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)-Ausnahmen. Dies geschieht, da die `Stringify`-Methode in erster Linie die dynamische Formatierung der primitiven Typen in der Klassenbibliothek von .NET Framework unterstützen soll. Allerdings werden die Metadaten nicht durch die Standardanweisungsdatei zur Verfügung gestellt. Auch wenn die Metadaten verfügbar gemacht werden, löst das Beispiel [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)-Ausnahmen aus, da die entsprechenden `ToString`-Implementierungen nicht im nativen Code eingeschlossen wurden.  
  
 Diese Ausnahmen können alle mithilfe des [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)-Elements gelöscht werden, um die Typen zu definieren, deren Metadaten vorhanden sein müssen, und durch Hinzufügen von `<Method>`-Elementen, um sicherzustellen, dass die Implementierung von Methodenüberladungen, die dynamisch aufgerufen werden können, ebenfalls vorhanden ist. So sieht die Datei "default.rd.xml" aus, die diese Ausnahmen eliminiert und die Ausführung des Beispiels ohne Fehler ermöglicht.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a>Siehe auch
- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [Element \<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)
