---
title: Grundlegende Verwendung der Aktivitäten SendParameters und ReceiveParameters
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: 8732b10f3f96ccf9ed352f9b54c60a4ee0d1664c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515397"
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a>Grundlegende Verwendung der Aktivitäten SendParameters und ReceiveParameters
Anhand dieses Beispiels wird die Verwendung der <xref:System.ServiceModel.Activities.SendParametersContent>-Aktivität und der <xref:System.ServiceModel.Activities.ReceiveParametersContent>-Aktivität veranschaulicht. Der Dienst macht einen Vorgang verfügbar, der ein Zeichenfolgenargument verwendet, und gibt die Eingabe in einem Echo-Vorgang an den Client zurück. Im Beispiel wird gezeigt, wie die Parameter für diese Messagingaktivitäten eingerichtet werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a>Verwenden dieses Beispiels  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie zunächst die unter "[Projektmappenbasisverzeichnis]\EchoWorkflowService\bin\debug" generierte EchoWorkflowService-Anwendung aus.  
  
3.  Führen Sie als Nächstes die unter "[Projektmappenbasisverzeichnis]\EchoWorkflowClient\bin\debug" generierte EchoWorkflowClient-Anwendung aus.  
  
4.  Der Client ruft den Echo-Vorgang für den Dienst auf und gibt die Ergebnisse aus. Drücken Sie nach dem Abschluss die EINGABETASTE, um den Client und dann der Dienst zu beenden.