---
title: "Zuverl&#228;ssige WS-Sitzung | Microsoft Docs"
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
  - "Zuverlässige Sitzung"
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# Zuverl&#228;ssige WS-Sitzung
Dieses Beispiel veranschaulicht die Verwendung von zuverlässigen Sitzungen.Zuverlässige Sitzungen bieten Unterstützung für zuverlässiges Messaging.Beim zuverlässigen Messaging wird die Kommunikation bei Fehlern erneut gestartet, und es werden Zustellungszusicherungen vorgenommen, wie Prüfung der Nachrichtenreihenfolge beim Eingang.Die Sitzungen erhalten den Status von Clients im Verlauf der verschiedenen Aufrufe aufrecht.Im Beispiel werden Sitzungen zum Aufrechterhalten des Clientstatus implementiert und Zustellungszusicherungen anhand der Nachrichtenreihenfolge festgelegt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das einen Rechnerdienst implementiert.Die Features für zuverlässige Sitzungen sind in den Anwendungskonfigurationsdateien für Client und Dienst aktiviert und konfiguriert.  
  
 In diesem Beispiel wird der Dienst in Internetinformationsdiensten \(IIS\) gehostet, und der Client ist eine Konsolenanwendung \(.exe\).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im Beispiel wird `wsHttpBinding` verwendet.Die Bindung wird in den Konfigurationsdateien sowohl für den Client als auch für den Dienst angegeben.Der Bindungstyp wird im `binding`\-Attribut des Endpunktelements angegeben \(siehe folgende Beispielkonfiguration\).  
  
```  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  
```  
  
 Der Endpunkt enthält ein `bindingConfiguration`\-Attribut, das auf die Bindungskonfiguration namens "Binding1" verweist. Die Bindungskonfiguration ermöglicht zuverlässige Sitzungen, indem das `enabled`\-Attribut des [\<\<reliableSession\>\>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) auf `true` festgelegt wird.Zustellungszusicherungen für geordnete Sitzungen werden gesteuert, indem das geordnete Attribut auf `true` oder `false` festgelegt wird.Der Standardwert ist `true`.  
  
```  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
  
```  
  
 Die Dienstimplementierungsklasse implementiert eine <xref:System.ServiceModel.InstanceContextMode>\-Instanziierung, um eine separate Klasseninstanz für jeden Client beizubehalten, wie im folgenden Beispielcode dargestellt.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
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
  
1.  Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Vergewissern Sie sich, dass Sie [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
3.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
4.  Wenn Sie das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend ausführen möchten, befolgen Sie die unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
## Siehe auch