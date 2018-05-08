---
title: 'Kernkommunikationen: TCP-Transportkanäle'
ms.date: 03/30/2017
ms.assetid: d5cd057f-faec-4e21-ae0e-18bbc22bcfb1
ms.openlocfilehash: 0dfbf939b39d53f104d749e0c0d24e04a05185e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="core-communications-tcp-transport-channels"></a>Kernkommunikationen: TCP-Transportkanäle
In diesem Thema sind alle von den TCP-Transportkanälen generierten Ausnahmen aufgeführt.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|SocketCloseReadTimeout|Der Remoteendpunkt des angegebenen Sockets hat auf eine Anforderung zum Schließen nicht innerhalb des zugewiesenen Zeitlimits geantwortet. Möglicherweise ruft der Remoteendpunkt nach dem Empfang des EOF-Signals (NULL) vom Receive-Vorgang nicht Close auf. Die für diesen Vorgang zugewiesene Zeit war möglicherweise ein Teil eines längeren Timeouts.|
