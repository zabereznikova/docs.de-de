---
title: 'Vorgehensweise: Festlegen von Headern in der Clientanforderung (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
ms.openlocfilehash: 9267f0e5b68823516764891a40e1435c1325b77f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174341"
---
# <a name="how-to-set-headers-in-the-client-request-wcf-data-services"></a>Vorgehensweise: Festlegen von Headern in der Clientanforderung (WCF Data Services)
Wenn Sie die WCF Data Services-Clientbibliothek für den Zugriff auf einen Datendienst verwenden, der das Open Data Protocol (OData) unterstützt, legt die Clientbibliothek automatisch die erforderlichen HTTP-Header in Anforderungsnachrichten fest, die an den Datendienst gesendet werden. Die Clientbibliothek ist jedoch nicht in der Lage, Nachrichtenheader festzulegen, die in bestimmten Fällen erforderlich sind, z. B. wenn der Datendienst die anspruchsbasierte Authentifizierung oder Cookies erfordert. Weitere Informationen finden Sie unter [Securing WCF Data Services](securing-wcf-data-services.md#clientAuthentication). In diesen Fällen müssen Sie Nachrichtenheader in der Anforderungsnachricht vor dem Senden manuell festlegen. Das Beispiel in diesem Thema zeigt, wie das <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>-Ereignis behandelt wird, um der Anforderungsnachricht einen neuen Header hinzuzufügen, bevor sie an den Datendienst gesendet wird.  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services-Schnellstart](quickstart-wcf-data-services.md)abschließen. Sie können auch den [Northwind-Beispieldatendienst](https://services.odata.org/Northwind/Northwind.svc/) verwenden, der auf der OData-Website veröffentlicht wird. Dieser Beispieldatendienst ist schreibgeschützt, und der Versuch, Änderungen zu speichern, gibt einen Fehler zurück. Die Beispieldatendienste auf der OData-Website ermöglichen eine anonyme Authentifizierung.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Sichern von WCF Data Services](securing-wcf-data-services.md)
- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
