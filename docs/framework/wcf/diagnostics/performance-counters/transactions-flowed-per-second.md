---
title: "Übergegangene Transaktionen pro Sekunde"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 432ed6adbaa1f121f11680e0f9574a642565a6f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="transactions-flowed-per-second"></a>Übergegangene Transaktionen pro Sekunde
Indikatorname: Transaktionen Flowed Per Second  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der in einer Sekunde an diesen Vorgang übergegangenen Transaktionen. Dieser Indikator wird jeweils inkrementiert, wenn eine TransaktionsID in einer Nachricht enthalten ist, die an den Vorgang gesendet wird.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
