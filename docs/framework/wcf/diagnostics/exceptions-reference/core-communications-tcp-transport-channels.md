---
title: 'Kernkommunikation: TCP-Transportkanäle'
ms.date: 03/30/2017
ms.assetid: d5cd057f-faec-4e21-ae0e-18bbc22bcfb1
ms.openlocfilehash: c9b2b31aaffccaae442f4444f69538245a813570
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277334"
---
# <a name="core-communications-tcp-transport-channels"></a>Kernkommunikation: TCP-Transportkanäle

In diesem Thema sind alle von den TCP-Transportkanälen generierten Ausnahmen aufgeführt.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|SocketCloseReadTimeout|Der Remoteendpunkt des angegebenen Sockets hat auf eine Anforderung zum Schließen nicht innerhalb des zugewiesenen Zeitlimits geantwortet. Möglicherweise ruft der Remoteendpunkt nach dem Empfang des EOF-Signals (NULL) vom Receive-Vorgang nicht Close auf. Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.|
