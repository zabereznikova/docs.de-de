---
title: "WCF-Fehlerbehandlung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# WCF-Fehlerbehandlung
Die bei einer WCF\-Anwendung aufgetretenen Fehler gehören zu einer von drei Gruppen:  
  
1.  Kommunikationsfehler  
  
2.  Proxy\-\/Channelfehler  
  
3.  Anwendungsfehler  
  
 Kommunikationsfehler treten auf, wenn ein Netzwerk nicht verfügbar ist, ein Client eine falsche Adresse verwendet oder der Diensthost keine eingehende Nachrichten überwacht.An den Client werden Fehler dieses Typs als <xref:System.ServiceModel.CommunicationException>\-Klasse oder abgeleitete <xref:System.ServiceModel.CommunicationException>\-Klasse zurückgegeben.  
  
 Proxy\-\/Channelfehler sind Fehler, die innerhalb des Channels oder des Proxys selbst auftreten.Fehler dieses Typs sind unter anderem: Versuche, einen Proxy oder Channel zu verwenden, der geschlossen wurde, ein Vertragskonflikt zwischen Client und Dienst oder die Ablehnung der Anmeldeinformationen des Clients durch den Dienst.Es gibt viele andere Fehlertypen in dieser Kategorie, die hier nicht alle aufgeführt werden können.An den Client werden Fehler dieses Typs unverändert zurückgegeben \(es wird keine Transformation für die Ausnahmeobjekte ausgeführt\).  
  
 Anwendungsfehler treten während der Ausführung eines Dienstvorgangs auf.Fehler dieser Art werden an den Client als <xref:System.ServiceModel.FaultException> oder <xref:System.ServiceModel.FaultException%601> gesendet.  
  
 Die Fehlerbehandlung in WCF wird durch einen oder mehrere der folgenden Schritte ausgeführt:  
  
-   Direkte Behandlung der ausgelösten Ausnahme.Dies erfolgt nur für Kommunikations\- und Proxy\-\/Channelfehler.  
  
-   Verwenden von Fehlerverträgen  
  
-   Implementieren der <xref:System.ServiceModel.Dispatcher.IErrorHandler>\-Schnittstelle  
  
-   Behandlung von <xref:System.ServiceModel.ServiceHost>\-Ereignissen  
  
## Fehlerverträge  
 Mithilfe von Fehlerverträgen können Sie die Fehler, die während eines Dienstvorgangs auftreten können, auf plattformunabhängige Weise definieren.Standardmäßig werden alle innerhalb eines Dienstvorgangs ausgelösten Ausnahmen an den Client als <xref:System.ServiceModel.FaultException>\-Objekt zurückgegeben.Das <xref:System.ServiceModel.FaultException>\-Objekt enthält sehr wenig Informationen.Sie können die an den Client gesendeten Informationen durch Definieren eines Fehlervertrags und Zurückgeben des Fehlers als <xref:System.ServiceModel.FaultException%601> steuern.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## IErrorHandler  
 Die <xref:System.ServiceModel.Dispatcher.IErrorHandler>\-Schnittstelle ermöglicht Ihnen mehr Kontrolle darüber, wie die WCF\-Anwendung auf Fehler reagiert.Sie gibt Ihnen volle Kontrolle über die Fehlermeldung, die an den Client zurückgegeben wird, und ermöglicht Ihnen, die benutzerdefinierte Fehlerverarbeitung auszuführen, z. B. die Protokollierung.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Dispatcher.IErrorHandler> und [Erweitern der Kontrolle über Fehlerbehandlung und \-meldung](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)  
  
## ServiceHost\-Ereignisse  
 Die <xref:System.ServiceModel.ServiceHost>\-Klasse hostet Dienste und definiert mehrere Ereignisse, die möglicherweise zur Fehlerbehandlung benötigt werden.Beispiel:  
  
1.  <xref:System.ServiceModel.ServiceHost.Faulted>  
  
2.  <xref:System.ServiceModel.ServiceHost.UnknownMessageReceived>  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] <xref:System.ServiceModel.ServiceHost>