---
title: "Abgebrochene abgewickelte Vorgänge pro Sekunde"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a54b84f2fa0ab9c7531a17e69b10f78c725255ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-operations-aborted-per-second"></a>Abgebrochene abgewickelte Vorgänge pro Sekunde
Indikatorname: Abgebrochene abgewickelte Vorgänge pro Sekunde.  
  
## <a name="description"></a>Beschreibung  
 Anzahl der von in diesem Dienst abgebrochenen Transaktionsvorgänge pro Sekunde.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
