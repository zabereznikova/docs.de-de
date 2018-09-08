---
title: Formatieren von Meldungen in Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
ms.openlocfilehash: eb9a6b3a83a28154dc968bd4c1c41d34028bdd41
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198971"
---
# <a name="formatting-messages-in-workflow-services"></a>Formatieren von Meldungen in Workflowdiensten
In diesem Beispiel wird gezeigt, wie verschiedene Benutzertypen in Messagingaktivitäten (WF-Dienste) verwendet werden können. Der Beispieldienst ist ein einfacher Dienst zur Kostengenehmigung und macht drei Vorgänge verfügbar. `ApproveExpense` akzeptiert einen Datenvertragstyp und zeigt, wie bekannte Typen verwendet werden. Der Vorgang gibt `true` oder `false` auf Grundlage der Gesamtausgaben zurück. `ApprovePO` akzeptiert einen XmlSerializer-Typ und gibt zurück `true` oder `false` basierend auf den Ausgabenbetrag.`ApprovedVendor` akzeptiert einen Nachrichtenvertragstyp und gibt zurück `true` oder `false` , wenn der Anbieter in der Liste der genehmigten Anbieter enthalten ist, oder wenn die Anforderung von der Finanzabteilung stammt (die Finanzabteilung kann jeden Anbieter verwenden).  
  
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`