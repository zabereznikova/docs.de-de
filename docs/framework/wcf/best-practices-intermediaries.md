---
title: 'Best Practices: Vermittler'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7aecdcecedcee98828b398f9172985d2e09fb9be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-intermediaries"></a>Best Practices: Vermittler
Beim Aufrufen von Vermittlern müssen Fehler ordnungsgemäß behandelt werden, um sicherzustellen, dass dienstseitige Kanäle im Vermittler ordnungsgemäß geschlossen werden.  
  
 Betrachten Sie folgendes Szenario. Ein Client ruft einen Vermittler auf, der dann einen Back-End-Dienst aufruft.  Der Back-End-Dienst definiert keinen Fehlervertrag. Deshalb wird jeder von diesem Dienst ausgelöste Fehler als nicht typisierter Fehler behandelt.  Löst die Back-End-Dienst eine <xref:System.ApplicationException> und WCF bricht den dienstseitigen Kanal ordnungsgemäß ab. Die <xref:System.ApplicationException> wird dann als <xref:System.ServiceModel.FaultException> für den Vermittler ausgelöste Ausnahme ausgegeben. Der Vermittler löst die <xref:System.ApplicationException> erneut aus. WCF interpretiert diese als nicht typisierten Fehler vom Vermittler und leitet den Fehler an den Client weiter. Bei Empfang des Fehlers lösen der Vermittler und der Client Fehler für ihre clientseitigen Kanäle aus. Der dienstseitige Kanal des Vermittlers bleibt jedoch geöffnet, da WCF nicht weiß, ob es sich um einen schwerwiegenden Fehler handelt.  
  
 Für dieses Szenario wird empfohlen, zu bestimmen, ob der vom Dienst stammende Fehler schwerwiegend ist, und wenn er schwerwiegend ist, sollte der Vermittler einen Fehler für seinen dienstseitigen Kanal auslösen, wie im folgenden Codeausschnitt gezeigt.  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    Else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Fehlerbehandlung](../../../docs/framework/wcf/wcf-error-handling.md)  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
