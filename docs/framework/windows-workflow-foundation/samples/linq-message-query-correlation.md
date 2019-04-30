---
title: LINQ-Meldungsabfragekorrelation
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: cc13696cfd8eb2dcdf22fdc067518c8bd55ca32d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004925"
---
# <a name="linq-message-query-correlation"></a>LINQ-Meldungsabfragekorrelation
Dieses Beispiel veranschaulicht, wie die inhaltsbasierte Korrelation mithilfe einer benutzerdefinierten <xref:System.ServiceModel.Dispatcher.MessageQuery>-Implementierung im Gegensatz zu der vom System bereitgestellten <xref:System.ServiceModel.XPathMessageQuery> erfolgt.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Benutzerdefinierte <xref:System.ServiceModel.Dispatcher.MessageQuery>, inhaltsbasierte Korrelation.  
  
## <a name="discussion"></a>Diskussion  
 In diesem Beispiel wird veranschaulicht, wie zum Zwecke der Korrelation eine Erweiterung von der <xref:System.ServiceModel.Dispatcher.MessageQuery>-Basisklasse durchgeführt wird. Die benutzerdefinierte Implementierung, `LinqMessageQuery`, ermöglicht es Benutzern, einen XName anzugeben, der innerhalb der Meldung mit XLinq gesucht werden soll. Die von der Abfrage abgerufenen Daten werden verwendet, um den Korrelationsschlüssel zu bilden, mit dem Meldungen an die entsprechende Workflowinstanz weitergeleitet werden.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Dieses Beispiel macht einen Workflowdienst mithilfe von HTTP-Endpunkten verfügbar. Ausführung dieser Beispiel, die richtige URL-ACLs hinzugefügt werden muss (finden Sie unter [Konfigurieren von HTTP und HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) Details), entweder durch Ausführen von Visual Studio als Administrator oder durch Ausführen von den folgenden Befehl an einer Eingabeaufforderung mit erhöhten Rechten aus, um die entsprechenden ACLs hinzuzufügen. Stellen Sie sicher, dass die Domäne und der Benutzername ersetzt werden.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. Sobald die URL-ACLs hinzugefügt wurden, führen Sie die folgenden Schritte aus.  
  
    1. Erstellen Sie die Projektmappe.  
  
    2. Legen Sie mehrere Startprojekte fest, von der rechten Maustaste auf die Projektmappe, und wählen **Startprojekte**. Hinzufügen **Service** und **Client** (in dieser Reihenfolge) als mehrere Startprojekte.  
  
    3. Führen Sie die Anwendung aus. Die Clientkonsole zeigt einen Workflow, der eine Bestellung sendet und die Bestell-ID empfängt und dann daraufhin den Auftrag bestätigt. Das Fenster "Dienst" zeigt die Anforderungen, die verarbeitet werden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
