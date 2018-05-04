---
title: '&lt;add&gt; des &lt;declaredTypes&gt;-Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 90eaf11ce8b9e3675a23ed3875680b03f149b56b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltdeclaredtypesgt-element"></a>&lt;add&gt; des &lt;declaredTypes&gt;-Elements
Fügt einen während der Deserialisierung vom <xref:System.Runtime.Serialization.DataContractSerializer> verwendeten Typ hinzu. Jeder deklarierte Typ umfasst die bekannten Typen, die als Feld oder Eigenschaft des deklarierten Typs zurückgegeben werden.  
  
 system.runtime.serialization  
\<"DataContractSerializer" >  
\<DeclaredTypes >  
\<Hinzufügen > der \<DeclaredTypes >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Erforderliches Zeichenfolgenattribut.<br /><br /> Gibt den Typnamen (einschließlich Namespace), den Assemblynamen, die Versionsnummer, die Kultur und das öffentliche Schlüsseltoken an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<KnownType >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Gibt den bekannten Typ für den deklarierten Typ an, der hinzugefügt wird. Falls es sich bei dem deklarierten Typ um einen generischen Typ handelt, müssen Sie auch dem `<knownType>`-Element ein Parameterelement hinzufügen, um anzugeben, welcher generische Parameter zum Zurückgeben des bekannten Typs verwendet wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<DeclaredTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Enthält die Typen, die während der Deserialisierung vom <xref:System.Runtime.Serialization.DataContractSerializer> bekannte Typen erfordern.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen über bekannte Typen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Finden Sie unter der [ \<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) für ein Beispiel für dieses Element.  
  
> [!NOTE]
>  Wenn Sie den <xref:System.Object>-Typ als `<declaredType>` hinzufügen, wird eine <xref:System.Configuration.ConfigurationErrorsException> ausgelöst. Der Grund hierfür ist, dass der <xref:System.Object>-Typ in der Konfiguration nicht als deklarierter Typ verwendet werden kann.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<Hinzufügen > der \<DeclaredTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
