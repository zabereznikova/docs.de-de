---
title: "Asynchrone Vorg&#228;nge (WCF Data Services) | Microsoft Docs"
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
  - "Asynchrone Vorgänge [WCF Data Services]"
  - "WCF Data Services, Asynchrone Vorgänge"
  - "WCF Data Services, Clientbibliothek"
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Asynchrone Vorg&#228;nge (WCF Data Services)
Bei Webanwendungen muss die gegenüber Anwendungen, die in internen Netzwerken ausgeführt werden, höhere Latenz zwischen Client und Server berücksichtigt werden.  Um die Leistung und das vom Benutzer wahrgenommene Verhalten der Anwendung zu optimieren, empfiehlt es sich, die asynchronen Methoden der <xref:System.Data.Services.Client.DataServiceContext>\-Klasse und der <xref:System.Data.Services.Client.DataServiceQuery%601>\-Klasse zu verwenden, wenn über das Internet auf [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Server zugegriffen wird.  
  
 Obwohl die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Server HTTP\-Anforderungen asynchron verarbeiten, sind einige Methoden der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliotheken synchron und warten, bis der gesamte Anforderung\/Antwort\-Austausch abgeschlossen wurde, bevor die Ausführung fortgesetzt wird.  Die asynchronen Methoden der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliotheken warten nicht, bis dieser Austausch abgeschlossen wurde. Sie können es der Anwendung ermöglichen, während dieses Austauschs eine reagierende Benutzeroberfläche beizubehalten.  
  
 Sie können asynchrone Vorgänge mit einem Paar von Methoden für die <xref:System.Data.Services.Client.DataServiceContext>\-Klasse und die <xref:System.Data.Services.Client.DataServiceQuery%601>\-Klasse ausführen, die mit *Begin* bzw. *End* beginnen.  Die *Begin*\-Methoden registrieren einen Delegaten, den der Dienst aufruft, wenn der Vorgang abgeschlossen ist.  Die *End*\-Methoden sollten im Delegaten aufgerufen werden, der zum Behandeln des Rückrufs von den abgeschlossenen Vorgängen registriert ist.  Wenn Sie die *End*\-Methode aufrufen, um einen asynchronen Vorgang abzuschließen, müssen Sie dies aus der gleichen <xref:System.Data.Services.Client.DataServiceQuery%601>\-Instanz oder <xref:System.Data.Services.Client.DataServiceContext>\-Instanz tun, mit der Sie den Vorgang begonnen haben.  Jede *Begin*\-Methode akzeptiert einen `state`\-Parameter, der ein Zustandsobjekt an den Rückruf übergeben kann.  Dieses Zustandsobjekt wird aus dem <xref:System.IAsyncResult> abgerufen, das mit dem Rückruf angegeben wird, und wird zum Aufrufen der entsprechenden *End*\-Methode zum Abschließen des asynchronen Vorgangs verwendet.  Wenn Sie beispielsweise die <xref:System.Data.Services.Client.DataServiceQuery%601>\-Instanz als `state`\-Parameter beim Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>\-Methode für die Instanz angeben, wird die gleiche <xref:System.Data.Services.Client.DataServiceQuery%601>\-Instanz vom <xref:System.IAsyncResult> zurückgegeben.  Diese Instanz von <xref:System.Data.Services.Client.DataServiceQuery%601> wird anschließend verwendet, um die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>\-Methode zum Abschließen des Abfragevorgangs aufzurufen.  Weitere Informationen finden Sie unter [Gewusst wie: Ausführen von asynchronen Datendienstabfragen](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
>  Nur asynchrone Vorgänge werden von den Clientbibliotheken unterstützt, die in .NET Framework für Silverlight bereitgestellt werden.  Weitere Informationen finden Sie unter [WCF Data Services \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkID=143149).  
  
 Die .NET Framework\-Clientbibliotheken unterstützen die folgenden asynchronen Vorgänge:  
  
|Vorgang|Methoden|  
|-------------|--------------|  
|Ausführen einer <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Ausführen einer Abfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Ausführen einer Batchabfrage aus dem <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Laden einer verknüpften Entität in den <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Speichern von Änderungen an Objekten im <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## Überlegungen zum Threading für asynchrone Vorgänge  
 In einer Multithreadanwendung wird der als Rückruf für den asynchronen Vorgang registrierte Delegat nicht unbedingt auf dem gleichen Thread aufgerufen, der zum Aufrufen der *Begin*\-Methode verwendet wurde, die die ursprüngliche Anforderung erstellt.  In einer Anwendung, wo der Rückruf auf einem bestimmten Thread aufgerufen werden muss, müssen Sie explizites Marshalling der Ausführung der *End*\-Methode, die die Antwort behandelt, zum gewünschten Thread durchführen.  In WPF \(Windows Presentation Foundation\)\-basierten Anwendungen und Silverlight\-basierten Anwendungen muss z. B. das Marshalling der Antwort zurück zum Benutzeroberflächenthread mit der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>\-Methode für das <xref:System.Windows.Threading.Dispatcher>\-Objekt durchgeführt werden.  Weitere Informationen finden Sie unter [Querying the Data Service \(WCF Data Services\/Silverlight\)](http://msdn.microsoft.com/de-de/3a7cdc07-c37e-4da2-b98b-c3763fd0970b).  
  
## Siehe auch  
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)