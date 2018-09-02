---
title: Senden und Behandeln von Fehlern
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 896f209e7daeeab2bb33c1fde15298aae96c8776
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406657"
---
# <a name="sending-and-handling-faults"></a>Senden und Behandeln von Fehlern
In diesem Beispiel wird veranschaulicht, wie die <xref:System.ServiceModel.Activities.SendReply>-Messagingaktivität und <xref:System.ServiceModel.Activities.ReceiveReply>-Messagingaktivität verwendet werden, um erwartete und unerwartete Fehler zu senden und zu empfangen. In diesem Szenario führt die erste Clientanforderung zu einem erwarteten Fehler, der in der <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>-Auflistung enthalten ist. Die nächsten Clientanforderungen führen zu unerwarteten Fehlern, bevor die abschließende Anforderung erfolgreich ist.  
  
## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erweiterten Berechtigungen, indem Sie mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.  
  
2.  Öffnen Sie die Faults.sln-Projektmappendatei.  
  
3.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
4.  Führen Sie das Dienstprojekt aus.  
  
    1.  In **Projektmappen-Explorer**, mit der rechten Maustaste die `FaultService` Projekt, und wählen **als Startprojekt festlegen**.  
  
    2.  Drücken Sie STRG+F5.  
  
5.  Öffnen Sie eine andere Kopie des [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erweiterten Berechtigungen, indem Sie mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.  
  
6.  Öffnen Sie die Faults.sln-Projektmappendatei.  
  
7.  Führen Sie das Clientprojekt aus.  
  
    1.  In **Projektmappen-Explorer**, mit der rechten Maustaste die `FaultClient` Projekt, und wählen **als Startprojekt festlegen**.  
  
    2.  Drücken Sie STRG+F5.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`