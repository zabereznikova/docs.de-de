---
title: "Kernkommunikation: Named Pipe-Transportkanäle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14ab8f84-ab3e-47cd-8ac5-dd68af940175
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43ca027a4696feeab1c0a1400b7f43a6d2b1e2fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="core-communications-named-pipe-transport-channels"></a>Kernkommunikation: Named Pipe-Transportkanäle
Dieses Thema enthält alle Ausnahmen, die von Named Pipe-Transportkanälen generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|PipeCantCloseWithPendingWrite|Die Pipe kann während eines anstehenden Schreibvorgangs nicht geschlossen werden.|  
|PipeReadPending|Für die Pipe wird bereits ein Lesevorgang ausgeführt.|  
|PipeShutdownReadError|Der Lesevorgang des Pipe-"Herunterfahren"-Indikators ist fehlgeschlagen.|  
|PipeShutdownWriteError|Der Schreibvorgang des Pipe-"Herunterfahren"-Indikators ist fehlgeschlagen.|  
|PipeWritePending|Für die Pipe wird bereits ein Schreibvorgang ausgeführt.|
