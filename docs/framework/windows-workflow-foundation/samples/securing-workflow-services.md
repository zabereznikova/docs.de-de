---
title: Sichern von Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
ms.openlocfilehash: 28c34ecf7d6d781bfa461b2737cb9325a657f47e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524334"
---
# <a name="securing-workflow-services"></a>Sichern von Workflowdiensten
Im Beispiel für einen gesicherten Workflowdienst werden die folgenden Verfahren veranschaulicht:  
  
-   Erstellen eines grundlegenden Workflowdiensts mit den Aktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply>.  
  
-   Verwenden Windows Communication Foundation (WCF)-Konfiguration, um sichere Endpunkte für die Verwendung durch den Workflowdienst zu definieren.  
  
-   Erstellen von Ansprüchen in einer benutzerdefinierten Richtlinie und Überprüfen von Ansprüchen mithilfe von <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Verwenden der WCF-Sicherheit, um die Kommunikation zwischen Client und Workflowdienst zu sichern, anspruchsbasierte Autorisierung.  
  
## <a name="discussion"></a>Diskussion  
 Dieses Beispiel veranschaulicht die Verwendung von WCF-Sicherheit-Infrastruktur zum Sichern eines Workflowdiensts, wie Sie mit einem normalen WCF-Dienst. Es wird ein benutzerdefinierter Anspruch zur Autorisierung verwendet. In diesem Fall werden <xref:System.ServiceModel.WSHttpBinding> und der Nachrichtensicherheitsmodus mit Windows-Anmeldeinformationen verwendet.  
  
 Das benutzerdefinierte <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Element (`CustomNameCheckerPolicy`) überprüft den Windows-Benutzernamen des Clients auf ein bestimmtes Zeichen. Wenn dieses Zeichen vorhanden ist, wird der Anspruch erstellt und <xref:System.IdentityModel.Policy.EvaluationContext> hinzugefügt. Dadurch erklärt die benutzerdefinierte Richtlinie, dass der Client dieses Zeichen im Benutzernamen aufweist. Dieser Anspruch kann während der gesamten Lebensdauer des Aufrufs abgefragt werden. Sie können dieses Zeichen in `Constants.cs` finden.  
  
 Die Autorisierungsrichtlinie sucht in `SecureWorkFlowAuthZManager` nach dem Anspruch. Wird er gefunden, wird `true` zurückgegeben, und der Workflow kann den Vorgang fortsetzen. Andernfalls wird `false` zurückgegeben. Dadurch wird die Meldung "Zugriff verweigert" an den Client zurückgegeben. Andere Ansprüche sind im Kontext vorhanden und können auch in `SecureWorkFlowAuthZManager` untersucht werden.  
  
#### <a name="to-run-this-sample"></a>So führen Sie dieses Beispiel aus  
  
1.  Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit Administratorrechten aus.  
  
2.  Laden Sie "SecuringWorkflowServices.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu kompilieren.  
  
4.  Legen Sie das Service-Projekt als Startprojekt für die Projektmappe fest.  
  
5.  Drücken Sie STRG+F5, um den Dienst ohne Debugging zu starten.  
  
6.  Legen Sie das Client-Projekt als Startprojekt für die Projektmappe fest.  
  
7.  Drücken Sie STRG+F5, um den Client ohne Debugging zu starten.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
