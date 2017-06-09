---
title: "Bew&#228;hrte Methoden: Vermittler | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Bew&#228;hrte Methoden: Vermittler
Es muss darauf geachtet werden, Fehler beim Aufrufen von Vermittlern ordnungsgemäß zu behandeln, um sicherzustellen, dass dienstseitige Kanäle auf dem Vermittler ordnungsgemäß geschlossen werden.  
  
 Nehmen Sie folgendes Szenario als Beispiel:Ein Client ruft einen Vermittler auf, der dann einen Back\-End\-Dienst aufruft.Der Back\-End\-Dienst definiert keinen Fehlervertrag, deshalb wird jeder von diesem Dienst ausgelöster Fehler als nicht typisierter Fehler behandelt.Der Back\-End\-Dienst löst einen <xref:System.ApplicationException> aus, und WCF bricht den dienstseitigen Kanal ordnungsgemäß ab.Der <xref:System.ApplicationException> taucht dann als <xref:System.ServiceModel.FaultException> auf, der zum Vermittler ausgelöst wird.Der Vermittler löst den <xref:System.ApplicationException> erneut aus.WCF interpretiert dieses als nicht typisierten Fehler vom Vermittler und leitet ihn an den Client weiter.Sowohl der Vermittler als auch der Client bemängeln ihre clientseitigen Kanäle bei Empfang des Fehlers.Der dienstseitige Kanal des Vermittlers bleibt jedoch geöffnet, da WCF nicht weiß, ob der Fehler schwerwiegend ist.  
  
 Die Best Practice in diesem Szenario ist es, zu erkennen, ob der Fehler, der vom Dienst kommt, schwerwiegend ist. Ist dies der Fall, sollte der Vermittler seinen dienstseitigen Kanal bemängeln, wie im folgenden Codeausschnitt angezeigt.  
  
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
  
## Siehe auch  
 [WCF\-Fehlerbehandlung](../../../docs/framework/wcf/wcf-error-handling.md)   
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)