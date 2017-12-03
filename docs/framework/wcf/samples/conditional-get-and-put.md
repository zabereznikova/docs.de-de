---
title: Bedingtes GET und PUT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59a9f0638855206f390ee7fbace580ba37e25e23
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="conditional-get-and-put"></a>Bedingtes GET und PUT
In diesem Beispiel wird veranschaulicht, wie die neuen bedingten Abruf- und Aktualisierungs-APIs für das WCF REST-Programmiermodell verwendet werden. Da bedingtes abrufen und aktualisieren für am besten geeignet sind Ressource orientierten und REST-Dienste, die in diesem Beispiel erweitert die [grundlegenden Ressourcendiensts](../../../../docs/framework/wcf/samples/basic-resource-service.md) Beispiel. Dieses Beispiel befasst sich das Hinzufügen der Unterstützung für bedingten Abruf- und aktualisieren Sie auf die [grundlegenden Ressourcendiensts](../../../../docs/framework/wcf/samples/basic-resource-service.md) -Beispiels mit der neuen APIs in eingeführte [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Bedingtes Abrufen und Aktualisieren  
  
## <a name="discussion"></a>Diskussion  
 Der WCF-Dienst in diesem Beispiel macht eine Auflistung der Kunden auf ressourcenorientierte und REST-Weise verfügbar. Eine ausführliche Beschreibung der dienstimplementierung, finden Sie unter der [grundlegenden Ressourcendiensts](../../../../docs/framework/wcf/samples/basic-resource-service.md) Beispiel.  
  
 Dieses Beispiel fügt die bedingten Abruf- und Aktualisierungsfunktionen auf die [grundlegenden Ressourcendiensts](../../../../docs/framework/wcf/samples/basic-resource-service.md) Beispiel. Die bedingten Abruf- und Aktualisierungsfunktionen überprüfen mithilfe der HTTP-Entitätstags und der HTTP-Header If-None-Match und If-Match, dass Clients entweder über die aktuellste Entität für eine angegebene Ressource verfügen oder nicht. Die Implementierung des Codes zum ordnungsgemäßen Analysieren der HTTP-Header If-None-Match und If-Match kann sich jedoch als mühsam und fehleranfällig erweisen. Aus diesem Grund wurden die Methoden <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> und <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> zu <xref:System.ServiceModel.Web.IncomingWebRequestContext> hinzugefügt, auf die über die aktuelle <xref:System.ServiceModel.Web.WebOperationContext>-Instanz zugegriffen werden kann. Darüber hinaus wurde die `SetETag`-Methode zu <xref:System.ServiceModel.Web.OutgoingWebRequestContext> hinzugefügt, sodass es einfacher ist, gültige Entitätstags zurückzugeben.  
  
 Die <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode ist für die Verwendung mit [WebGet]-Vorgängen bestimmt. Das aktuelle Entitätstag wird für die angegebene Ressource als `entityTag`-Parameter verwendet. Dabei kann es sich um `string`, `int`, `long` oder `Guid` handeln. Die <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode vergleicht das Entitätstag mit dem HTTP-Header If-None-Match der Anforderung. Wenn das Entitätstag im HTTP-Header If-None-Match vorhanden ist, wird eine <xref:System.ServiceModel.Web.WebFaultException> mit dem Statuscode 304 (Nicht geändert) ausgelöst; andernfalls gibt die Methode einen Wert zurück. Der bedingte Abrufmechanismus ermöglicht es dem Client, dem Server mitzuteilen, dass er über diese Entität verfügt, und dass die aktuelle Entität nur gesendet werden soll, wenn sie der Client nicht bereits hat. Beispiele für die Nutzung der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode sind in den Vorgängen `GetCustomer` und `GetCustomers` des Diensts zu finden. Wichtig: Aufrufe der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode geben möglicherweise keinen Wert zurück. Entwickler sollten den Vorgang so implementieren, dass die Anforderung bereits vor dem Aufruf von <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> als erfolgreich angesehen wird, damit der Dienst eine Antwort mit erfolgreichem Statuscode senden würde, auch wenn der Aufruf von <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> nicht vorhanden wäre.  
  
 Die <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>-Methode ähnelt der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode. Sie verwendet auch das aktuelle Entitätstag für die angegebene Ressource. Es soll jedoch mit [WebInvoke]-Vorgängen verwendet werden, in dem die Methode auf "PUT" oder "DELETE" festgelegt ist. Die <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>-Methode vergleicht das Entitätstag mit dem HTTP-Header If-Match der Anforderung. Wenn das Entitätstag im HTTP-Header If-Match nicht vorhanden ist, wird eine <xref:System.ServiceModel.Web.WebFaultException> mit dem Statuscode 412 (Vorbedingungsfehler) ausgelöst. Der bedingte Aktualisierungsmechanismus ermöglicht es dem Client, dem Server mitzuteilen, dass er über diese Entität für die Ressource verfügt und dass nur er die Ressource ändern kann, vorausgesetzt dass er über die aktuelle Entität verfügt. Beispiele für die Nutzung der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>-Methode sind in den Vorgängen `UpdateCustomer` und `DeleteCustomer` des Diensts zu finden. Wie bei der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode sollte auch hier beachtet werden, dass Aufrufe der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>-Methode möglicherweise keinen Wert zurückgeben. Entwickler sollten den Vorgang so implementieren, dass die Anforderung bereits vor dem Aufruf von <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> als erfolgreich angesehen wird, damit der Dienst eine Antwort mit erfolgreichem Statuscode senden würde, auch wenn der Aufruf von <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> nicht vorhanden wäre.  
  
 Das Beispiel umfasst einen selbst gehosteten Dienst und einen Client, der in einer Konsolenanwendung ausgeführt wird. Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe für das bedingte Get- und Put-Beispiel. Sie müssen [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] als Administrator ausführen, damit das Beispiel erfolgreich ausgeführt werden kann. Zu diesem Zweck mit der rechten Maustaste die [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Symbol und Auswahl **als Administrator ausführen** aus dem Kontextmenü.  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen, und dann STRG+F5, um das Konsolenanwendungsprojekt auszuführen. Wenn bei der Ausführung dieses Projekts Debuggen aktiviert ist, (durch Drücken von F5 statt STRG+F5), wird der Debugger beendet, wenn durch die bedingte GET und PUT-Überprüfung eine Ausnahme ausgelöst wird. Drücken Sie in dem Fall F5, um mit der Ausführung des Beispiels fortzufahren.  
  
3.  Im eingeblendeten Konsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt.  
  
4.  Während das Beispiel ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die Antworten in das Konsolenfenster.  
  
5.  Drücken Sie eine beliebige Taste, um das Beispiel zu beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`
