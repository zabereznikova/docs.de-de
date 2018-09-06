---
title: Inhaltsbasierte Korrelation
ms.date: 03/30/2017
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
ms.openlocfilehash: c0367f480701468dcd5024ea3439bdcd38acc78f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785816"
---
# <a name="content-based-correlation"></a>Inhaltsbasierte Korrelation
Dieses Beispiel veranschaulicht, wie die Messagingaktivitäten (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply>) mit mehreren inhaltsbasierten Korrelationen und einer inhaltsbasierter Korrelation verwendet werden können. In diesem Szenario wird zuerst auf Grundlage einer Bestellungs-ID eine Korrelation initialisiert, und dann wird auf Grundlage der Kunden-ID später eine andere Korrelation erstellt. Dies zeigt, wie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität basierend auf der gleichen eingehenden Nachricht einer vorhandenen Korrelation folgen und eine neue Korrelation initialisieren kann.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Messagingaktivitäten und inhaltsbasierte Korrelation  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird gezeigt, wie mehrere inhaltsbasierte Korrelationen verwendet werden.  In diesem Szenario wird zuerst auf Grundlage einer Bestellungs-ID eine Korrelation initialisiert, und dann wird auf Grundlage der Kunden-ID später eine andere Korrelation erstellt.  Die Korrelationen überlappen mithilfe einer <xref:System.ServiceModel.Activities.Receive>-Aktivität, die auf Grundlage der gleichen eingehenden Nachricht einer vorhandenen Korrelation (PurchaseOrderId) folgt und eine neue Korrelation (CustomerId) initialisiert.  Die <xref:System.ServiceModel.Activities.Receive>-Aktivität erreicht dies mithilfe der Eigenschaften <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> und <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.  
  
## <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit erweiterten Berechtigungen, indem Sie mit der rechten Maustaste die [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] und wählen Sie dann **als Administrator ausführen**.  
  
2.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "CascadingCorrelation.sln".  
  
3.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
4.  Drücken Sie F5, um den Server auszuführen.  
  
5.  Sobald der Dienst bereit ist und Nachrichten überwacht, klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Clientprojekt, und führen Sie es aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`