---
title: "Benutzerdefinierte Überwachungsdatensätze"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a459e6df0e030f4e17bb73461d8fa790a61787e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="custom-tracking-records"></a>Benutzerdefinierte Überwachungsdatensätze
In diesem Thema wird veranschaulicht, wie benutzerdefinierte Überwachungsdatensätze erstellt und mit Daten gefüllt werden, die mit den Datensätzen ausgegeben werden sollen.  
  
## <a name="emitting-custom-tracking-records"></a>Ausgeben von benutzerdefinierten Nachverfolgungsdatensätzen  
 Eine Codeaktivität kann benutzerdefinierte Nachverfolgungsdatensätze ausgeben, wie im folgenden Beispiel gezeigt.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 Ein <xref:System.Activities.Tracking.CustomTrackingRecord>-Objekt wird in einer Codeaktivität ausgegeben, indem die <xref:System.Activities.NativeActivityContext.Track%2A>-Methode für den `ActvityContext` aufgerufen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Server App Fabric-Überwachung](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Überwachen von Anwendungen mit AppFabric](http://go.microsoft.com/fwlink/?LinkId=201275)
