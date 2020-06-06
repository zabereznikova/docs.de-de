---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 7a76e5a90fe3218bc0302501b71daa9de0b098bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854837"
---
# \<userDefinedType>
Stellt einen benutzerdefinierten Typ (UDT) dar, der in den Dienstvertrag eingeschlossen werden soll.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<userDefinedTypes>**](userdefinedtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userDefinedType>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`name`|Ein optionales Attribut, das eine Zeichenfolge enthält, die den lesbaren Namen des Typs angibt. Dieses wird nicht von der Laufzeit verwendet, sondern hilft einem Reader bei der Typunterscheidung.|  
|`TypeDefID`|Eine GUID-Zeichenfolge, mit der der spezifische UDT-Typ in der registrierten Typbibliothek identifiziert wird.|  
|`TypeLibID`|Eine GUID-Zeichenfolge, die die registrierte Typbibliothek angibt, mit der der Typ definiert wird.|  
|`TypeLibVersion`|Eine Zeichenfolge, die die Version der Typbibliothek angibt, mit der der Typ definiert wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`userDefinedTypes`|Eine Auflistung von `userDefinedType`-Elementen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Durch Überprüfen der Typbibliothek werden von der Laufzeit der COM+-Integration Dienste erstellt. Wenn COM+-Komponenten Methoden enthalten, die einen VARIANT übergeben, können die tatsächlichen Typen, die vor der Laufzeit übergeben werden sollen, vom System nicht bestimmt werden. Aus diesem Grund tritt beim Versuch, einen benutzerdefinierten Typ in einem VARIANT zu übergeben, ein Fehler auf, da der Typ für die Serialisierung nicht bekannt ist.  
  
 Sie können jedoch der Konfigurationsdatei die UDTs hinzufügen, sodass diese als bekannte Typen im entsprechenden Dienstvertrag eingefügt werden können, um das Problem zu umgehen. Voraussetzung hierfür ist eine eindeutige Identifizierung des UDT und der Verträge, d.&#160;h. der ursprünglich verwendeten COM-Schnittstelle.  
  
 Im folgenden Beispiel wird veranschaulicht, wie dem <`userDefinedTypes`>-Abschnitt der Konfigurationsdatei zwei spezifische UDTs hinzugefügt werden.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 Beim Initialisieren des Diensts werden die angegebenen Typen von der Integrationslaufzeit gesucht und der Auflistung der bekannten Typen für die angegebenen Verträge hinzugefügt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [\<comContracts>](comcontracts.md)
- [Integration in com+-Anwendungen](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
