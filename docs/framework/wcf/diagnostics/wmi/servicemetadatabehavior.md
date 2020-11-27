---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 921a880dad0d77558a70dff8a09f75c25a3cbb8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262280"
---
# <a name="servicemetadatabehavior"></a>ServiceMetadataBehavior

ServiceMetadataBehavior  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die ServiceMetadataBehavior-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die ServiceMetadataBehavior-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="externalmetadatalocation"></a>ExternalMetadataLocation  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, zu dem der Dienst Metadatenanforderungen umleitet.  
  
### <a name="httpgetenabled"></a>HttpGetEnabled  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.  
  
### <a name="httpgeturl"></a>HttpGetUrl  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.  
  
### <a name="httpsgetenabled"></a>HttpsGetEnabled  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.  
  
### <a name="httpsgeturl"></a>HttpsGetUrl  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
