---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 6590c5188e4e1758987a75fbd007099703ea6bc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250423"
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement

MsmqTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Von der MsmqTransportBindingElement-Klasse werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  

 Die MsmqTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="maxpoolsize"></a>MaxPoolSize  

 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Maximale Größe des Pools, der interne MSMQ-Nachrichtenobjekte enthält.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Enumerationswert, der den Wartenschlangentransport für den Kommunikationskanal angibt, der von der Bindung verwendet wird.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt einen booleschen Wert zurück, der angibt, ob Warteschlangenadressen mit Active Directory konvertiert werden sollen.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
