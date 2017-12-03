---
title: Sichern von Workflowdiensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cd7620186ed51110a32e251d5239c85bb90e0f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="securing-workflow-services"></a>Sichern von Workflowdiensten
Im Beispiel für einen gesicherten Workflowdienst werden die folgenden Verfahren veranschaulicht:  
  
-   Erstellen eines grundlegenden Workflowdiensts mit den Aktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply>.  
  
-   Verwenden der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Konfiguration, um sichere Endpunkte für den Workflowdienst zu definieren.  
  
-   Erstellen von Ansprüchen in einer benutzerdefinierten Richtlinie und Überprüfen von Ansprüchen mithilfe von <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Verwenden der WCF-Sicherheit, um die Kommunikation zwischen Client und Workflowdienst zu sichern, anspruchsbasierte Autorisierung.  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird die Verwendung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sicherheitsinfrastruktur veranschaulicht, um einen Workflowdienst wie einen normalen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zu sichern. Es wird ein benutzerdefinierter Anspruch zur Autorisierung verwendet. In diesem Fall werden <xref:System.ServiceModel.WSHttpBinding> und der Nachrichtensicherheitsmodus mit Windows-Anmeldeinformationen verwendet.  
  
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
