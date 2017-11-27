---
title: Verteilte Oracle-Transaktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7c48232bb204b71c662a99bf210ad54fc3ee9eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-distributed-transactions"></a>Verteilte Oracle-Transaktionen
Das <xref:System.Data.OracleClient.OracleConnection>-Objekt wird automatisch in einer vorhandenen verteilten Transaktion aufgelistet, wenn es ermittelt, dass eine Transaktion aktiv ist. Die automatische Eintragung von Transaktionen wird vorgenommen, wenn die Verbindung aus dem Verbindungspool geöffnet oder abgerufen wird. Die automatische Eintragung kann in vorhandenen Transaktionen deaktiviert werden, indem   
  
```  
Enlist=false  
```  
  
 als Verbindungszeichenfolgenparameter für die <xref:System.Data.OracleClient.OracleConnection> angegeben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
