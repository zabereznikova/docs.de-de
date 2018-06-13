---
title: Verfügbarmachen und Aufrufen von ActivityActions
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: 2d369ec4b028b047ce02016dd511c1c088b46a91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513151"
---
# <a name="exposing-and-invoking-activityactions"></a>Verfügbarmachen und Aufrufen von ActivityActions
In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität, die über eine <xref:System.Activities.ActivityAction> verfügt, entwickelt wird. Darüber hinaus wird die Verwendung dieser Aktivität veranschaulicht, indem eine Implementierung der <xref:System.Activities.ActivityAction> bereitgestellt wird.  
  
 Ein <xref:System.Activities.ActivityAction> ermöglicht einem aktivitätsautor, "Löcher" mit bestimmten Signaturen, in denen der aktivitätsbenutzer ein benutzerdefiniertes Verhalten einbinden kann, verfügbar zu machen. Z. B. die <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` Aktivität (die über eine Auflistung von Elementen wirkt) hat eine <xref:System.Activities.ActivityAction> , mit dessen Hilfe der aktivitätsbenutzer Verhalten einzubinden, das auf das aktuelle iterationselement wirkt.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen der **ActivityAction.sln** -Beispielprojektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, und führen Sie sie aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`