---
title: WS-MetadataExchange-Bindungen
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795472"
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
