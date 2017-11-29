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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 31e10bade2b467b01b47f01f894fee438f523e44
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
