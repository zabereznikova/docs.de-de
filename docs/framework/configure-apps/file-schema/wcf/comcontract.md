---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 35596f32bf0e0de9081bc0d4c33fb370c7ab708b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173782"
---
# \<comContract>

Gibt einen Dienstvertrag für die COM+-Integration an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|contract|Eine Zeichenfolge, die den Vertragstyp enthält.|  
|name|Eine Zeichenfolge, die den Vertragsnamen enthält.|  
|Namespace|Eine Zeichenfolge, die den Vertragsnamespace enthält.|  
|requiresSession|Ein boolescher Wert, der angibt, ob der Vertrag nur für sitzungsbasierte Bindungen verwendet werden kann. Bei der Initialisierung des Diensts wird von der Integrationslaufzeit sichergestellt, dass diese Einstellung mit dem verwendeten Bindungstyp übereinstimmt. Eine Ausnahme wird generiert, wenn eine oder mehrere Bindungen für den Vertrag miteinander in Konflikt stehen. Wenn die Eigenschaft `false` ist, ein Einwegkanal verwendet wird und [out]-Parameter vorhanden sind, wird ebenfalls eine Ausnahme generiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|persistableTypes|Alle dauerhaften Typen.|  
|userDefinedTypes|Eine Auflistung benutzerdefinierter Typen (UDT), die im Dienstvertrag verwendet werden soll.|  
|exposedMethods|Eine Auflistung von COM+-Methoden, die verfügbar gemacht werden, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|comContracts|Enthält eine Auflistung von `comContract`-Elementen.|  
  
## <a name="remarks"></a>Bemerkungen  

 Com+-Integrations Dienstverträge sind zurzeit auf den `http://tempuri.org` Namespace beschränkt, und der Vertrags Name wird von der unterstützenden com-Schnittstelle abgeleitet. Sie können Alternativen aber angeben, indem Sie den `comContracts`-Abschnitt und das `comContract`-Element in der Konfigurationsdatei verwenden. Sie können beispielsweise folgende Konfiguration zum Angeben des Namespaces, des Vertragsnamens, der benutzerdefinierten Typen und anderer Einstellungen für einen Dienstvertrag verwenden.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [Integration in com+-Anwendungen](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
