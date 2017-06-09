---
title: "Vorgehensweise: Festlegen von Headern in der Clientanforderung (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Anpassen von Anforderungen"
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Vorgehensweise: Festlegen von Headern in der Clientanforderung (WCF Data Services)
Wenn Sie mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliothek auf einen Datendienst zugreifen, der das [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] unterstützt, legt die Clientbibliothek die erforderlichen HTTP\-Header in Anforderungsnachrichten an den Datendienst automatisch fest.  Die Clientbibliothek ist jedoch nicht in der Lage, Nachrichtenheader festzulegen, die in bestimmten Fällen erforderlich sind, z. B. wenn der Datendienst die anspruchsbasierte Authentifizierung oder Cookies erfordert.  Weitere Informationen finden Sie unter [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication).  In diesen Fällen müssen Sie Nachrichtenheader in der Anforderungsnachricht vor dem Senden manuell festlegen.  Das Beispiel in diesem Thema zeigt, wie das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>\-Ereignis behandelt wird, um der Anforderungsnachricht einen neuen Header hinzuzufügen, bevor sie an den Datendienst gesendet wird.  
  
 Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  Sie können auch den öffentlichen [Northwind\-Beispieldatendienst](http://go.microsoft.com/fwlink/?LinkId=187426) auf der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Website verwenden. Dieser Beispieldatendienst ist schreibgeschützt. Wenn Sie versuchen, Änderungen zu speichern, wird ein Fehler zurückgegeben.  Die Beispieldatendienste auf der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Website lassen die anonyme Authentifizierung zu.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Handler für das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>\-Ereignis registriert und anschließend eine Abfrage für den Datendienst ausgeführt.  
  
> [!NOTE]
>  Wenn Sie bei einem Datendienst den Nachrichtenheader für jede Anforderung manuell festlegen müssen, ist es u. U. sinnvoll, den Handler für das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>\-Ereignis durch Überschreiben der partiellen `OnContextCreated`\-Methode im Entitätscontainer, der den Datendienst darstellt \(in diesem Fall `NorthwindEntities`\), zu registrieren.  
  
 [!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#registerheadersquery)]
 [!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#registerheadersquery)]  
  
## Beispiel  
 Die folgende Methode behandelt das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>\-Ereignis und fügt der Anforderung einen Authentifizierungsheader hinzu.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onsendingrequest)]
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onsendingrequest)]  
  
## Siehe auch  
 [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)   
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)