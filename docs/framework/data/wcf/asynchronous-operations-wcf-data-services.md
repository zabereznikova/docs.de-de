---
title: Asynchrone Vorgänge (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: 665e424ada24e5e2990eccde7193a91dc039b265
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43407471"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Asynchrone Vorgänge (WCF Data Services)
Bei Webanwendungen muss die gegenüber Anwendungen, die in internen Netzwerken ausgeführt werden, höhere Latenz zwischen Client und Server berücksichtigt werden. Um die Leistung und das vom Benutzer wahrgenommene Verhalten der Anwendung zu optimieren, empfiehlt es sich, die asynchronen Methoden der <xref:System.Data.Services.Client.DataServiceContext>-Klasse und der <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse zu verwenden, wenn über das Internet auf [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Server zugegriffen wird.  
  
 Obwohl die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Server HTTP-Anforderungen asynchron verarbeiten, sind einige Methoden der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliotheken synchron und warten, bis der gesamte Anforderung/Antwort-Austausch abgeschlossen wurde, bevor die Ausführung fortgesetzt wird. Die asynchronen Methoden der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliotheken warten nicht, bis dieser Austausch abgeschlossen wurde. Sie können es der Anwendung ermöglichen, während dieses Austauschs eine reagierende Benutzeroberfläche beizubehalten.  
  
 Sie können asynchrone Vorgänge ausführen, indem Sie mit einem Paar von Methoden für die <xref:System.Data.Services.Client.DataServiceContext> und <xref:System.Data.Services.Client.DataServiceQuery%601> Klassen, die mit beginnen *beginnen* und *End* bzw. Die *beginnen* -Methoden registrieren einen Delegaten, der den Dienst aufruft, wenn der Vorgang abgeschlossen ist. Die *End* Methoden aufgerufen werden soll, in der Delegat, der zum Behandeln des Rückrufs von den abgeschlossenen Vorgängen registriert ist. Beim Aufrufen der *End* Methode, um einen asynchronen Vorgang abzuschließen müssen Sie diesen aus der gleichen <xref:System.Data.Services.Client.DataServiceQuery%601> oder <xref:System.Data.Services.Client.DataServiceContext> Instanz, mit denen Sie den Vorgang zu starten. Jede *beginnen* -Methode übernimmt eine `state` Parameter, der ein Zustandsobjekt an den Rückruf übergeben kann. Dieses Zustandsobjekt wird abgerufen, von der <xref:System.IAsyncResult> , die mit dem Rückruf angegeben wird, und dient zum Aufrufen der entsprechenden *End* Methode, um den asynchronen Vorgang abzuschließen. Wenn Sie beispielsweise die <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz als `state`-Parameter beim Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode für die Instanz angeben, wird die gleiche <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz vom <xref:System.IAsyncResult> zurückgegeben. Diese Instanz von <xref:System.Data.Services.Client.DataServiceQuery%601> wird anschließend verwendet, um die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode zum Abschließen des Abfragevorgangs aufzurufen. Weitere Informationen finden Sie unter [wie: Ausführen des asynchronen Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
>  Nur asynchrone Vorgänge werden von den Clientbibliotheken unterstützt, die in .NET Framework für Silverlight bereitgestellt werden. Weitere Informationen finden Sie unter [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149).  
  
 Die .NET Framework-Clientbibliotheken unterstützen die folgenden asynchronen Vorgänge:  
  
|Vorgang|Methoden|  
|---------------|-------------|  
|Ausführen einer <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Ausführen einer Abfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Ausführen einer Batchabfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Laden einer verknüpften Entität in den <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Speichern von Änderungen an Objekten im <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Überlegungen zum Threading für asynchrone Vorgänge  
 In einer Multithreadanwendung, die als Rückruf für den asynchronen Vorgang registrierte Delegat nicht unbedingt aufgerufen auf dem gleichen Thread, der verwendet wurde, zum Aufrufen der *beginnen* -Methode, die die ursprüngliche Anforderung erstellt. In einer Anwendung, in dem der Rückruf für einen bestimmten Thread aufgerufen werden muss, müssen Sie explizites Marshalling die Ausführung der *End* -Methode, die die Antwort behandelt, zum gewünschten Thread durchführen. In WPF (Windows Presentation Foundation)-basierten Anwendungen und Silverlight-basierten Anwendungen muss z. B. das Marshalling der Antwort zurück zum Benutzeroberflächenthread mit der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>-Methode für das <xref:System.Windows.Threading.Dispatcher>-Objekt durchgeführt werden. Weitere Informationen finden Sie unter [Abfragen des Datendiensts (WCF Data Services/Silverlight)](https://msdn.microsoft.com/library/3a7cdc07-c37e-4da2-b98b-c3763fd0970b).  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
