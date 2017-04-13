---
title: "WSHttpBinding | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "WS-Profilbindung"
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
caps.latest.revision: 39
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# WSHttpBinding
Dieses Beispiel zeigt, wie mithilfe von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein typischer Dienst und ein typischer Client implementiert werden.Das Beispiel besteht aus einem Clientkonsolenprogramm \(client.exe\) und einer von IIS \(Internet Information Services, Internetinformationsdienste\) gehosteten Dienstbibliothek.Der Dienst implementiert einen Vertrag, der ein Anforderungs\-Antwort\-Kommunikationsmuster definiert.Der Vertrag wird von der `ICalculator`\-Schnittstelle definiert, die mathematische Operationen \(Addieren, Subtrahieren, Multiplizieren und Dividieren\) verfügbar macht.Der Client stellt synchrone Anforderungen an eine gegebene mathematische Operation, und der Dienst antwortet mit dem Ergebnis.Die Clientaktivität ist im Konsolenfenster sichtbar.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
>  Die Setupprozedur und die Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Abschnitts.  
  
 In diesem Beispiel wird der `ICalculator`\-Vertrag mit dem [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) verfügbar gemacht.Die Konfiguration dieser Bindung wurde in der Datei "Web.config" ausgedehnt.  
  
```  
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
  
 Im `binding`\-Basiselement können Sie mit dem `maxReceivedMessageSize`\-Wert die maximale Größe einer eingehenden Nachricht \(in Bytes\) konfigurieren.Mit dem `hostNameComparisonMode`\-Wert können Sie konfigurieren, ob beim Demultiplexing von Nachrichten für den Dienst der Hostname eine Rolle spielt.Mit dem `messageEncoding`\-Wert können Sie konfigurieren, ob Text\- oder MTOM\-Codierung für Nachrichten verwendet werden soll.Mit dem `textEncoding`\-Wert können Sie die Zeichencodierung für Nachrichten konfigurieren.Mit dem `bypassProxyOnLocal`\-Wert können Sie konfigurieren, ob ein HTTP\-Proxy zur lokalen Kommunikation verwendet werden soll.Der `transactionFlow`\-Wert konfiguriert, ob die aktuelle Transaktion übergeben wird \(wenn ein Vorgang für den Transaktionsfluss konfiguriert ist\).  
  
 Im [\<\<reliableSession\>\>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)\-Element konfiguriert der aktivierte boolesche Wert, ob zuverlässige Sitzungen aktiviert sind.Der `ordered`\-Wert konfiguriert, ob die Nachrichtenreihenfolge beibehalten wird.Der `inactivityTimeout`\-Wert konfiguriert, wie lange sich eine Sitzung im Leerlauf befinden darf, bevor sie einen Fehler verursacht.  
  
 Im [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) konfiguriert der `mode`\-Wert, welcher Sicherheitsmodus verwendet werden soll.In diesem Beispiel wird die Nachrichtensicherheit verwendet. Daher wird [\<message\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) in [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) angegeben.  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Vergewissern Sie sich, dass Sie [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
3.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
4.  Wenn Sie das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend ausführen möchten, befolgen Sie die unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
## Siehe auch