---
title: "MTOM-Codierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 820e316f-4ee1-4eb5-ae38-b6a536e8a14f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# MTOM-Codierung
Dieses Beispiel veranschaulicht die Verwendung der MTOM\-Nachrichtencodierung \(Message Transmission Optimization Mechanism\) mit einer WSHttpBinding.MTOM ist ein Mechanismus zum Übertragen großer Binäranhänge mit SOAP\-Nachrichten als unformatierte Bytes, was kleinere Nachrichten ermöglicht.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MTOM`  
  
 Standardmäßig sendet und empfängt WSHttpBinding Nachrichten als normales Text\-XML.Wenn Sie das Senden und Empfangen von MTOM\-Nachrichten aktivieren möchten, legen Sie das `messageEncoding`\-Attribut in der Bindungskonfiguration \(wie im folgenden Beispielcode\) oder direkt in der Bindung mithilfe der `MessageEncoding`\-Eigenschaft fest.Der Dienst oder Client kann nun MTOM\-Nachrichten senden und empfangen.  
  
```  
<wsHttpBinding>  
    <binding name="WSHttpBinding_IUpload" messageEncoding="Mtom"/>  
</wsHttpBinding>  
```  
  
 Der MTOM\-Encoder kann Arrays von Bytes und Streams optimieren.In diesem Beispiel verwendet der Vorgang einen `Stream`\-Parameter und kann deshalb optimiert werden.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
  public interface IUpload  
  {  
      [OperationContract]  
      int Upload(Stream data);  
  }  
```  
  
 Der für dieses Beispiel gewählte Vertrag überträgt Binärdaten an den Dienst und empfängt die Anzahl der hochgeladenen Bytes als Rückgabewert.Wenn der Dienst installiert ist und der Client ausgeführt wird, gibt er die Zahl 1000 aus. Damit wird angezeigt, dass alle 1000 Bytes empfangen wurden.Der Rest der Ausgabe führt optimierte und nicht optimierte Nachrichtengrößen für verschiedene Nutzlasten auf.  
  
```  
Output:  
1000  
  
Text encoding with a 100 byte payload: 433  
MTOM encoding with a 100 byte payload: 912  
  
Text encoding with a 1000 byte payload: 1633  
MTOM encoding with a 1000 byte payload: 2080  
  
Text encoding with a 10000 byte payload: 13633  
MTOM encoding with a 10000 byte payload: 11080  
  
Text encoding with a 100000 byte payload: 133633  
MTOM encoding with a 100000 byte payload: 101080  
  
Text encoding with a 1000000 byte payload: 1333633  
MTOM encoding with a 1000000 byte payload: 1001080  
  
Press <ENTER> to terminate client.  
```  
  
 Der Zweck der Verwendung von MTOM besteht in der Optimierung der Übertragung großer binärer Nutzlasten.Das Senden einer SOAP\-Nachricht mit MTOM bedeutet zwar einen deutlichen Mehraufwand bei kleinen binären Nutzlasten, ist jedoch bei Datenmengen von mehr als einigen Tausend Bytes eine große Ersparnis.Der Grund dafür liegt darin, dass normales Text\-XML Binärdaten mit Base64 codiert. Dabei sind vier Zeichen für drei Bytes erforderlich, wodurch die Datenmenge um ein Drittel vergrößert wird.MTOM kann Binärdaten als unformatierte Bytes übertragen, spart dadurch die Zeit zum Codieren\/Decodieren und erzeugt kleinere Nachrichten.Der Schwellenwert von einigen Tausend Bytes ist verglichen mit heutigen Geschäftsdokumenten und Digitalfotos klein.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Vergewissern Sie sich, dass Sie [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
3.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
4.  Wenn Sie das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend ausführen möchten, befolgen Sie die unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
## Siehe auch