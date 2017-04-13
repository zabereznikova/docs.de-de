---
title: "&lt;Eigenschaft&gt; Element (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# &lt;Eigenschaft&gt; Element (.NET Native)
Wendet eine Laufzeitreflektionsrichtlinie auf eine Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Eigenschaftennamen an.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen nach Informationen über die Eigenschaft oder das Auflisten der Eigenschaft, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf die Eigenschaft, um dynamische Programmierung zu ermöglichen. Diese Richtlinie stellt sicher, dass eine Eigenschaft zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.|  
|`Serialize`|Serialisierung|Optionales Attribut. Steuert den Laufzeitzugriff auf eine Eigenschaft, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*keine Variablenargumentlisten verwenden*|Der Eigenschaftenname. Der Typ der Eigenschaft wird vom übergeordneten Element definiert [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) oder [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) Element.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für die Eigenschaft angewendet werden soll. Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`. Weitere Informationen finden Sie unter [Laufzeitrichtlinieneinstellungen der Richtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Richtlinie einer Eigenschaft nicht explizit definiert ist, erbt sie die Laufzeitrichtlinie des übergeordneten Elements.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird Reflektion zum Instanziieren eines `Book`-Objekts und zum Anzeigen seiner Eigenschaftenwerte verwendet. Die ursprüngliche Datei default.rd.xml für das Projekt sieht folgendermaßen aus:  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
  
```  
  
 Die Datei wendet den Wert `All` auf die `Activate`-Richtlinie für die `Book`-Klasse an, die den Zugriff auf Klassenkonstruktoren über Reflektion ermöglicht. Die `Browse`-Richtlinie für die `Book`-Klasse wird vom übergeordneten Namespace geerbt. Diese wird auf `Required Public` festgelegt, wodurch Metadaten zur Laufzeit verfügbar werden.  
  
 Der Quellcode für das Beispiel lautet wie folgt. Die `outputBlock` Variable steht für einen [TextBlock](http://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) Steuerelement.  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 Kompilieren und Ausführen dieses Beispiels löst jedoch eine [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) Ausnahme. Obwohl wir Metadaten für den `Book`-Typ verfügbar gemacht haben, haben wir keine Implementierungen der Eigenschaftengetter dynamisch zur Verfügung gestellt. Wir können diesen Fehler auf eine von zwei Arten beheben:  
  
-   durch die Definition der `Dynamic` -Richtlinie für die `Book` Geben Sie in der [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) Element.  
  
-   Durch Hinzufügen eines verschachtelten [ <> \> ](../../../docs/framework/net-native/property-element-net-native.md) -Element für jede Eigenschaft, deren Getter wir aufrufen möchten, wie in die folgenden Datei default.rd.xml.  
  
    ```  
  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeit-Konfigurationsdatei Laufzeitdirektiven (rd.xml) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elemente der Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Richtlinie für die Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md)