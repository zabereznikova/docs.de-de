---
title: Datenbindung in einem Windows Forms-Client
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: afca572fcc2c4e519d799511010d66859dc8b472
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652106"
---
# <a name="data-binding-in-a-windows-forms-client"></a>Datenbindung in einem Windows Forms-Client
In diesem Beispiel wird veranschaulicht, wie zum Binden an Daten, die von einem Windows Communication Foundation (WCF)-Dienst in einer Windows Forms-Anwendung zurückgegeben wird.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Artikels.  
  
 In diesem Beispiel wird ein Dienst veranschaulicht, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Das Beispiel besteht aus einem Windows Forms-Anwendung (.exe) von Client und einen WCF-Dienst von IIS (Internetinformationsdienste) gehostet.  
  
 Der Vertrag wird von der `IWeatherService`-Schnittstelle definiert, die einen Vorgang mit der Bezeichnung `GetWeatherData` verfügbar macht. Dieser Vorgang nimmt ein Array aus Städten an und gibt ein Array aus `WeatherData`-Objekten zurück, die die vorhergesagte Höchst- und Tiefsttemperatur für eine Stadt wiedergeben.  
  
 Die Datenbindung tritt auf dem Client in der Windows Forms-Anwendung auf. `DataGridView` wird im Windows Forms-Designer definiert, der eine grafische Darstellung der Daten bereitstellt. Außerdem wird ein Vermittler namens `BindingSource` erstellt. Die Datenquelle von `BindingSource` wird auf das vom Dienst zurückgegebene Datenarray festgelegt. Die `BindingSource` soll eine Dereferenzierungsschicht zwischen den Daten und der Datenansicht bereitstellen. Alle Interaktionen mit den Daten, beispielsweise Navigieren, Sortieren, Filtern und Aktualisieren, werden durch Aufrufe der `BindingSource`-Komponente ausgeführt. Zum Ausführen der Datenbindung an `DataGridView` wird dann die `datasource` von `DataGridView` auf das `BindingSource`-Objekt festgelegt. Alle der vom WCF-Dienst zurückgegebenen Daten dann grafisch angezeigt, die dem Benutzer.  Jedes Mal, wenn der Benutzer auf die Schaltfläche klickt, werden die zurückgegebenen Daten automatisch in der datengebundenen `DataGridView` aktualisiert.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a>Siehe auch
