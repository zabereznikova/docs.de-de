---
title: Transport und Codierung für benutzerdefinierte Bindungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: ee15fd37390f8bf4ca3bc287f9a3dbd5f8ebd935
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668677"
---
# <a name="custom-binding-transport-and-encoding"></a>Transport und Codierung für benutzerdefinierte Bindungen
Eine benutzerdefinierte Bindung wird durch eine geordnete Liste einzelner Bindungselemente definiert. In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Bindung mit verschiedenen Transportarten und Nachrichtencodierungselementen konfiguriert wird.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel basiert auf der [Selbsthosting](../../../../docs/framework/wcf/samples/self-host.md), und wurde geändert, um die drei Endpunkte zur Unterstützung von HTTP-, TCP- und NamedPipe-Transporte mit benutzerdefinierten Bindungen zu konfigurieren. Die Clientkonfiguration wurde ebenfalls entsprechend angepasst und der Clientcode verändert, um mit jedem der drei Endpunkte zu kommunizieren.  
  
 In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Bindung konfiguriert wird, die eine bestimmte Transportart und Nachrichtencodierung unterstützt. Dies wird durch Konfiguration einer Transportart und einer Codierung für das `binding`-Element erreicht. Die Reihenfolge der Bindungselemente ist wichtig, beim Definieren einer benutzerdefinierten Bindung, da jeweils eine Ebene im Kanalstapel darstellt (siehe [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)). In diesem Beispiel werden drei benutzerdefinierte Bindungen konfiguriert: ein HTTP-Transport mit Textcodierung, ein TCP-Transport mit Textcodierung und ein NamedPipe-Transport mit binärer Codierung.  
  
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
>  Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#-, C++ oder Visual Basic .NET .NET-Edition der Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
  
## <a name="see-also"></a>Siehe auch
