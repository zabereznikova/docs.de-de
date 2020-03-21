---
title: Asynchrone Kommunikation
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: e1bc63b5d3178b8e98350dedd8eb0791e0e35589
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142875"
---
# <a name="asynchronous-communication"></a>Asynchrone Kommunikation
In diesem Beispiel wird veranschaulicht, wie die Kommunikation zwischen zwei verschiedenen Windows Workflow Foundation (WF)-Diensten standardmäßig asynchron erfolgt.  
  
## <a name="demonstrates"></a>Zeigt  
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
  
1. Klicken Sie mit der rechten Maustaste auf die **AsynchronousCommunication-Lösung,** und wählen Sie **Eigenschaften**aus.  
  
2. Wählen Sie unter **Allgemeine Eigenschaften**die Option **Projekt starten**aus, und wählen Sie **Mehrere Startprojekte**aus.  
  
3. Verschieben Sie **RentalApprovalService** auf die erste Position in der Liste, gefolgt von **CreditCheckService**, gefolgt von **Client**. Legen Sie die **Startaktion** für alle drei Projekte fest.  
  
4. Klicken Sie auf **OK**, und drücken Sie F5, um das Beispiel auszuführen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
