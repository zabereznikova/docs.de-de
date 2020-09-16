---
title: Asynchrone Vorgänge (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: d1f45979dba5c3ab0dccc8d0a61a7abaa9913e11
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556862"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Asynchrone Vorgänge (WCF Data Services)
Bei Webanwendungen muss die gegenüber Anwendungen, die in internen Netzwerken ausgeführt werden, höhere Latenz zwischen Client und Server berücksichtigt werden. Um die Leistung und die Benutzer Leistung Ihrer Anwendung zu optimieren, wird empfohlen, die asynchronen Methoden der <xref:System.Data.Services.Client.DataServiceContext> -Klasse und der-Klasse zu verwenden, <xref:System.Data.Services.Client.DataServiceQuery%601> Wenn auf WCF Data Services-Server über das Internet zugegriffen wird.  
  
 Obwohl die WCF Data Services Server HTTP-Anforderungen asynchron verarbeiten, sind einige Methoden der WCF Data Services Client Bibliotheken synchron und warten, bis der gesamte Anforderungs Antwort-Austausch abgeschlossen ist, bevor die Ausführung fortgesetzt wird. Die asynchronen Methoden der WCF Data Services Client Bibliotheken warten nicht auf den Abschluss dieses Austauschs und können der Anwendung in der Zwischenzeit eine reaktionsfähige Benutzeroberfläche ermöglichen.  
  
 Sie können asynchrone Vorgänge ausführen, indem Sie ein Methoden Paar für die <xref:System.Data.Services.Client.DataServiceContext> -Klasse und die- <xref:System.Data.Services.Client.DataServiceQuery%601> Klasse verwenden, die mit *Begin* bzw. *End* beginnen. Die *Begin* -Methoden registrieren einen Delegaten, den der Dienst aufruft, wenn der Vorgang beendet ist. Die *End* -Methoden sollten im Delegaten aufgerufen werden, der zum Behandeln des Rückrufs von den abgeschlossenen Vorgängen registriert ist. Wenn Sie die *End* -Methode zum Ausführen eines asynchronen Vorgangs aufgerufen haben, müssen Sie dies über die gleiche-oder-Instanz tun, die <xref:System.Data.Services.Client.DataServiceQuery%601> <xref:System.Data.Services.Client.DataServiceContext> Sie zum Starten des Vorgangs verwendet haben. Jede *Begin* -Methode nimmt einen `state` Parameter an, der ein Zustands Objekt an den Rückruf übergeben kann. Dieses Zustands Objekt wird aus dem abgerufen <xref:System.IAsyncResult> , das mit dem Rückruf angegeben wird, und wird verwendet, um die entsprechende *End* -Methode aufzurufen, um den asynchronen Vorgang abzuschließen. Wenn Sie beispielsweise die <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz als `state`-Parameter beim Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode für die Instanz angeben, wird die gleiche <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz vom <xref:System.IAsyncResult> zurückgegeben. Diese Instanz von <xref:System.Data.Services.Client.DataServiceQuery%601> wird anschließend verwendet, um die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode zum Abschließen des Abfragevorgangs aufzurufen. Weitere Informationen finden Sie unter Gewusst [wie: Ausführen von asynchronen Datendienst Abfragen](how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
> Nur asynchrone Vorgänge werden von den Clientbibliotheken unterstützt, die in .NET Framework für Silverlight bereitgestellt werden. Weitere Informationen finden Sie unter [WCF Data Services (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 Die .NET Framework-Clientbibliotheken unterstützen die folgenden asynchronen Vorgänge:  
  
|Vorgang|Methoden|  
|---------------|-------------|  
|Ausführen einer <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Ausführen einer Abfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Ausführen einer Batchabfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Laden einer verknüpften Entität in den <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Speichern von Änderungen an Objekten im <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Überlegungen zum Threading für asynchrone Vorgänge  
 In einer Multithreadanwendung wird der Delegat, der als Rückruf für den asynchronen Vorgang registriert ist, nicht notwendigerweise in demselben Thread aufgerufen, der zum Aufrufen der *Begin* -Methode verwendet wurde, die die ursprüngliche Anforderung erstellt. In einer Anwendung, in der der Rückruf für einen bestimmten Thread aufgerufen werden muss, müssen Sie die Ausführung der *End* -Methode, die die Antwort verarbeitet, explizit an den gewünschten Thread Mars Hallen. In WPF (Windows Presentation Foundation)-basierten Anwendungen und Silverlight-basierten Anwendungen muss z. B. das Marshalling der Antwort zurück zum Benutzeroberflächenthread mit der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>-Methode für das <xref:System.Windows.Threading.Dispatcher>-Objekt durchgeführt werden. Weitere Informationen finden Sie unter [Abfragen des Daten Dienstanbieter (WCF Data Services/Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc903932(v=vs.95)).  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
