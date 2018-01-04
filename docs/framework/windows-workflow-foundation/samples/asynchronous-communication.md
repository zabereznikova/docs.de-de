---
title: Asynchrone Kommunikation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 602fc0ee27d460b11851103b88983d37b472b77a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="asynchronous-communication"></a>Asynchrone Kommunikation
Anhand dieses Beispiels wird veranschaulicht, wie die Kommunikation zwischen zwei verschiedenen [!INCLUDE[wf](../../../../includes/wf-md.md)]-Diensten standardmäßig asynchron erfolgt.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Asynchrone Kommunikation zwischen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Diensten.  
  
## <a name="discussion"></a>Diskussion  
 Dieses Beispiel zeigt, wie die Kommunikation zwischen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Anwendungen mithilfe der von .NET Framework bereitgestellten Messagingaktivitäten asynchron erfolgt.  
  
 Dieses Beispiel besteht aus den folgenden drei Projekten.  
  
 CreditCheckService  
 Dieser Dienst empfängt den Kreditscore (die Kreditwürdigkeit) einer bestimmten Person oder den Wert des zu erwerbenden Elements und legt dann fest, ob der Person der Kredit gewährt wird.  
  
 RentalApprovalService  
 Dieser Dienst empfängt eine Anwendung von einer Person, die einen Kredit benötigt. Dieser Dienst kommuniziert asynchron mit dem `CreditCheckService`-Dienst, um zu bestimmen, ob die Kreditanwendung gültig ist.  
  
 Client  
 Der Client kommuniziert synchron mit dem `RentalApprovalService`-Dienst, um zu ermitteln, ob der Kredit genehmigt wird.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Mit der rechten Maustaste die **AsynchronousCommunication** Lösung, und wählen **Eigenschaften**.  
  
2.  In **allgemeine Eigenschaften**Option **Startprojekt**, und wählen Sie **mehrere Startprojekte**.  
  
3.  Verschieben Sie **RentalApprovalService** an die erste Position in der Liste, gefolgt von **CreditCheckService**, gefolgt von **Client**. Legen Sie die **starten** Aktion für alle drei Projekte.  
  
4.  Klicken Sie auf **OK**, und drücken Sie F5, um das Beispiel ausführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
