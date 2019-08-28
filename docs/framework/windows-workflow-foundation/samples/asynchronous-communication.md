---
title: Asynchrone Kommunikation
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: b5cf788ce4587dacb5a7642e25cb1b5b1e6f3e3c
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044368"
---
# <a name="asynchronous-communication"></a>Asynchrone Kommunikation
In diesem Beispiel wird veranschaulicht, wie die Kommunikation zwischen zwei unterschiedlichen WF-Diensten (Windows Workflow Foundation) standardmäßig asynchron erfolgt.  
  
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
  
1. Klicken Sie mit der rechten Maustaste auf die Lösung **asynchronouscommunication** , und wählen Sie **Eigenschaften**.  
  
2. Wählen Sie unter **Allgemeine Eigenschaften**die Option **Startprojekt**aus, und wählen Sie **mehrere Start Projekte**aus.  
  
3. Verschieben Sie **rentalapprovalservice** an die erste Position in der Liste, gefolgt von **creditcheckservice**, gefolgt vom **Client**. Legen Sie die **Start** Aktion für alle drei Projekte fest.  
  
4. Klicken Sie auf **OK**, und drücken Sie F5, um das Beispiel auszuführen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
