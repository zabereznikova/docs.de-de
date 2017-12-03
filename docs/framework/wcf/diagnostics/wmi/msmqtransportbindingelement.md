---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 572a19723583a6bc717a71b3b46040148f29e1cd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 Datentyp: string (Zeichenfolge)  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
