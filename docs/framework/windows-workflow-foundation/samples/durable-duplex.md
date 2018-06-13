---
title: Permanenter Duplex
ms.date: 03/30/2017
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
ms.openlocfilehash: 3df5ba962ef33594df1eaebc20789fa9e2d35244
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809426"
---
# <a name="durable-duplex"></a>Permanenter Duplex
Dieses Beispiel veranschaulicht das Einrichten und konfigurieren permanenter duplexnachrichtenaustausch mithilfe der messagingaktivitäten in Windows Workflow Foundation (WF). Ein permanenter Duplexnachrichtenaustausch ist ein bidirektionaler Nachrichtenaustausch, der im Verlauf eines langen Zeitraums stattfindet. Die Lebensdauer des Nachrichtenaustauschs ist möglicherweise länger als die Lebensdauer des Kommunikationskanals und die Lebensdauer der Dienstinstanzen im Arbeitsspeicher.  
  
## <a name="sample-details"></a>Beispieldetails  
 In diesem Beispiel sind zwei Windows Communication Foundation (WCF)-Dienste, die mithilfe von Windows Workflow Foundation implementiert haben einen permanenten duplexnachrichtenaustausch konfiguriert. Der permanente duplexnachrichtenaustausch besteht aus zwei unidirektionalen Nachrichten über MSMQ gesendet und eine Korrelation zwischen verwenden [.NET Context Exchange](http://go.microsoft.com/fwlink/?LinkID=166059). Die Nachrichten werden mit den Messagingaktivitäten <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.Receive> gesendet. Der .NET-Kontextaustausch wird verwendet, um die Rückrufadresse in den gesendeten Nachrichten anzugeben. Beide Dienste werden mit WAS (Windows Process Activation Services) gehostet und sind konfiguriert, um Persistenz der Dienstinstanzen zu ermöglichen.  
  
 Der erste Dienst (Service1.xamlx) sendet eine Anforderung an den zweiten Dienst (Service2.xamlx), einige Arbeiten zu erledigen. Sobald die Arbeit abgeschlossen ist, sendet Service2.xamlx eine Benachrichtigung an Service1.xamlx zurück, um anzugeben, dass die Arbeit abgeschlossen ist. Eine Konsolenanwendung für Workflows richtet die Warteschlangen ein, die die Dienste überwachen, und sendet die ursprüngliche Startnachricht, um Service1.xamlx zu aktivieren. Sobald Service1.xamlx die Benachrichtigung von Service2.xamlx empfangen hat, dass die angeforderte Arbeit abgeschlossen ist, speichert Service1.xamlx das Ergebnis in einer XML-Datei. Während des Wartens auf die Rückrufmeldung behält Service1.xamlx den Instanzzustand mit dem standardmäßigen <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> bei. Service2.xamlx behält den Instanzzustand als Teil des Abschlusses der von Service1.xamlx angeforderten Arbeit bei.  
  
 Um die Dienste zu konfigurieren, sodass der .NET-Kontextaustausch über MSMQ verwendet wird, werden beide Dienste zur Verwendung einer benutzerdefinierten Bindung konfiguriert, die aus <xref:System.ServiceModel.Channels.ContextBindingElement> und <xref:System.ServiceModel.Channels.MsmqTransportBindingElement> besteht. Eine Rückrufadresse wird mit <xref:System.ServiceModel.Channels.ContextBindingElement> angegeben und ist in einem Rückrufkontextheader von allen Nachrichten enthalten, die mit einer benutzerdefinierten Bindung gesendet werden. Im folgenden Codebeispiel wird die benutzerdefinierte Bindung definiert.  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  Die von diesem Beispiel verwendete Bindung ist nicht sicher. Wenn Sie die Anwendung bereitstellen, sollten Sie die Bindung auf Grundlage der Sicherheitsanforderungen der Anwendung konfigurieren.  
  
> [!NOTE]
>  Die in diesem Beispiel verwendeten Warteschlangen sind nicht transaktionsgebunden. Ein Beispiel, das zeigt, wie WCF-Nachrichtenaustausch, die mithilfe von Warteschlangen Transaktion eingerichtet werden, finden Sie unter der [MSMQ-Aktivierung](../../../../docs/framework/wcf/samples/msmq-activation.md) Beispiel.  
  
 Die von Service1.xamlx an Service2.xamlx gesendete Nachricht wird mit einem Clientendpunkt gesendet, der mit der Adresse von Service2.xamlx und der benutzerdefinierten Bindung, die zuvor definiert wurden, konfiguriert ist. Der Rückruf von Service2.xamlx an Service1.xamlx wird mit einem Clientendpunkt ohne explizit konfigurierte Adresse gesendet, da die Adresse dem Rückrufkontext entnommen wird, der von Service1.xamlx gesendet wurde. Im folgenden Codebeispiel werden die Clientendpunkte definiert.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 Das folgende Codebeispiel macht Endpunkte verfügbar, die diese benutzerdefinierte Bindung verwenden, indem die Standardprotokollzuordnung für net.msmq-Basisadressen auf die Verwendung dieser benutzerdefinierten Bindung geändert wird.  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 Im folgenden Codebeispiel wird Persistenz für beide Dienste ermöglicht, indem das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>-Verhalten den Diensten hinzufügt und die Verbindungszeichenfolge für die Persistenzdatenbank angegeben wird.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a>Systemanforderungen  
 Folgende Komponenten sind für dieses Beispiel erforderlich.  
  
1.  Internetinformationsdienste.  
  
2.  Internetinformationsdienste -> IIS 6.0-Verwaltungskompatibilität -> IIS-Metabasis und IIS 6.0-Konfigurationskompatibilität.  
  
3.  WWW-Dienste -> Anwendungsentwicklungsfunktionen -> ASP.NET.  
  
4.  Microsoft-Server für Meldungswarteschlangen (MSMQ).  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Richten Sie die Persistenzdatenbank und das Ergebnisverzeichnis ein.  
  
    1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
    2.  Navigieren Sie zum Ordner für dieses Beispiel, und führen "Setup.cmd" aus.  
  
2.  Richten Sie die virtuelle Anwendung ein.  
  
    1.  Registrieren Sie an einer [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung ASP.NET, indem Sie den folgenden Befehl ausführen.  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  Führen Sie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] mit Administratorberechtigungen durch Rechtsklicken auf [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] auswählen und **als Administrator ausführen**.  
  
    3.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Datei "DurableDuplex.sln".  
  
3.  Richten Sie die Dienstwarteschlangen ein.  
  
    1.  Um den DurableDuplex-Client auszuführen, drücken Sie F5.  
  
    2.  Öffnen der **Computerverwaltung** Konsole Treiberdienst `Compmgmt.msc` über eine Eingabeaufforderung.  
  
    3.  Erweitern Sie **Dienste und Anwendungen**, **Message Queuing-**. **Private Warteschlangen**.  
  
    4.  Mit der rechten Maustaste in der Warteschlangen durableduplex/service1.xamlx und durableduplex/Service2.xamlx, und wählen Sie **Eigenschaften**.  
  
    5.  Wählen Sie die **Sicherheit** Registerkarte und ermöglichen **"Jeder" Nachricht empfangen**, **Peek Message** und **Send Message** Berechtigungen für beide Warteschlangen.  
  
    6.  Öffnen Sie den IIS-Manager (Internet Information Services, Internetinformationsdienste).  
  
    7.  Navigieren Sie zu **Server**, **Sites**, **Standardwebsite**, **private**, **permanenter Duplex** , und wählen Sie **Erweiterte Optionen**.  
  
    8.  Ändern der **aktivierte Protokolle** auf **HTTP, NET.MSMQ**.  
  
4.  Führen Sie das Beispiel aus.  
  
    1.  Navigieren Sie zu http://localhost/private/durableduplex/service1.xamlx und http://localhost/private/durableduplex/service2.xamlx um sicherzustellen, dass beide Dienste ausgeführt werden.  
  
    2.  Drücken Sie F5, um DurableDuplexClient auszuführen.  
  
         Wenn der permanente Duplexnachrichtenaustausch abgeschlossen ist, wird eine result.xml-Datei im Ordner C:\Inbox gespeichert und enthält das Ergebnis des Nachrichtenaustauschs.  
  
#### <a name="to-cleanup-optional"></a>So führen Sie eine (optionale) Bereinigung durch  
  
1.  Führen Sie die Datei "Cleanup.cmd" aus.  
  
    1.  Öffnen Sie eine [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]-Eingabeaufforderung.  
  
    2.  Navigieren Sie zum Ordner für dieses Beispiel, und führen "Cleanup.cmd" aus.  
  
2.  Entfernen Sie die virtuelle Anwendung für die Dienste.  
  
    1.  Öffnen Sie den Internetinformationsdienste (Internet Information Services, IIS) Manager durch Ausführen von `Inetmgr.exe` über eine Eingabeaufforderung.  
  
    2.  Navigieren Sie zu der Standardwebsite, und entfernen Sie die **private** virtuelles Verzeichnis.  
  
3.  Entfernen Sie die Warteschlangeneinrichtung für dieses Beispiel.  
  
    1.  Öffnen Sie die Computerverwaltungskonsole Treiberdienst `Compmgmt.msc` über eine Eingabeaufforderung.  
  
    2.  Erweitern Sie **Dienste und Anwendungen**, **Message Queuing-**, **Private Warteschlangen**.  
  
    3.  Löschen Sie die Warteschlangen durableduplex/service1.xamlx und durableduplex/service2.xamlx.  
  
4.  Entfernen Sie das Verzeichnis C:\Inbox.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`