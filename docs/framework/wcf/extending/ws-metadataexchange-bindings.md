---
title: WS-MetadataExchange-Bindungen
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293987"
---
# <a name="ws-metadataexchange-bindings"></a>WS-MetadataExchange-Bindungen

In diesem Thema wird beschrieben, wie die Standardmetadatenaustausch-Bindungen für verschiedene Transporte erstellt werden.  
  
## <a name="the-default-bindings"></a>Die Standardbindungen  
  
|Standardbindungsname|Wie die Bindung erstellt wird|  
|--------------------------|------------------------------------|  
|mexHttpBinding|Eine <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter Sicherheit auf Transportebene.|  
|mexHttpsBinding|Eine <xref:System.ServiceModel.WSHttpBinding>, die Sicherheit auf Transportebene unterstützt.|  
|mexNamedPipeBinding|Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>, das die Standardwerte verwendet.|  
|mexTcpBinding|Eine <xref:System.ServiceModel.Channels.CustomBinding> mit einem <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, das die Standardwerte verwendet.|
