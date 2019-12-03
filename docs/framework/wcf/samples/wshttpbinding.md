---
title: WSHttpBinding
ms.date: 03/30/2017
helpviewer_keywords:
- WS Profile binding
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
ms.openlocfilehash: 6ea07f206064a389da8af04a4afd292022b8ca44
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714567"
---
# <a name="wshttpbinding"></a>WSHttpBinding
In diesem Beispiel wird veranschaulicht, wie ein typischer Dienst und ein typischer Client mithilfe von Windows Communication Foundation (WCF) implementiert werden. Das Beispiel besteht aus einem Clientkonsolenprogramm (client.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek. Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht. Der Client stellt synchrone Anforderungen an eine gegebene mathematische Operation, und der Dienst antwortet mit dem Ergebnis. Die Clientaktivität ist im Konsolenfenster sichtbar.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel macht den `ICalculator` Vertrag mithilfe des [\<WSHttpBinding-> verfügbar](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Die Konfiguration dieser Bindung wurde in der Datei „Web.config“ erweitert.  
  
```xml
<bindings>  
  <wsHttpBinding>  
    <!--The following is the expanded configuration section for a-->  
    <!--WSHttpBinding. Each property is configured with the default-->   
    <!--value. See the ReliableSession, TransactionFlow, -->  
    <!--TransportSecurity, and MessageSecurity samples in the WS -->  
    <!--directory to learn how to configure these features. -->  
    <binding name="Binding1"  
              bypassProxyOnLocal="false"   
              transactionFlow="false"   
              hostNameComparisonMode="StrongWildcard"  
              maxBufferPoolSize="524288"   
              maxReceivedMessageSize="65536"  
              messageEncoding="Text"   
              textEncoding="utf-8"   
              useDefaultWebProxy="true"  
              allowCookies="false">  
      <reliableSession ordered="true"   
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Message">  
        <message clientCredentialType="Windows"   
                 negotiateServiceCredential="true"  
                 algorithmSuite="Default"   
                 establishSecurityContext="true" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 Im `binding`-Basiselement können Sie mit dem `maxReceivedMessageSize`-Wert die maximale Größe einer eingehenden Nachricht (in Bytes) konfigurieren. Mit dem `hostNameComparisonMode`-Wert können Sie konfigurieren, ob beim Demultiplexing von Nachrichten für den Dienst der Hostname eine Rolle spielt. Mit dem `messageEncoding`-Wert können Sie konfigurieren, ob Text- oder MTOM-Codierung für Nachrichten verwendet werden soll. Mit dem `textEncoding`-Wert können Sie die Zeichencodierung für Nachrichten konfigurieren. Mit dem `bypassProxyOnLocal`-Wert können Sie konfigurieren, ob ein HTTP-Proxy zur lokalen Kommunikation verwendet werden soll. Der `transactionFlow`-Wert konfiguriert, ob die aktuelle Transaktion übergeben wird (wenn ein Vorgang für den Transaktionsfluss konfiguriert ist).  
  
 Im [\<ReliableSession->](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) Element konfiguriert der aktivierte boolesche Wert, ob zuverlässige Sitzungen aktiviert sind. Der `ordered`-Wert konfiguriert, ob die Nachrichtenreihenfolge beibehalten wird. Der `inactivityTimeout`-Wert konfiguriert, wie lange sich eine Sitzung im Leerlauf befinden darf, bevor sie einen Fehler verursacht.  
  
 Auf der [\<-Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)konfiguriert der `mode` Wert, welcher Sicherheitsmodus verwendet werden soll. In diesem Beispiel wird die Nachrichten Sicherheit verwendet. aus diesem Grund wird die [\<-Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) in der [\<Security->](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)angegeben.  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
