---
title: LINQ-Meldungsabfragekorrelation
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: a4b0ed058cfe8d3d487342c9feefdf1b1efe07c8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715585"
---
# <a name="linq-message-query-correlation"></a>LINQ-Meldungsabfragekorrelation
Dieses Beispiel veranschaulicht, wie die inhaltsbasierte Korrelation mithilfe einer benutzerdefinierten <xref:System.ServiceModel.Dispatcher.MessageQuery>-Implementierung im Gegensatz zu der vom System bereitgestellten <xref:System.ServiceModel.XPathMessageQuery> erfolgt.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Benutzerdefinierte <xref:System.ServiceModel.Dispatcher.MessageQuery>, inhaltsbasierte Korrelation.  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird veranschaulicht, wie zum Zwecke der Korrelation eine Erweiterung von der <xref:System.ServiceModel.Dispatcher.MessageQuery>-Basisklasse durchgeführt wird. Die benutzerdefinierte Implementierung, `LinqMessageQuery`, ermöglicht es Benutzern, einen XName anzugeben, der innerhalb der Meldung mit XLinq gesucht werden soll. Die von der Abfrage abgerufenen Daten werden verwendet, um den Korrelationsschlüssel zu bilden, mit dem Meldungen an die entsprechende Workflowinstanz weitergeleitet werden.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP-Endpunkten verfügbar. Zum Ausführen dieses Beispiels müssen die richtigen URL-ACLs hinzugefügt werden (Weitere Informationen finden Sie unter [Konfigurieren von http und HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) ), entweder durch Ausführen von Visual Studio als Administrator oder durch Ausführen des folgenden Befehls an einer Eingabeaufforderung mit erhöhten Rechten, um die entsprechenden ACLs hinzuzufügen. Stellen Sie sicher, dass die Domäne und der Benutzername ersetzt werden.  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. Sobald die URL-ACLs hinzugefügt wurden, führen Sie die folgenden Schritte aus.  
  
    1. Erstellen Sie die Projektmappe.  
  
    2. Legen Sie mehrere Start Projekte fest, indem Sie mit der rechten Maustaste auf die Projekt Mappe Klicken und **Start Projekte festlegen**auswählen. Fügen Sie den **Dienst** und den **Client** (in dieser Reihenfolge) als mehrere Start Projekte hinzu.  
  
    3. Führen Sie die Anwendung aus. Die Clientkonsole zeigt einen Workflow, der eine Bestellung sendet und die Bestell-ID empfängt und dann daraufhin den Auftrag bestätigt. Das Fenster "Dienst" zeigt die Anforderungen, die verarbeitet werden.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
