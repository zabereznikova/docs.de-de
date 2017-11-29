---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c130093b9600c324e7179febce6857341b8a7d3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 <xref:System.ServiceModel.Channels.TransportBindingElement>
