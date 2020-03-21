---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: b1b61c18c801059e95cd0b13a3135132a583882f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183339"
---
# <a name="srmp"></a>SRMP
In diesem Beispiel wird veranschaulicht, wie eine abgewickelte Warteschlangenkommunikation mithilfe von Message Queuing (MSMQ) über HTTP durchgeführt wird.  
  
 In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst. Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet. Der Dienst empfängt Nachrichten aus der Warteschlange. Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.  
  
 MSMQ aktiviert die Verwendung des HTTP (einschließlich der Verwendung des HTTPS), um Nachrichten an eine Warteschlange zu senden. In diesem Beispiel demonstrieren wir die Verwendung der WCF-Kommunikation (Windows Communication Foundation) in der Warteschlange und das Senden von Nachrichten über HTTP. MSMQ verwendet ein Protokoll namens SRMP, das ein SOAP-basiertes Protokoll für Kommunikation über HTTP ist.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4. Stellen Sie vor dem Ausführen des Beispiels unter **Hinzufügen/Entfernen von Windows-Komponenten**sicher, dass MSMQ mit HTTP-Unterstützung installiert ist. Die Installation der HTTP-Unterstützung installiert automatisch Internetinformationsdienste (IIS) und fügt die Protokollunterstützung in IIS für MSMQ hinzu.  
  
5. Wenn Sie sichergehen möchten, dass HTTP für die Kommunikation verwendet wird, können Sie MSMQ aktivieren, um eine Ausführung im geschützten Modus zu erreichen. Hierdurch wird sichergestellt, dass keine Nachrichten an Warteschlangen, die auf dem Computer gehostet werden, durch Nicht-HTTP-Transporte empfangen werden können.  
  
6. Nachdem Sie MSMQ für die Ausführung im gehärteten Modus ausgewählt haben, muss der Computer auf Windows Server 2003 neu gestartet werden.  
  
7. Führen Sie den Dienst aus.  
  
8. Führen Sie den Client aus. Ändern Sie die Endpunktadresse so, dass diese auf den Computernamen oder die IP-Adresse anstelle von "localhost" verweist. Der Client sendet eine Nachricht und wird beendet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 Zum Ausführen dieses Beispiels muss IIS zusätzlich zu MSMQ sowohl auf dem Dienst- als auch auf dem Clientcomputer installiert sein.  
  
## <a name="demonstrates"></a>Zeigt  
 Das Beispiel veranschaulicht das Senden von WCF-Nachrichten in der Warteschlange mit MSMQ über HTTP. Dies wird auch als SRMP-Messaging bezeichnet. Wenn eine in der Warteschlange befindliche Nachricht gesendet wird, überträgt MSMQ auf dem sendenden Computer die Nachrichten über TCP- oder HTTP-Transport an den empfangenden Warteschlangen-Manager. Indem er SRMP auswählt, gibt der Benutzer die Auswahl von HTTP als Transport für Warteschlangenübertragung an. SRMP Secure aktiviert die Verwendung von HTTPS.  
  
## <a name="example"></a>Beispiel  
 Der Beispielcode basiert auf dem durchgeführten Beispiel. Wie über SRMP eine Nachricht zu einer Warteschlange gesendet und wie eine Nachricht aus einer Warteschlange empfangen wird, entspricht dem Senden und Empfangen von Nachrichten mithilfe eines systemeigenen Protokolls.  
  
 Die Konfiguration für den Client wird geändert, um die Auswahl des Warteschlangen-Übertragungsprotokolls anzugeben. Das Warteschlangen-Übertragungsprotokoll kann systemeigen, SRMP oder SrmpSecure sein. Standardmäßig ist das Übertragungsprotokoll systemeigen. Der Client und der Dienst legen in diesem Beispiel in der Konfiguration die Verwendung von SRMP fest.  
  
 Bei SRMP gibt es Einschränkungen in Bezug auf die Transportsicherheit. Die Standard-MSMQ-Transportsicherheit erfordert Active Directory. Daher müssen sich der sendende und der empfangende Warteschlangen-Manager auf der gleichen Windows-Domäne befinden. Dies ist beim Senden von Nachrichten über die HTTP-Grenze nicht möglich. Auf diese Weise funktioniert die Standardtransportsicherheit nicht. Die Transportsicherheit muss auf Zertifikat (Certificate) festgelegt werden, wenn Transportsicherheit gewünscht wird. Nachrichtensicherheit kann auch genutzt werden, um die Nachricht zu schützen. In diesem Beispiel werden sowohl Transport- als auch Nachrichtensicherheit ausgeschaltet, um SRMP-Messaging zu illustrieren.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"
           bindingConfiguration="srmpBinding"
           binding="netMsmqBinding"
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 Die Durchführung des Beispiels führt zu folgender Ausgabe.  
  
```console  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4
Customer: somecustomer.com
OrderDetails
    Order LineItem: 54 of Blue Widget @unit price: $29.99
    Order LineItem: 890 of Red Widget @unit price: $45.89
    Total cost of this order: $42461.56
    Order status: Pending  
```  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
