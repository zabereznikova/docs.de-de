---
title: Vorgangsleistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 59c75dacb2a01f1b85d67d5cc1651dbc55b6aa8e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320166"
---
# <a name="operation-performance-counters"></a>Vorgangsleistungsindikatoren
Vorgangsleistungsindikatoren befinden sich unter dem `ServiceModelOperation 4.0.0.0`-Leistungsobjekt, wenn sie mit dem Leistungsmonitor (Perfmon.exe) angezeigt werden. Jeder Vorgang hat eine einzelne Instanz. Das heißt, wenn ein bestimmter Vertrag 10 Vorgänge enthält, werden mit diesem Vertrag 10 Vorgangsleistungsindikatoren verbunden. Die Objektinstanzen werden nach dem folgenden Muster benannt:  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 Mit diesem Indikator können Sie messen, wie der Aufruf verwendet wird und wie gut der Vorgang funktioniert.  
  
> [!CAUTION]
> Es gibt eine Längenbeschränkung des Namens einer Leistungsindikatorinstanz. Wenn der Name einer Windows Communication Foundation (WCF)-Leistungs Zählers die maximale Länge überschreitet, ersetzt WCF einen Teil des Instanznamens durch einen Hashwert.  
  
## <a name="see-also"></a>Siehe auch

- [Leistungsindikatoren](index.md)
