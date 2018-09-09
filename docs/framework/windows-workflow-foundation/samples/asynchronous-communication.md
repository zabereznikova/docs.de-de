---
title: Asynchrone Kommunikation
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: e85f7efb0de1326ceb5091c305b20f34809eab57
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44251585"
---
# <a name="asynchronous-communication"></a>Asynchrone Kommunikation
In diesem Beispiel wird veranschaulicht, wie die Kommunikation zwischen zwei verschiedene Windows Workflow Foundation (WF)-Dienste standardmäßig asynchron ausgeführt wird.  
  
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
  
1.  Mit der rechten Maustaste die **AsynchronousCommunication** Projektmappe, und wählen **Eigenschaften**.  
  
2.  In **allgemeine Eigenschaften**Option **Startprojekt**, und wählen Sie **mehrere Startprojekte**.  
  
3.  Verschieben Sie **RentalApprovalService** an die erste Position in der Liste, gefolgt von **CreditCheckService**, gefolgt von **Client**. Legen Sie die **starten** Aktion für alle drei Projekte.  
  
4.  Klicken Sie auf **OK**, und drücken Sie F5, um das Beispiel auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
