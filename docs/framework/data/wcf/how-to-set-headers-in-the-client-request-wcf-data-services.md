---
title: 'Vorgehensweise: Festlegen von Headern in der Client Anforderung (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: 5a72b349526d5cbba229cba627c23b1b1b889678
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943930"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>Vorgehensweise: Festlegen von Headern in der Client Anforderung (WCF Data Services)
Wenn Sie mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek auf einen Datendienst zugreifen, der das [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] unterstützt, legt die Clientbibliothek die erforderlichen HTTP-Header in Anforderungsnachrichten an den Datendienst automatisch fest. Die Clientbibliothek ist jedoch nicht in der Lage, Nachrichtenheader festzulegen, die in bestimmten Fällen erforderlich sind, z. B. wenn der Datendienst die anspruchsbasierte Authentifizierung oder Cookies erfordert. Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication). In diesen Fällen müssen Sie Nachrichtenheader in der Anforderungsnachricht vor dem Senden manuell festlegen. Das Beispiel in diesem Thema zeigt, wie das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis behandelt wird, um der Anforderungsnachricht einen neuen Header hinzuzufügen, bevor sie an den Datendienst gesendet wird.  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)ausführen. Sie können auch den [Northwind-Beispiel Datendienst](https://go.microsoft.com/fwlink/?LinkId=187426) verwenden, der auf der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Website veröffentlicht wird. dieser Beispiel Datendienst ist schreibgeschützt, und der Versuch, Änderungen zu speichern, gibt einen Fehler zurück. Die Beispiel Datendienste auf der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Website ermöglichen die anonyme Authentifizierung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Handler für das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis registriert und anschließend eine Abfrage für den Datendienst ausgeführt.  
  
> [!NOTE]
> Wenn Sie bei einem Datendienst den Nachrichtenheader für jede Anforderung manuell festlegen müssen, ist es u. U. sinnvoll, den Handler für das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis durch Überschreiben der partiellen `OnContextCreated`-Methode im Entitätscontainer, der den Datendienst darstellt (in diesem Fall `NorthwindEntities`), zu registrieren.  
  
[!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#registerheadersquery)]   
[!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#registerheadersquery)]
  
## <a name="example"></a>Beispiel  
 Die folgende Methode behandelt das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis und fügt der Anforderung einen Authentifizierungsheader hinzu.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#onsendingrequest)]  
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#onsendingrequest)]  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
