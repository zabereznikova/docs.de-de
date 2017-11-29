---
title: Adressheader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 19a7291ce13221e85b49c6ef97c6b375b8b71014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="address-headers"></a>Adressheader
Im Beispiel zu Adressheadern wird veranschaulicht, wie Clients Verweisparameter mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] an einen Dienst übergeben können.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In der WS-Adressierungsspezifikation wird ein Endpunktverweis als Möglichkeit definiert, einen bestimmten Webdienstendpunkt zu adressieren. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden Endpunktverweise mit der `EndpointAddress`-Klasse modelliert. `EndpointAddress` ist der Typ des Address-Felds in der `ServiceEndpoint`-Klasse.  
  
 Bestandteil des Endpunktverweismodells ist, dass jeder Verweis einige Verweisparameter enthalten kann, die weitere identifizierende Informationen liefern. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden diese Endpunktverweise als Instanzen der `AddressHeader`-Klasse modelliert.  
  
 In diesem Beispiel fügt der Client der `EndpointAddress` des Clientendpunkts einen Verweisparameter hinzu. Der Dienst sucht diesen Verweisparameter und verwendet seinen Wert in der Logik des "Hello"-Dienstvorgangs.  
  
## <a name="client"></a>Client  
 Damit der Client einen Verweisparameter senden kann, muss er der `AddressHeader` von `EndpointAddress` einen `ServiceEndpoint` hinzufügen. Da die `EndpointAddress`-Klasse unveränderlich ist, muss das Ändern einer Endpunktadresse mithilfe der `EndpointAddressBuilder`-Klasse erfolgen. Im folgenden Code wird der Client zum Senden eines Verweisparameters als Teil der Nachricht initialisiert.  
  
```  
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 Im Code wird ein `EndpointAddressBuilder` mit der ursprünglichen `EndpointAddress` als Anfangswert erstellt. Dann wird ein neu erstellter Adressheader hinzugefügt. Durch den Aufruf von `CreateAddressHeadercreates` wird ein Header mit einem bestimmten Namen, Namespace und Wert erstellt. Hier lautet der Wert "John". Nach dem Hinzufügen des Headers zum Builder konvertiert die `ToEndpointAddress()`-Methode den (änderbaren) Builder zurück in eine (unveränderliche) Endpunktadresse. Diese wird dann wieder dem Address-Feld des Clientendpunkts zugewiesen.  
  
 Wenn der Client nun `Console.WriteLine(client.Hello());` aufruft, kann der Dienst den Wert dieses Adressparameters abrufen, wie in der Ausgabe des Clients angezeigt.  
  
 `Hello, John`  
  
## <a name="server"></a>Server  
 Bei der Implementierung des Servervorgangs `Hello()` wird der aktuelle `OperationContext` verwendet, um die Werte der Header in der eingehenden Nachricht zu überprüfen.  
  
```  
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h =   
        OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr =   
OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 Der Code durchläuft alle Header in der eingehenden Nachricht und sucht Header, bei denen es sich um Verweisparameter mit einem bestimmten Namen handelt. Wenn der Parameter gefunden wird, wird der Wert des Parameters gelesen und in der "id"-Variablen gespeichert.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
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
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## <a name="see-also"></a>Siehe auch
