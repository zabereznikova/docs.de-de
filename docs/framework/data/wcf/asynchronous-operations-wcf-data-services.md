---
title: "Asynchrone Vorgänge (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1fc4b2f02c5b07df71ccf78ade4904297583f7e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-operations-wcf-data-services"></a>Asynchrone Vorgänge (WCF Data Services)
Bei Webanwendungen muss die gegenüber Anwendungen, die in internen Netzwerken ausgeführt werden, höhere Latenz zwischen Client und Server berücksichtigt werden. Um die Leistung und das vom Benutzer wahrgenommene Verhalten der Anwendung zu optimieren, empfiehlt es sich, die asynchronen Methoden der <xref:System.Data.Services.Client.DataServiceContext>-Klasse und der <xref:System.Data.Services.Client.DataServiceQuery%601>-Klasse zu verwenden, wenn über das Internet auf [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Server zugegriffen wird.  
  
 Obwohl die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Server HTTP-Anforderungen asynchron verarbeiten, sind einige Methoden der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliotheken synchron und warten, bis der gesamte Anforderung/Antwort-Austausch abgeschlossen wurde, bevor die Ausführung fortgesetzt wird. Die asynchronen Methoden der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliotheken warten nicht, bis dieser Austausch abgeschlossen wurde. Sie können es der Anwendung ermöglichen, während dieses Austauschs eine reagierende Benutzeroberfläche beizubehalten.  
  
 Können Sie asynchrone Vorgänge ausführen, indem Sie ein Paar von Methoden auf die <xref:System.Data.Services.Client.DataServiceContext> und <xref:System.Data.Services.Client.DataServiceQuery%601> Klassen, die mit beginnt *beginnen* und *End* bzw.. Die *beginnen* Methoden zu registrieren ein Delegat, der den Dienst aufruft, wenn der Vorgang abgeschlossen ist. Die *End* Methoden aufgerufen werden soll, in der Delegat, der zum Behandeln des Rückrufs von den abgeschlossenen Vorgängen registriert ist. Beim Aufrufen der *End* -Methode zum Abschließen eines asynchronen Vorgangs müssen Sie dies tun, aus der gleichen <xref:System.Data.Services.Client.DataServiceQuery%601> oder <xref:System.Data.Services.Client.DataServiceContext> Instanz, mit denen Sie den Vorgang zu starten. Jede *beginnen* -Methode übernimmt ein `state` Parameter, der ein Zustandsobjekt an den Rückruf übergeben kann. Dieses Zustandsobjekt wird abgerufen, von der <xref:System.IAsyncResult> , die mit dem Rückruf angegeben wird, und wird verwendet, um das Aufrufen der entsprechenden *End* Methode, um den asynchronen Vorgang abzuschließen. Wenn Sie beispielsweise die <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz als `state`-Parameter beim Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode für die Instanz angeben, wird die gleiche <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz vom <xref:System.IAsyncResult> zurückgegeben. Diese Instanz von <xref:System.Data.Services.Client.DataServiceQuery%601> wird anschließend verwendet, um die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode zum Abschließen des Abfragevorgangs aufzurufen. Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen des asynchronen Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
>  Nur asynchrone Vorgänge werden von den Clientbibliotheken unterstützt, die in .NET Framework für Silverlight bereitgestellt werden. Weitere Informationen finden Sie unter [WCF Data Services (Silverlight)](http://go.microsoft.com/fwlink/?LinkID=143149).  
  
 Die .NET Framework-Clientbibliotheken unterstützen die folgenden asynchronen Vorgänge:  
  
|Vorgang|Methoden|  
|---------------|-------------|  
|Ausführen einer <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Ausführen einer Abfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Ausführen einer Batchabfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Laden einer verknüpften Entität in den <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Speichern von Änderungen an Objekten im <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Überlegungen zum Threading für asynchrone Vorgänge  
 In einer Multithreadanwendung Aufrufen des Delegaten, der als Rückruf für den asynchronen Vorgang registriert ist nicht unbedingt auf dem gleichen Thread, der verwendet wurde, zum Aufrufen der *beginnen* -Methode, die die ursprüngliche Anforderung erstellt. In einer Anwendung, wo der Rückruf auf einem bestimmten Thread aufgerufen werden muss, müssen Sie explizites Marshalling die Ausführung der *End* -Methode, die die Antwort behandelt, zum gewünschten Thread durchführen. In WPF (Windows Presentation Foundation)-basierten Anwendungen und Silverlight-basierten Anwendungen muss z. B. das Marshalling der Antwort zurück zum Benutzeroberflächenthread mit der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>-Methode für das <xref:System.Windows.Threading.Dispatcher>-Objekt durchgeführt werden. Weitere Informationen finden Sie unter [Abfragen des Datendiensts (WCF Data Services/Silverlight)](http://msdn.microsoft.com/en-us/3a7cdc07-c37e-4da2-b98b-c3763fd0970b).  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
