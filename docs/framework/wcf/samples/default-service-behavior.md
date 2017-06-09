---
title: "Standard-Dienstverhalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Beispiel zum Standard-Dienstverhalten [Windows Communication Foundation]"
  - "Dienstverhalten, Standard"
ms.assetid: 442d4f71-c64e-4c62-816a-a66c38e7d3ec
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Standard-Dienstverhalten
In diesem Beispiel wird veranschaulicht, wie Einstellungen für das Dienstverhalten konfiguriert werden können.Das Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das den `ICalculator`\-Dienstvertrag implementiert.In diesem Beispiel werden explizit Dienstverhaltensweisen und Vorgangsverhaltensweisen mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute>\-Attribut bzw. dem <xref:System.ServiceModel.OperationBehaviorAttribute>\-Attribut definiert.Sie können Verhaltensweisen in Konfigurationsdateien oder imperativ im Code konfigurieren, wie dieses Beispiel zeigt.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung \(.exe\), und der Dienst wird von IIS \(Internet Information Services, Internetinformationsdienste\) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienstklasse gibt Verhaltensweisen mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute> und dem <xref:System.ServiceModel.OperationBehaviorAttribute> an, wie im folgenden Beispielcode dargestellt.Alle angegebenen Werte sind Standardwerte.  
  
```  
[ServiceBehavior(  
    AutomaticSessionShutdown=true,  
    ConcurrencyMode=ConcurrencyMode.Single,  
    InstanceContextMode=InstanceContextMode.PerSession,  
    IncludeExceptionDetailInFaults=false,  
    UseSynchronizationContext=true,  
    ValidateMustUnderstand=true)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(  
        TransactionAutoComplete=true,  
        TransactionScopeRequired=false,  
        Impersonation=ImpersonationOption.NotAllowed)]  
    public double Add(double n1, double n2)  
    {  
        System.Threading.Thread.Sleep(1600);  
        return n1 + n2;  
    }  
    ...  
}  
  
```  
  
 Dienstverhaltensweisen werden mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute>\-Attribut angegeben.In der folgenden Tabelle werden einige dieser Verhaltensweisen beschrieben.  
  
|Dienstverhalten|Beschreibung|  
|---------------------|------------------|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.AutomaticSessionShutdown%2A>|Fährt eine Sitzung auf Anforderung des Clients automatisch herunter.|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>|Gibt den Parallelitätsmodus für jede Dienstinstanz an.|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>|Gibt den Instanzkontextmodus an.|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.UseSynchronizationContext%2A>|Bestimmt, ob der bereitgestellte Synchronisierungskontext \(falls festgelegt\) verwendet werden soll.Verwenden Sie dies, wenn Sie kontrollieren möchten, ob in Windows Forms\-Anwendungen ein `WindowsFormsSynchronizationContext` verwendet werden soll.|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A>|Bestimmt, ob allgemeine unbehandelte Ausführungsausnahmen in eine `Fault<string>` konvertiert und als Fehlermeldung gesendet werden sollen.|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>|Gibt die Isolierungsebene für Transaktionen an.|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ValidateMustUnderstand%2A>|Legt fest, ob unerwartete Nachrichtenheader eine Fehlerbedingung auslösen.|  
  
 Vorgangsverhaltensweisen werden mit dem <xref:System.ServiceModel.OperationBehaviorAttribute>\-Attribut angegeben.In der folgenden Tabelle werden einige dieser Verhaltensweisen beschrieben.  
  
|Vorgangsverhalten|Beschreibung|  
|-----------------------|------------------|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>|Bestimmt, ob bei Abschluss eines Dienstvorgangs ein Commit für die aktuelle Transaktion ausgeführt wird.|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>|Bestimmt, ob sich der Dienstvorgang in einem Clienttransaktionsfluss einträgt.|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>|Bestimmt, ob der Dienstvorgang die Identität des Aufrufers annimmt.|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A>|Bestimmt, ob Dienstinstanzen zu Beginn oder am Ende des Dienstvorgangsaufrufs wiederverwendet werden.|  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.Die Verzögerung zwischen den Aufrufen resultiert von den in den Dienstvorgängen vorgenommenen Aufrufen von `System.Threading.Thread.Sleep()`.Diese Verhaltensweisen werden in den restlichen Verhaltensbeispielen ausführlicher erklärt.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
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
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Default`  
  
## Siehe auch