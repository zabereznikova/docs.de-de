---
title: "Asynchrone Kommunikation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Asynchrone Kommunikation
Anhand dieses Beispiels wird veranschaulicht, wie die Kommunikation zwischen zwei verschiedenen [!INCLUDE[wf](../../../../includes/wf-md.md)]\-Diensten standardmäßig asynchron erfolgt.  
  
## Veranschaulicht  
 Asynchrone Kommunikation zwischen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Diensten.  
  
## Diskussion  
 Dieses Beispiel zeigt, wie die Kommunikation zwischen [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Anwendungen mithilfe der von .NET Framework bereitgestellten Messagingaktivitäten asynchron erfolgt.  
  
 Dieses Beispiel besteht aus den folgenden drei Projekten.  
  
 CreditCheckService  
 Dieser Dienst empfängt den Kreditscore \(die Kreditwürdigkeit\) einer bestimmten Person oder den Wert des zu erwerbenden Elements und legt dann fest, ob der Person der Kredit gewährt wird.  
  
 RentalApprovalService  
 Dieser Dienst empfängt eine Anwendung von einer Person, die einen Kredit benötigt.Dieser Dienst kommuniziert asynchron mit dem `CreditCheckService`\-Dienst, um zu bestimmen, ob die Kreditanwendung gültig ist.  
  
 Client  
 Der Client kommuniziert synchron mit dem `RentalApprovalService`\-Dienst, um zu ermitteln, ob der Kredit genehmigt wird.  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Klicken Sie mit der rechten Maustaste auf die Projektmappe **AsynchronousCommunication**, und wählen Sie **Eigenschaften**.  
  
2.  Wählen Sie unter **Allgemeine Eigenschaften** die Option **Startprojekt** und dann **Mehrere Startprojekte** aus.  
  
3.  Verschieben Sie **RentalApprovalService** an die erste Position in der Liste, gefolgt von **CreditCheckService** und **Client**.Legen Sie die **Start**\-Aktion für alle drei Projekte fest.  
  
4.  Klicken Sie auf **OK**, und drücken Sie F5, um das Beispiel auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`