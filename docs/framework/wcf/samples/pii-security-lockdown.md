---
title: "Sperre der PII-Sicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
caps.latest.revision: 25
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 25
---
# Sperre der PII-Sicherheit
In diesem Beispiel wird veranschaulicht, wie mehrere sicherheitsbezogene Funktionen eines [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Diensts gesteuert werden durch:  
  
-   Das Verschlüsseln von vertraulichen Informationen in der Konfigurationsdatei eines Diensts.  
  
-   Das Sperren von Elementen in der Konfigurationsdatei, sodass geschachtelte Dienstunterverzeichnisse keine Einstellungen überschreiben können.  
  
-   Die Steuerung der Protokollierung von personenbezogenen Informationen \(PII\) in Ablaufverfolgungs\- und Nachrichtenprotokollen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## Diskussion  
 Jede dieser Funktionen kann getrennt oder gemeinsam verwendet werden, um Aspekte einer Dienstsicherheit zu steuern.  Dies ist kein endgültiger Leitfaden zur Sicherung eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts.  
  
 Die .NET Framework\-Konfigurationsdateien können vertrauliche Informationen, wie beispielsweise Verbindungszeichenfolgen enthalten, um eine Verbindung mit Datenbanken herzustellen.  In freigegebenen, im Internet gehosteten Szenarien kann es wünschenswert sein, diese Informationen in der Konfigurationsdatei für einen Dienst zu verschlüsseln, sodass die in der Konfigurationsdatei enthaltenen Daten gegen zufälliges Einsehen geschützt sind.  .NET Framework 2.0 und höher kann Teile der Konfigurationsdatei mithilfe von Windows\-DPAPI \(Data Protection Application Programming Interface\) oder dem RSA Cryptographic Provider verschlüsseln.  Die Datei "aspnet\_regiis.exe" kann mit DPAPI oder RSA ausgewählte Teile einer Konfigurationsdatei verschlüsseln.  
  
 In im Internet gehosteten Szenarien ist es möglich, Dienste in Unterverzeichnissen anderer Dienste zu haben.  Die Standardsemantik für die Bestimmung von Konfigurationswerten ermöglicht es Konfigurationsdateien in den geschachtelten Verzeichnissen, die Konfigurationswerte im übergeordneten Verzeichnis zu überschreiben.  In bestimmten Situationen kann dies aus verschiedenen Gründen unerwünscht sein.  Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienstkonfiguration unterstützt das Sperren von Konfigurationswerten, sodass eine geschachtelte Konfiguration Ausnahmen erzeugt, wenn ein geschachtelter Dienst mit überschriebenen Konfigurationswerten ausgeführt wird.  
  
 Dieses Beispiel veranschaulicht das Steuern der Protokollierung von bekannten personenbezogenen Informationen \(PII, Personally Identifiable Information\) in Ablaufverfolgungs\- und Nachrichtenprotokollen, beispielsweise Benutzername und Kennwort.  Standardmäßig ist die Protokollierung von bekannten PII deaktiviert. Allerdings kann in bestimmten Situationen die Protokollierung von PII beim Debuggen einer Anwendung wichtig sein.  Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).  In diesem Beispiel werden außerdem Ablaufverfolgungs\- und Nachrichtenprotokollierung verwendet.  Weitere Informationen finden Sie im Beispiel [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
## Verschlüsseln von Konfigurationsdateielementen  
 Aus Sicherheitsgründen kann es in einer freigegebenen Webhostingumgebung wünschenswert sein, bestimmte Konfigurationselemente zu verschlüsseln, wie beispielsweise Datenbankverbindungszeichenfolgen, die vertrauliche Informationen enthalten.  Ein Konfigurationselement kann mit dem Tool aspnet\_regiis.exe im .NET Framework\-Ordner \(z. B. %WINDIR%\\Micrsoft.NET\\Framework\\v4.0.20728\) verschlüsselt werden.  
  
#### So verschlüsseln Sie die Werte im Abschnitt appSettings in Web.config für das Beispiel  
  
1.  Öffnen Sie eine Eingabeaufforderung über "Start\-\>Ausführen".  Geben Sie `cmd` ein, und klicken Sie auf **OK**.  
  
2.  Navigieren Sie zum aktuellen .NET Framework\-Verzeichnis, indem Sie folgenden Befehl ausgeben: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.  
  
3.  Verschlüsseln Sie die appSettings\-Konfigurationseinstellungen im Web.config\-Ordner, indem Sie folgenden Befehl ausgeben: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.  
  
 Weitere Informationen zur Verschlüsselung von Abschnitten in Konfigurationsdateien finden Sie in den Anleitungen über DPAPI in der ASP.NET\-Konfiguration \([Erstellen von Secure ASP.NET\-Anwendungen: Authentifizierung, Autorisierung und sichere Kommunikation](http://go.microsoft.com/fwlink/?LinkId=95137)\) und über RSA in der ASP.NET\-Konfiguration \([Gewusst wie: Verschlüsseln von Konfigurationsabschnitten in ASP.NET 2.0 mithilfe von RSA](http://go.microsoft.com/fwlink/?LinkId=95138)\).  
  
## Sperren von Konfigurationsdateielementen  
 In im Internet gehosteten Szenarien ist es möglich, Dienste in Unterverzeichnissen von Diensten zu haben.  In diesen Situationen werden die Konfigurationswerte für den Dienst im Unterverzeichnis berechnet durch die Überprüfung von Werten in "Machine.config", darauf folgendes Zusammenfügen mit Web.config\-Dateien in übergeordneten Verzeichnissen im Verzeichnisbaum nach unten gehend sowie durch das Zusammenfügen der Web.config\-Datei im Verzeichnis, das den Dienst enthält.  Das Standardverhalten der meisten Konfigurationselemente besteht darin, zu erlauben, dass Konfigurationsdateien in Unterverzeichnissen die in den übergeordneten Verzeichnissen gesetzten Werte überschreiben.  In bestimmten Situationen kann es erwünscht sein, dass die Konfigurationsdateien in den Unterverzeichnissen die in der Konfiguration des übergeordneten Verzeichnisses gesetzten Werte nicht überschreiben.  
  
 .NET Framework bietet eine Möglichkeit des Sperrens von Konfigurationsdateielementen, sodass Konfigurationen, die gesperrte Konfigurationselemente überschreiben, Laufzeitausnahmen auslösen.  
  
 Ein Konfigurationselement kann gesperrt werden, indem das `lockItem`\-Attribut für einen Knoten in der Konfigurationsdatei festgelegt wird. Beispielsweise kann die folgende Konfiguration genutzt werden, um einen CalculatorServiceBehavior\-Knoten zu sperren, sodass Rechnerdienste in geschachtelten Konfigurationsdateien das Verhalten nicht ändern können.  
  
```  
<configuration>  
   <system.serviceModel>  
      <behaviors>   
          <serviceBehaviors>   
             <behavior name="CalculatorServiceBehavior" lockItem="true">   
               <serviceMetadata httpGetEnabled="True"/>   
               <serviceDebug includeExceptionDetailInFaults="False" />   
             </behavior>   
          </serviceBehaviors>   
       </behaviors>   
    </system.serviceModel>  
</configuration>  
```  
  
 Konfigurationselemente können individuell gesperrt werden.  Als Wert für `lockElements` kann eine Liste von Elementen festgelegt werden, um nur bestimmte Elemente innerhalb einer Auflistung von Unterelementen zu sperren.  Eine Liste an Attributen kann als Wert für `lockAttributes` festgelegt werden, um eine Menge an Attributen innerhalb eines Elements zu sperren.  Eine gesamte Auflistung an Elementen oder Attributen kann mit Ausnahme einer festgelegten Liste gesperrt werden, indem die Attribute `lockAllElementsExcept` oder `lockAllAttributesExcept` auf einem Knoten festgelegt werden.  
  
## Konfiguration von PII\-Protokollierung  
 Die Protokollierung von PII wird über zwei Schalter gesteuert: eine computerweite Einstellung in Machine.config, die es einem Computeradministrator ermöglicht, die Protokollierung von PII zu erlauben oder zu verweigern, und eine Anwendungseinstellung, die es einem Anwendungsadministrator ermöglicht, die Protokollierung von PII für jede Quelle in einer Web.config\- oder App.config\-Datei ein\- bzw. auszuschalten.  
  
 Die computerweite Einstellung wird in Machine.config im Abschnitt `enableLoggingKnownPii` mithilfe von `true` gesteuert, indem dieser Wert auf `false` oder `machineSettings` festgelegt wird.  Dass Anwendungen die Protokollierung von PII aktivieren wird beispielsweise folgendermaßen ermöglicht.  
  
```  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  Die Machine.config\-Datei hat einen Standardspeicherort: %WINDIR%\\Microsoft.NET\\Framework\\v2.0.50727\\CONFIG.  
  
 Ist das `enableLoggingKnownPii`\-Attribut nicht in "Machine.config" vorhanden, ist die Protokollierung von PII nicht zugelassen.  
  
 Die Aktivierung der Protokollierung von PII für eine Anwendung wird erreicht, indem man das `logKnownPii`\-Attribut des Quellelements in der Web.config\- oder App.config\-Datei auf `true` oder `false` festlegt.  Die Protokollierung von PII sowohl für Nachrichten\- als auch für Ablaufverfolgungsprotokollierung wird beispielsweise folgendermaßen aktiviert.  
  
```  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel.MessageLogging" logKnownPii="true">  
                <listeners>   
                ...   
                </listeners>  
            </source>  
            <source name="System.ServiceModel" switchValue="Verbose, ActivityTracing">  
            <listeners>  
        ...   
            </listeners>  
            </source>  
        </sources>  
    </system.diagnostics>  
</configuration>  
```  
  
 Wenn das `logKnownPii`\-Attribut nicht festgelegt ist, wird PII nicht protokolliert.  
  
 PII wird nur protokolliert, wenn sowohl `enableLoggingKnownPii` auf `true` und `logKnownPii` auf `true` festgelegt ist.  
  
> [!NOTE]
>  System.Diagnostics ignoriert alle Attribute auf allen Quellen, ausgenommen der zuerst in der Konfigurationsdatei aufgelisteten.  Das Hinzufügen des `logKnownPii`\-Attributs zur zweiten Quelle in der Konfigurationsdatei hat keine Auswirkungen.  
  
> [!IMPORTANT]
>  Die Ausführung dieses Beispiels erfordert die manuelle Änderung von "Machine.config".  Die Änderung von "Machine.config" sollte vorsichtig vorgenommen werden, da falsche Werte oder Syntax dazu führen können, dass die Ausführung aller .NET Framework\-Anwendungen verhindert wird.  
  
 Es ist auch möglich, Konfigurationsdateielemente mit DPAPI und RSA zu verschlüsseln.  Weitere Informationen finden Sie unter den folgenden Links:  
  
-   [Erstellen von Secure ASP.NET\-Anwendungen: Authentifizierung, Autorisierung und sichere Kommunikation](http://go.microsoft.com/fwlink/?LinkId=95137)  
  
-   [Gewusst wie: Verschlüsseln von Konfigurationsabschnitten in ASP.NET 2.0 mithilfe von RSA](http://go.microsoft.com/fwlink/?LinkId=95138)  
  
#### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Bearbeiten Sie "Machine.config", um das `enableLoggingKnownPii`\-Attribut auf `true` festzulegen, wobei Sie, falls notwendig, die übergeordneten Knoten hinzufügen.  
  
3.  Befolgen Sie zum Erstellen der C\#\- oder Visual Basic .NET\-Variante der Lösung die Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Wenn Sie das Beispiel in einer Einzelcomputer\- oder einer computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
#### So bereinigen Sie das Beispiel  
  
1.  Bearbeiten Sie Machine.config, und legen Sie `enableLoggingKnownPii`\-Attribut auf `false` fest.  
  
## Siehe auch  
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)