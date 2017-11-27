---
title: Datenbindung in einem Windows Forms-Client
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 163bd72d9c42680d72c435e8266c75876490a2dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-in-a-windows-forms-client"></a>Datenbindung in einem Windows Forms-Client
Dieses Beispiel veranschaulicht das Binden an Daten, die von einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst zurückgegeben wurden, in einer Windows Forms-Anwendung.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Artikels.  
  
 In diesem Beispiel wird ein Dienst veranschaulicht, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Das Beispiel besteht aus einer Windows Forms-Clientanwendung (.exe) und einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst, der von Internetinformationsdiensten (IIS) gehostet wird.  
  
 Der Vertrag wird von der `IWeatherService`-Schnittstelle definiert, die einen Vorgang mit der Bezeichnung `GetWeatherData` verfügbar macht. Dieser Vorgang nimmt ein Array aus Städten an und gibt ein Array aus `WeatherData`-Objekten zurück, die die vorhergesagte Höchst- und Tiefsttemperatur für eine Stadt wiedergeben.  
  
 Die Datenbindung tritt auf dem Client in der Windows Forms-Anwendung auf. `DataGridView` wird im Windows Forms-Designer definiert, der eine grafische Darstellung der Daten bereitstellt. Außerdem wird ein Vermittler namens `BindingSource` erstellt. Die Datenquelle von `BindingSource` wird auf das vom Dienst zurückgegebene Datenarray festgelegt. Die `BindingSource` soll eine Dereferenzierungsschicht zwischen den Daten und der Datenansicht bereitstellen. Alle Interaktionen mit den Daten, beispielsweise Navigieren, Sortieren, Filtern und Aktualisieren, werden durch Aufrufe der `BindingSource`-Komponente ausgeführt. Zum Ausführen der Datenbindung an `DataGridView` wird dann die `datasource` von `DataGridView` auf das `BindingSource`-Objekt festgelegt. Alle vom [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zurückgegebenen Daten werden für den Benutzer grafisch angezeigt.  Jedes Mal, wenn der Benutzer auf die Schaltfläche klickt, werden die zurückgegebenen Daten automatisch in der datengebundenen `DataGridView` aktualisiert.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a>Siehe auch
