---
title: 'Endpunkt: Übergegangene Transaktionen pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44227141"
---
# <a name="endpoint-transactions-flowed-per-second"></a>Endpunkt: Übergegangene Transaktionen pro Sekunde
Indikatorname: Transaktionen Flowed Per Second.  
  
## <a name="description"></a>Beschreibung  
 Die Anzahl der Transaktionen, die an diesem Endpunkt pro Sekunde in Vorgänge übergegangen sind. Dieser Indikator wird jedes Mal gesteigert, wenn eine Transaktions-ID in einer Nachricht vorhanden ist, die an den Endpunkt gesendet wird.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
