---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641618"
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Von der Klasse TransportBindingElement werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die Klasse TransportBindingElement verfügt über die folgenden Eigenschaften:  
  
### <a name="manualaddressing"></a>ManualAddressing  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob der Benutzer die Kontrolle über die Nachrichtenadressierung übernehmen möchte.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 Datentyp: sint64  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Pufferpoolgröße der Bindung.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 Datentyp: sint64  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die maximale Größe einer Nachricht, die von dieser Bindung verarbeitet wird.  
  
### <a name="scheme"></a>Schema  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Das URI-Schema für den Transport.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.TransportBindingElement>
