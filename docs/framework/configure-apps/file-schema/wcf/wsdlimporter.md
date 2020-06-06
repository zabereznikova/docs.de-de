---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854757"
---
# \<wsdlImporter>
Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`type`|Der Typ dieses Elements.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|Gibt alle WSDL-Importer an, mit denen Web Services Description Language (WSDL) 1.1-Metadaten mit WS-Richtlinienanhängen importiert werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Ein WSDL-Importer wird zum Importieren von Metadaten und zum Konvertieren der Informationen in verschiedene Klassen verwendet, die Vertrags- und Endpunktinformationen darstellen. Vertrags- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import- und Konvertierungsvorgang relevant sind, können selektiv importiert werden. Außerdem wird der Import von Bindungsinformationen und -eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL-Dokumente, WSDL-Erweiterungen und XML-Schemadokumente bereitstellen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [WCF-Clientkonfiguration](../../../wcf/feature-details/client-configuration.md)
- [Clients](../../../wcf/feature-details/clients.md)
