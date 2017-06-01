---
title: "Zusammenwirken mit ASMX-Webdiensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7c11f0a-9e68-4f03-a6b1-39cf478d1a89
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Zusammenwirken mit ASMX-Webdiensten
In diesem Beispiel wird veranschaulicht, wie eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Clientanwendung in einem vorhandenen ASMX\-Webdienst integriert wird.  
  
> [!NOTE]
>  Die Setupprozedur und die Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel besteht aus einem Clientkonsolenprogramm \(.exe\) und einer von IIS \(Internet Information Services, Internetinformationsdienste\) gehosteten Dienstbibliothek \(.dll\).Bei dem Dienst handelt es sich um einen ASMX\-Webdienst, der einen Vertrag implementiert, der ein Anforderungs\-Antwort\-Kommunikationsmuster definiert.Der Dienst macht mathematische Operationen \(`Add`, `Subtract`, `Multiply` und `Divide`\) verfügbar.Der Client stellt synchrone Anforderungen an einen mathematischen Vorgang, und der Dienst antwortet mit dem Ergebnis.Die Clientaktivität ist im Konsolenfenster sichtbar.  
  
 Die im folgenden Beispielcode dargestellte ASMX\-Webdienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück.  
  
```  
[WebService(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class CalculatorService : System.Web.Services.WebService  
    {  
        [WebMethod]  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
        [WebMethod]  
        public double Subtract(double n1, double n2)  
        {  
            return n1 - n2;  
        }  
        [WebMethod]  
        public double Multiply(double n1, double n2)  
        {  
            return n1 * n2;  
        }  
        [WebMethod]  
        public double Divide(double n1, double n2)  
        {  
            return n1 / n2;  
        }  
    }  
  
```  
  
 Wie in der Konfiguration angegeben, kann auf den Dienst unter http:\/\/localhost\/servicemodelsamples\/service.asmx von einem Client auf dem gleichen Computer zugegriffen werden.Für Clients auf Remotecomputern muss für den Dienstzugriff statt localhost ein vollqualifizierter Domänenname angegeben werden.  
  
 Die Kommunikation erfolgt über einen vom [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generierten Client.Der Client ist in der Datei "generatedClient.cs" enthalten.Der ASMX\-Dienst muss zur Generierung des Proxycodes verfügbar sein, da dieser zum Abrufen der aktualisierten Metadaten verwendet wird.Führen Sie den folgenden Befehl an einer Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren.  
  
```  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedClient.cs  
```  
  
 Durch das Verwenden des generierten Clients können Sie auf einen Dienstendpunkt zugreifen, indem Sie die entsprechende Adresse und Bindung konfigurieren.Wie auch der Dienst gibt der Client den Endpunkt, mit dem er kommuniziert, mithilfe einer Konfigurationsdatei \(App.config\) an.Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag, wie in der folgenden Beispielkonfiguration gezeigt.  
  
```  
<client>  
   <endpoint   
      address="http://localhost/ServiceModelSamples/service.asmx"   
      binding="basicHttpBinding"   
      contract="Microsoft.ServiceModel.Samples.CalculatorServiceSoap" />  
</client>  
  
```  
  
 Die Clientimplementierung erstellt eine Instanz des generierten Clients.Der generierte Client kann dann für die Kommunikation mit dem Dienst verwendet werden.  
  
```  
// Create a client.  
CalculatorServiceSoapClient client = new CalculatorServiceSoapClient();  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
// Call the Subtract service operation.  
value1 = 145.00D;  
value2 = 76.54D;  
result = client.Subtract(value1, value2);  
Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
// Call the Multiply service operation.  
value1 = 9.00D;  
value2 = 81.25D;  
result = client.Multiply(value1, value2);  
Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
// Call the Divide service operation.  
value1 = 22.00D;  
value2 = 7.00D;  
result = client.Divide(value1, value2);  
Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\ASMX`  
  
## Siehe auch