---
title: Asynchrone Vorgänge (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: 01212b859e10ec1bbbb452486ce1aa6a2cecb583
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965826"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Asynchrone Vorgänge (WCF Data Services)
Bei Webanwendungen muss die gegenüber Anwendungen, die in internen Netzwerken ausgeführt werden, höhere Latenz zwischen Client und Server berücksichtigt werden. Um die Leistung und das vom Benutzer wahrgenommene Verhalten der Anwendung zu optimieren, empfiehlt es sich, die asynchronen Methoden der <xref:System.Data.Services.Client.DataServiceContext>-Klasse und der <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse zu verwenden, wenn über das Internet auf [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Server zugegriffen wird.  
  
 Obwohl die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Server HTTP-Anforderungen asynchron verarbeiten, sind einige Methoden der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Clientbibliotheken synchron und warten, bis der gesamte Anforderung/Antwort-Austausch abgeschlossen wurde, bevor die Ausführung fortgesetzt wird. Die asynchronen Methoden der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliotheken warten nicht, bis dieser Austausch abgeschlossen wurde. Sie können es der Anwendung ermöglichen, während dieses Austauschs eine reagierende Benutzeroberfläche beizubehalten.  
  
 Sie können asynchrone Vorgänge ausführen, indem Sie ein Methoden Paar für die <xref:System.Data.Services.Client.DataServiceContext> - <xref:System.Data.Services.Client.DataServiceQuery%601> Klasse und die-Klasse verwenden, die mit *Begin* bzw. *End* beginnen. Die *Begin* -Methoden registrieren einen Delegaten, den der Dienst aufruft, wenn der Vorgang beendet ist. Die *End* -Methoden sollten im Delegaten aufgerufen werden, der zum Behandeln des Rückrufs von den abgeschlossenen Vorgängen registriert ist. Wenn Sie die *End* -Methode zum Ausführen eines asynchronen Vorgangs aufgerufen haben, müssen Sie dies über die <xref:System.Data.Services.Client.DataServiceQuery%601> gleiche <xref:System.Data.Services.Client.DataServiceContext> -oder-Instanz tun, die Sie zum Starten des Vorgangs verwendet haben. Jede *Begin* -Methode nimmt `state` einen Parameter an, der ein Zustands Objekt an den Rückruf übergeben kann. Dieses Zustands Objekt wird aus dem <xref:System.IAsyncResult> abgerufen, das mit dem Rückruf angegeben wird, und wird verwendet, um die entsprechende *End* -Methode aufzurufen, um den asynchronen Vorgang abzuschließen. Wenn Sie beispielsweise die <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz als `state`-Parameter beim Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode für die Instanz angeben, wird die gleiche <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz vom <xref:System.IAsyncResult> zurückgegeben. Diese Instanz von <xref:System.Data.Services.Client.DataServiceQuery%601> wird anschließend verwendet, um die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode zum Abschließen des Abfragevorgangs aufzurufen. Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von asynchronen Datendienst](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md)Abfragen.  
  
> [!NOTE]
> Nur asynchrone Vorgänge werden von den Clientbibliotheken unterstützt, die in .NET Framework für Silverlight bereitgestellt werden. Weitere Informationen finden Sie unter [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149).  
  
 Die .NET Framework-Clientbibliotheken unterstützen die folgenden asynchronen Vorgänge:  
  
|Vorgang|Methoden|  
|---------------|-------------|  
|Ausführen einer <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Ausführen einer Abfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Ausführen einer Batchabfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Laden einer verknüpften Entität in den <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Speichern von Änderungen an Objekten im <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Überlegungen zum Threading für asynchrone Vorgänge  
 In einer Multithreadanwendung wird der Delegat, der als Rückruf für den asynchronen Vorgang registriert ist, nicht notwendigerweise in demselben Thread aufgerufen, der zum Aufrufen der *Begin* -Methode verwendet wurde, die die ursprüngliche Anforderung erstellt. In einer Anwendung, in der der Rückruf für einen bestimmten Thread aufgerufen werden muss, müssen Sie die Ausführung der *End* -Methode, die die Antwort verarbeitet, explizit an den gewünschten Thread Mars Hallen. In WPF (Windows Presentation Foundation)-basierten Anwendungen und Silverlight-basierten Anwendungen muss z. B. das Marshalling der Antwort zurück zum Benutzeroberflächenthread mit der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>-Methode für das <xref:System.Windows.Threading.Dispatcher>-Objekt durchgeführt werden. Weitere Informationen finden Sie unter [Abfragen des Daten Dienstanbieter (WCF Data Services/Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc903932(v=vs.95)).  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
