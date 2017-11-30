---
title: Formatieren von Meldungen in Workflowdiensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d2367f4fe4ebe576eb9a5e2f707eb043e5ee7ccb
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="formatting-messages-in-workflow-services"></a>Formatieren von Meldungen in Workflowdiensten
In diesem Beispiel wird gezeigt, wie verschiedene Benutzertypen in Messagingaktivitäten (WF-Dienste) verwendet werden können. Der Beispieldienst ist ein einfacher Dienst zur Kostengenehmigung und macht drei Vorgänge verfügbar. `ApproveExpense` akzeptiert einen Datenvertragstyp und zeigt, wie bekannte Typen verwendet werden. Der Vorgang gibt `true` oder `false` auf Grundlage der Gesamtausgaben zurück. `ApprovePO`akzeptiert einen XmlSerializer-Typ und gibt `true` oder `false` Grundlage der Gesamtausgaben.`ApprovedVendor` akzeptiert einen Nachrichtenvertragstyp und gibt `true` oder `false` , wenn der Anbieter in der Liste der genehmigten Anbieter enthalten ist oder wenn die Anforderung von der Finanzabteilung stammt (die Finanzabteilung kann jeden Anbieter verwenden).  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.  
  
2.  Führen Sie zuerst den unter "[Projektmappenbasisverzeichnis]\FormatterService\bin\debug\" generierten Dienst aus.  
  
3.  Führen Sie als Nächstes die unter "[Projektmappenbasisverzeichnis]\FormatterClient\bin\debug" generierte Clientanwendung aus.  
  
4.  Der Client ruft drei Vorgänge für den Dienst auf und gibt die Ergebnisse aus. Drücken Sie nach dem Abschluss die EINGABETASTE, um den Client und dann der Dienst zu beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`