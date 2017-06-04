---
title: "Kernkommunikation: Named Pipe-Transportkan&#228;le | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 14ab8f84-ab3e-47cd-8ac5-dd68af940175
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Kernkommunikation: Named Pipe-Transportkan&#228;le
Dieses Thema enthält alle Ausnahmen, die von Named Pipe\-Transportkanälen generiert werden.  
  
## Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|--------------------|----------------------------|  
|PipeCantCloseWithPendingWrite|Die Pipe kann während eines anstehenden Schreibvorgangs nicht geschlossen werden.|  
|PipeReadPending|Für die Pipe wird bereits ein Lesevorgang ausgeführt.|  
|PipeShutdownReadError|Der Lesevorgang des Pipe\-"Herunterfahren"\-Indikators ist fehlgeschlagen.|  
|PipeShutdownWriteError|Der Schreibvorgang des Pipe\-"Herunterfahren"\-Indikators ist fehlgeschlagen.|  
|PipeWritePending|Für die Pipe wird bereits ein Schreibvorgang ausgeführt.|