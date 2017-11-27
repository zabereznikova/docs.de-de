---
title: Aufrufe pro Sekunde
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0efb5a94-d83b-4793-b529-6fcbedb65c43
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 54e8b60679c7e7106f5b2e28abfebe5adc589174
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="calls-per-second"></a>Aufrufe pro Sekunde
Zählername: Aufrufe pro Sekunde  
  
## <a name="description"></a>Beschreibung  
 Anzahl von Aufrufen in diesem Vorgang pro Sekunde.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
