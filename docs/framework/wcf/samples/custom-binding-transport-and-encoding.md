---
title: Transport und Codierung für benutzerdefinierte Bindungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: 47841b23dc3259aeb233192f396397745864d7ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145163"
---
# <a name="custom-binding-transport-and-encoding"></a>Transport und Codierung für benutzerdefinierte Bindungen
Eine benutzerdefinierte Bindung wird durch eine geordnete Liste einzelner Bindungselemente definiert. In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Bindung mit verschiedenen Transportarten und Nachrichtencodierungselementen konfiguriert wird.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel basiert auf [dem Self-Host](../../../../docs/framework/wcf/samples/self-host.md)und wurde geändert, um drei Endpunkte für http-, TCP- und NamedPipe-Transporte mit benutzerdefinierten Bindungen zu konfigurieren. Die Clientkonfiguration wurde ebenfalls entsprechend angepasst und der Clientcode verändert, um mit jedem der drei Endpunkte zu kommunizieren.  
  
 In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Bindung konfiguriert wird, die eine bestimmte Transportart und Nachrichtencodierung unterstützt. Dies wird durch Konfiguration einer Transportart und einer Codierung für das `binding`-Element erreicht. Die Reihenfolge von Bindungselementen ist wichtig, um eine benutzerdefinierte Bindung zu definieren, da jede eine Ebene im Kanalstapel darstellt (siehe [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)). In diesem Beispiel werden drei benutzerdefinierte Bindungen konfiguriert: ein HTTP-Transport mit Textcodierung, ein TCP-Transport mit Textcodierung und ein NamedPipe-Transport mit binärer Codierung.  
  
 Die Dienstkonfiguration definiert die benutzerdefinierten Bindungen wie folgt:  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt. Der Client kommuniziert mit jedem der drei Endpunkte und greift dabei zuerst auf HTTP zu, dann auf TCP und schließlich auf NamedPipe. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
 Die `namedPipeTransport`-Bindung unterstützt keine computerübergreifenden Vorgänge. Sie dient nur zur Kommunikation auf einem einzigen Computer. Wenn das Beispiel computerübergreifend ausgeführt werden soll, kommentieren Sie die folgenden Zeilen in der Clientcodedatei aus:  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
> Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die .NET-Edition von C, C++ oder Visual Basic zu erstellen.  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
