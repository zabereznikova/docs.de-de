---
title: Datenbindung in einem Windows Forms-Client
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: d2784c86bc3ef84f99f4731f441019b3f568b321
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575484"
---
# <a name="data-binding-in-a-windows-forms-client"></a>Datenbindung in einem Windows Forms-Client
Dieses Beispiel veranschaulicht das Binden an Daten, die von einem Windows Communication Foundation (WCF)-Dienst in einer Windows Forms-Anwendung zurückgegeben werden.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Artikels.  
  
 In diesem Beispiel wird ein Dienst veranschaulicht, der einen Vertrag implementiert, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Das Beispiel besteht aus einem Client Windows Forms Anwendung (. exe) und einem WCF-Dienst, der von Internetinformationsdienste (IIS) gehostet wird.  
  
 Der Vertrag wird von der `IWeatherService`-Schnittstelle definiert, die einen Vorgang mit der Bezeichnung `GetWeatherData` verfügbar macht. Dieser Vorgang nimmt ein Array aus Städten an und gibt ein Array aus `WeatherData`-Objekten zurück, die die vorhergesagte Höchst- und Tiefsttemperatur für eine Stadt wiedergeben.  
  
 Die Datenbindung tritt auf dem Client in der Windows Forms-Anwendung auf. `DataGridView` wird im Windows Forms-Designer definiert, der eine grafische Darstellung der Daten bereitstellt. Außerdem wird ein Vermittler namens `BindingSource` erstellt. Die Datenquelle von `BindingSource` wird auf das vom Dienst zurückgegebene Datenarray festgelegt. Die `BindingSource` soll eine Dereferenzierungsschicht zwischen den Daten und der Datenansicht bereitstellen. Alle Interaktionen mit den Daten, beispielsweise Navigieren, Sortieren, Filtern und Aktualisieren, werden durch Aufrufe der `BindingSource`-Komponente ausgeführt. Zum Ausführen der Datenbindung an `DataGridView` wird dann die `datasource` von `DataGridView` auf das `BindingSource`-Objekt festgelegt. Alle Daten, die vom WCF-Dienst zurückgegeben werden, werden dann grafisch dem Benutzer angezeigt.  Jedes Mal, wenn der Benutzer auf die Schaltfläche klickt, werden die zurückgegebenen Daten automatisch in der datengebundenen `DataGridView` aktualisiert.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
