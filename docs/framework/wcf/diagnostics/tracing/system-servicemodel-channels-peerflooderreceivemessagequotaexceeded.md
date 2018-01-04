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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 136baabc0760826aa9ba76dc19862c9c4b60e16e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
Die Empfangsrate eingehender Nachrichten ist zu hoch.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung tritt auf, wenn versucht wird, eingehende Nachrichten zu verarbeiten. Eine Nachricht konnte nicht an einen bestimmten Nachbarn weitergeleitet werden, da das festgelegte Kontingent für diesen Nachbarn überschritten wurde. Dies tritt auf, wenn ein nicht reagierender Nachbar das Backlog der anstehenden Nachrichten für diesen Nachbarn nicht löst.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Reduzieren Sie die Rate, mit der Nachrichten innerhalb des Mesh gesendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
