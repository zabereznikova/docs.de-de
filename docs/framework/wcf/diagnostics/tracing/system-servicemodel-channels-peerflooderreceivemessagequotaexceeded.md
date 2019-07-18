---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 0ca3d198ce225221348ac7b405ea91ad215cd298
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61950643"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
Die Empfangsrate eingehender Nachrichten ist zu hoch.  
  
## <a name="description"></a>Beschreibung  
 Diese Ablaufverfolgung tritt auf, wenn versucht wird, eingehende Nachrichten zu verarbeiten. Eine Nachricht konnte nicht an einen bestimmten Nachbarn weitergeleitet werden, da das festgelegte Kontingent für diesen Nachbarn überschritten wurde. Dies tritt auf, wenn ein nicht reagierender Nachbar das Backlog der anstehenden Nachrichten für diesen Nachbarn nicht löst.  
  
## <a name="troubleshooting"></a>Problembehandlung  
 Reduzieren Sie die Rate, mit der Nachrichten innerhalb des Mesh gesendet werden.  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)
