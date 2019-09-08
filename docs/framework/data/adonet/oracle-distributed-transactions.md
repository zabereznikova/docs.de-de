---
title: Verteilte Oracle-Transaktionen
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 6f910f1dbbe448352c0edd5d1b80df659ac453d4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795147"
---
# <a name="oracle-distributed-transactions"></a>Verteilte Oracle-Transaktionen
Das <xref:System.Data.OracleClient.OracleConnection>-Objekt wird automatisch in einer vorhandenen verteilten Transaktion aufgelistet, wenn es ermittelt, dass eine Transaktion aktiv ist. Die automatische Eintragung von Transaktionen wird vorgenommen, wenn die Verbindung aus dem Verbindungspool geöffnet oder abgerufen wird. Die automatische Eintragung kann in vorhandenen Transaktionen deaktiviert werden, indem  
  
```  
Enlist=false  
```  
  
 als Verbindungszeichenfolgenparameter für die <xref:System.Data.OracleClient.OracleConnection> angegeben wird.  
  
## <a name="see-also"></a>Siehe auch

- [Oracle und ADO.NET](oracle-and-adonet.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
