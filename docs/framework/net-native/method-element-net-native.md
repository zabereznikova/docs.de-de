---
title: <Method>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
ms.openlocfilehash: 8db32c660846b4f4071fff2a40c760a3d1ef2489
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180991"
---
# <a name="method-element-net-native"></a>\<Method>-Element (.net Native)
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
  
|attribute|Attributtyp|BESCHREIBUNG|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Namen der Methode an.|  
|`Signature`|Allgemein|Optionales Attribut. Gibt die Methodensignatur an. Wenn mehrere Parameter vorhanden sind, werden sie durch Kommas getrennt. Das folgende `<Method>`-Element definiert beispielsweise die Richtlinie für die <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29>-Methode.<br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> Wenn das Attribut nicht vorhanden ist, gilt die Laufzeitrichtlinie für alle Überladungen der Methode.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen nach Informationen über eine Methode oder das Auflisten einer Methode, ermöglicht jedoch keinen dynamischen Aufruf zur Laufzeit.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf einen Konstruktor oder eine Methode, um die dynamische Programmierung zu ermöglichen. Diese Richtlinie stellt sicher, dass ein Member dynamisch zur Laufzeit aufgerufen werden kann.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*method_name*|Der Methodenname. Der Typ der Methode wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.|  
  
## <a name="signature-attribute"></a>Signature-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*method_signature*|Die Parametertypen, die die Signatur der Methode bilden. Mehrere Parameter werden durch Kommas getrennt, z. B. `"System.String,System.Int32,System.Int32)"`. Parametertypnamen müssen vollqualifiziert sein.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Parameter>](parameter-element-net-native.md)|Wendet die Richtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.|  
|[\<GenericParameter>](genericparameter-element-net-native.md)|Wendet die Richtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.|  
|[\<ImpliesType>](impliestype-element-net-native.md)|Wendet die Richtlinie auf einen Typ an, wenn diese Richtlinie auf die Methode angewendet wurde, die vom enthaltenden `<Method>`-Element dargestellt wird.|  
|[\<TypeParameter>](typeparameter-element-net-native.md)|Wendet die Richtlinie auf den Typ an, der von einem <xref:System.Type>-Argument dargestellt wird, dass an eine Methode übergeben wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Ein `<Method>`-Element einer generischen Methode wendet seine Richtlinie für alle Instanziierungen an, die keine eigene Richtlinie haben.  
  
 Sie können das `Signature`-Attribut zum Angeben einer Richtlinie für eine bestimmte Methodenüberladung verwenden. Wenn das `Signature`-Attribut aber nicht vorhanden ist, gilt die Laufzeitrichtlinie für alle Überladungen der Methode.  
  
 Sie können die Laufzeitreflektionsrichtlinie für einen Konstruktor nicht mit dem `<Method>`-Element definieren. Verwenden Sie stattdessen das-Attribut des-,-,- `Activate` [\<Assembly>](assembly-element-net-native.md) oder- [\<Namespace>](namespace-element-net-native.md) [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.  
  
## <a name="example"></a>Beispiel  
 Die `Stringify`-Methode im folgenden Beispiel ist eine allgemeine Formatierungsmethode, die Reflektion verwendet, um ein Objekt in seine Zeichenfolgendarstellung zu konvertieren. Zusätzlich zum Aufrufen der Standard-`ToString`-Methode des Objekts kann die Methode eine formatierte Ergebniszeichenfolge durch Übergeben der `ToString`-Methode eines Objekts an eine Formatzeichenfolge, eine <xref:System.IFormatProvider>-Implementierung oder beides erzeugen. Sie kann auch eine der <xref:System.Convert.ToString%2A?displayProperty=nameWithType>-Überladungen aufrufen, die eine Zahl in die binäre, oktale oder hexadezimale Zeichenfolgendarstellung konvertiert.  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Die `Stringify`-Methode kann durch Code wie dem folgenden aufgerufen werden:  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Bei der Kompilierung mit .NET Native kann das Beispiel allerdings zur Laufzeit einige Ausnahmen auslösen, einschließlich der <xref:System.NullReferenceException>- und [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)-Ausnahmen. Dies geschieht, da die `Stringify`-Methode in erster Linie die dynamische Formatierung der primitiven Typen in der Klassenbibliothek von .NET Framework unterstützen soll. Allerdings werden die Metadaten nicht durch die Standardanweisungsdatei zur Verfügung gestellt. Auch wenn die Metadaten verfügbar gemacht werden, löst das Beispiel [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)-Ausnahmen aus, da die entsprechenden `ToString`-Implementierungen nicht im nativen Code eingeschlossen wurden.  
  
 Diese Ausnahmen können entfernt werden, indem das- [\<Type>](type-element-net-native.md) Element verwendet wird, um die Typen zu definieren, deren Metadaten vorhanden sein müssen, und durch Hinzufügen von `<Method>` Elementen, um sicherzustellen, dass die Implementierung von Methoden Überladungen, die dynamisch aufgerufen werden können, ebenfalls vorhanden ist. So sieht die Datei "default.rd.xml" aus, die diese Ausnahmen eliminiert und die Ausführung des Beispiels ohne Fehler ermöglicht.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md)
- [\<MethodInstantiation>Gewisses](methodinstantiation-element-net-native.md)
