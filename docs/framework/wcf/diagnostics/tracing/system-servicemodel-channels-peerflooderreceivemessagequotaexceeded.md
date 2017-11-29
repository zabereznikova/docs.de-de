---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2931eec5646b44eea19d70b11eb43c056b0ee0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
Die Empfangsrate eingehender Nachrichten ist zu hoch.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung tritt auf, wenn versucht wird, eingehende Nachrichten zu verarbeiten. Eine Nachricht konnte nicht an einen bestimmten Nachbarn weitergeleitet werden, da das festgelegte Kontingent für diesen Nachbarn überschritten wurde. Dies tritt auf, wenn ein nicht reagierender Nachbar das Backlog der anstehenden Nachrichten für diesen Nachbarn nicht löst.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Reduzieren Sie die Rate, mit der Nachrichten innerhalb des Mesh gesendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung beheben](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
