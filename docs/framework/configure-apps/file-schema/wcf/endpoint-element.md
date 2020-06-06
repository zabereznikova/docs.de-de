---
title: <endpoint>-Element
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855380"
---
# <a name="endpoint-element"></a>\<endpoint>-Element
Gibt die Bindung, den Vertrag und Adresseigenschaften für einen Dienstendpunkt an, der zur Verfügbarmachung von Diensten verwendet wird.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|address|Eine Zeichenfolge mit der Adresse des Endpunkts. Die Adresse kann als absolute oder relative Adresse angegeben werden. Bei Bereitstellung einer relativen Adresse wird vom Host erwartet, dass er eine Basisadresse bereitstellt, die für das in der Bindung verwendete Transportschema geeignet ist. Wenn keine Adresse konfiguriert wird, wird angenommen, dass die Basisadresse der Adresse für diesen Endpunkt entspricht.<br /><br /> Der Standardwert ist eine leere Zeichenfolge.|  
|behaviorConfiguration|Eine Zeichenfolge mit dem Namen des Verhaltens, das am Endpunkt verwendet werden soll.|  
|binding|Erforderliches Zeichenfolgenattribut, das den Typ der zu verwendenden Bindung angibt. Dieser muss einen registrierten Konfigurationsabschnitt aufweisen, da sonst nicht auf ihn verwiesen werden kann. Der Typ wird anhand des Abschnittsnamens registriert, nicht anhand des Typnamens der Bindung.|  
|bindingConfiguration|Eine Zeichenfolge, die den Namen der Bindung enthält, die beim Instanziieren des Endpunkts verwendet werden soll. Der Name der Bindung muss sich bei der Endpunktdefinition im Gültigkeitsbereich befinden. Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Dieses Attribut wird zusammen mit `binding` zum Verweisen auf eine spezifische Bindungskonfiguration in der Konfigurationsdatei verwendet. Legen Sie dieses Attribut fest, wenn Sie eine benutzerdefinierte Bindung verwenden möchten. Andernfalls wird unter Umständen eine Ausnahme ausgelöst.|  
|bindingName|Eine Zeichenfolge, die den eindeutigen qualifizierten Namen der Bindung für den Definitionsexport über WSDL definiert. Der Standardwert ist eine leere Zeichenfolge.|  
|bindingNamespace|Eine Zeichenfolge, die den qualifizierten Namen des Namespaces der Bindung für den Definitionsexport über WSDL definiert. Der Standardwert ist eine leere Zeichenfolge.|  
|contract|Eine Zeichenfolge, die angibt, welche Verträge von diesem Endpunkt verfügbar gemacht werden. Die Assembly muss den Vertragstyp implementieren. Wenn eine Dienstimplementierung einen einzelnen Vertragstyp implementiert, kann diese Eigenschaft ausgelassen werden. Der Standardwert ist eine leere Zeichenfolge.|  
|endpointConfiguration|Eine Zeichenfolge, die den Namen des Standardendpunkts angibt, der mit dem `kind`-Attribut festgelegt wird, das auf die zusätzlichen Konfigurationsinformationen dieses Standardendpunkts verweist. Der gleiche Name muss im Abschnitt `<standardEndpoints>` definiert werden.|  
|isSystemEndpoint|Ein boolescher Wert, der angibt, ob ein Endpunkt ein Infrastrukturendpunkt ist.|  
|kind|Eine Zeichenfolge, die den Typ des angewendeten Standardendpunkts angibt. Der Typ muss im `<extensions>` Abschnitt oder in Machine. config registriert werden. Wenn nichts angegeben wird, wird ein allgemeiner Dienst Endpunkt erstellt.|  
|listenUriMode|Gibt an, wie der Transport die `ListenUri` verarbeitet, die für die Überwachung durch den Dienst bereitgestellt wurde. Folgende Werte sind gültig:<br /><br /> -Explizit<br />-Eindeutig<br /><br /> Der Standardwert ist Explicit.|  
|listenUri|Eine Zeichenfolge mit dem URI, an dem der Dienstendpunkt lauscht. Der Standardwert ist eine leere Zeichenfolge.|  
|name|Optionales Attribut. Eine Zeichenfolge, die den Namen des Dienstendpunkts angibt. Der Standardwert ist die Verkettung des Bindungsnamen und des Vertragsbeschreibungsnamens. Dienste haben möglicherweise mehrere Endpunkte, sodass das `name`-Attribut des Endpunkts sich vom Namen des Diensts unterscheidet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<headers>](headers.md)|Eine Auflistung von Adressheadern.|  
|[\<identity>](identity.md)|Eine Identität, welche die Authentifizierung eines Endpunkts durch andere Endpunkte ermöglicht, mit denen Nachrichten ausgetauscht werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<service>](service.md)|Ein Konfigurationsabschnitt, der eine Liste mit Endpunkten definiert, zu denen ein Client eine Verbindung herstellen kann.|  
  
## <a name="example"></a>Beispiel  
 Dies ist ein Beispiel für eine Dienstendpunkt-Konfiguration.  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [Endpunkte: Adressen, Bindungen und Verträge](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
