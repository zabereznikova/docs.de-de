---
title: Sperre der PII-Sicherheit
ms.date: 03/30/2017
ms.assetid: c44fb338-9527-4dd0-8607-b8787d15acb4
ms.openlocfilehash: ad4f4a024b04a028b815faedded58713e001cab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144265"
---
# <a name="pii-security-lockdown"></a>Sperre der PII-Sicherheit
In diesem Beispiel wird veranschaulicht, wie Sie mehrere sicherheitsrelevante Features eines Windows Communication Foundation (WCF)-Dienstes steuern, indem Sie:  
  
- Das Verschlüsseln von vertraulichen Informationen in der Konfigurationsdatei eines Diensts.  
  
- Das Sperren von Elementen in der Konfigurationsdatei, sodass geschachtelte Dienstunterverzeichnisse keine Einstellungen überschreiben können.  
  
- Die Steuerung der Protokollierung von personenbezogenen Informationen (PII) in Ablaufverfolgungs- und Nachrichtenprotokollen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\SecurityLockdown`  
  
## <a name="discussion"></a>Diskussion  
 Jede dieser Funktionen kann getrennt oder gemeinsam verwendet werden, um Aspekte einer Dienstsicherheit zu steuern. Dies ist kein endgültiger Leitfaden für die Sicherung eines WCF-Dienstes.  
  
 Die .NET Framework-Konfigurationsdateien können vertrauliche Informationen, wie beispielsweise Verbindungszeichenfolgen enthalten, um eine Verbindung mit Datenbanken herzustellen. In freigegebenen, im Internet gehosteten Szenarien kann es wünschenswert sein, diese Informationen in der Konfigurationsdatei für einen Dienst zu verschlüsseln, sodass die in der Konfigurationsdatei enthaltenen Daten gegen zufälliges Einsehen geschützt sind. .NET Framework 2.0 und höher kann Teile der Konfigurationsdatei mithilfe von Windows-DPAPI (Data Protection Application Programming Interface) oder dem RSA Cryptographic Provider verschlüsseln. Die Datei "aspnet_regiis.exe" kann mit DPAPI oder RSA ausgewählte Teile einer Konfigurationsdatei verschlüsseln.  
  
 In im Internet gehosteten Szenarien ist es möglich, Dienste in Unterverzeichnissen anderer Dienste zu haben. Die Standardsemantik für die Bestimmung von Konfigurationswerten ermöglicht es Konfigurationsdateien in den geschachtelten Verzeichnissen, die Konfigurationswerte im übergeordneten Verzeichnis zu überschreiben. In bestimmten Situationen kann dies aus verschiedenen Gründen unerwünscht sein. Die WCF-Dienstkonfiguration unterstützt das Sperren von Konfigurationswerten, sodass die verschachtelte Konfiguration Ausnahmen generiert, wenn ein verschachtelter Dienst mit überschriebenen Konfigurationswerten ausgeführt wird.  
  
 Dieses Beispiel veranschaulicht das Steuern der Protokollierung von bekannten personenbezogenen Informationen (PII, Personally Identifiable Information) in Ablaufverfolgungs- und Nachrichtenprotokollen, beispielsweise Benutzername und Kennwort. Standardmäßig ist die Protokollierung von bekannten PII deaktiviert. Allerdings kann in bestimmten Situationen die Protokollierung von PII beim Debuggen einer Anwendung wichtig sein. Dieses Beispiel basiert auf den [Ersten Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md). In diesem Beispiel werden außerdem Ablaufverfolgungs- und Nachrichtenprotokollierung verwendet. Weitere Informationen finden Sie im Beispiel [für Ablaufverfolgung und Nachrichtenprotokollierung.](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)  
  
## <a name="encrypting-configuration-file-elements"></a>Verschlüsseln von Konfigurationsdateielementen  
 Aus Sicherheitsgründen kann es in einer freigegebenen Webhostingumgebung wünschenswert sein, bestimmte Konfigurationselemente zu verschlüsseln, wie beispielsweise Datenbankverbindungszeichenfolgen, die vertrauliche Informationen enthalten. Ein Konfigurationselement kann mit dem Tool aspnet_regiis.exe verschlüsselt werden, das im Ordner .NET Framework gefunden wird, z. B. %WINDIR%-Microsoft.NET-Framework-v4.0.20728.  
  
#### <a name="to-encrypt-the-values-in-the-appsettings-section-in-webconfig-for-the-sample"></a>So verschlüsseln Sie die Werte im Abschnitt appSettings in Web.config für das Beispiel  
  
1. Öffnen Sie eine Eingabeaufforderung, indem Sie Start->Ausführen verwenden.... Geben `cmd` Sie ein, und klicken Sie auf **OK**.  
  
2. Navigieren Sie zum aktuellen .NET Framework-Verzeichnis, indem Sie folgenden Befehl ausgeben: `cd %WINDIR%\Microsoft.NET\Framework\v4.0.20728`.  
  
3. Verschlüsseln Sie die appSettings-Konfigurationseinstellungen im Web.config-Ordner, indem Sie folgenden Befehl ausgeben: `aspnet_regiis -pe "appSettings" -app "/servicemodelsamples" -prov "DataProtectionConfigurationProvider"`.  
  
 Weitere Informationen zum Verschlüsseln von Abschnitten von Konfigurationsdateien finden Sie unter lesen Sie ein How-to zu auf DPAPI in ASP.NET Konfiguration ([Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))) und ein How-to auf RSA in ASP.NET Konfiguration ( How[To: Encrypt Configuration Sections in ASP.NET 2.0 Using RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))).  
  
## <a name="locking-configuration-file-elements"></a>Sperren von Konfigurationsdateielementen  
 In im Internet gehosteten Szenarien ist es möglich, Dienste in Unterverzeichnissen von Diensten zu haben. In diesen Situationen werden die Konfigurationswerte für den Dienst im Unterverzeichnis berechnet durch die Überprüfung von Werten in "Machine.config", darauf folgendes Zusammenfügen mit Web.config-Dateien in übergeordneten Verzeichnissen im Verzeichnisbaum nach unten gehend sowie durch das Zusammenfügen der Web.config-Datei im Verzeichnis, das den Dienst enthält. Das Standardverhalten der meisten Konfigurationselemente besteht darin, zu erlauben, dass Konfigurationsdateien in Unterverzeichnissen die in den übergeordneten Verzeichnissen gesetzten Werte überschreiben. In bestimmten Situationen kann es erwünscht sein, dass die Konfigurationsdateien in den Unterverzeichnissen die in der Konfiguration des übergeordneten Verzeichnisses gesetzten Werte nicht überschreiben.  
  
 .NET Framework bietet eine Möglichkeit des Sperrens von Konfigurationsdateielementen, sodass Konfigurationen, die gesperrte Konfigurationselemente überschreiben, Laufzeitausnahmen auslösen.  
  
 Ein Konfigurationselement kann gesperrt werden, indem das `lockItem`-Attribut für einen Knoten in der Konfigurationsdatei festgelegt wird. Beispielsweise kann die folgende Konfiguration genutzt werden, um einen CalculatorServiceBehavior-Knoten zu sperren, sodass Rechnerdienste in geschachtelten Konfigurationsdateien das Verhalten nicht ändern können.  
  
```xml  
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
  
 Konfigurationselemente können individuell gesperrt werden. Als Wert für `lockElements` kann eine Liste von Elementen festgelegt werden, um nur bestimmte Elemente innerhalb einer Auflistung von Unterelementen zu sperren. Eine Liste an Attributen kann als Wert für `lockAttributes` festgelegt werden, um eine Menge an Attributen innerhalb eines Elements zu sperren. Eine gesamte Auflistung an Elementen oder Attributen kann mit Ausnahme einer festgelegten Liste gesperrt werden, indem die Attribute `lockAllElementsExcept` oder `lockAllAttributesExcept` auf einem Knoten festgelegt werden.  
  
## <a name="pii-logging-configuration"></a>Konfiguration von PII-Protokollierung  
 Die Protokollierung von PII wird über zwei Schalter gesteuert: eine computerweite Einstellung in Machine.config, die es einem Computeradministrator ermöglicht, die Protokollierung von PII zu erlauben oder zu verweigern, und eine Anwendungseinstellung, die es einem Anwendungsadministrator ermöglicht, die Protokollierung von PII für jede Quelle in einer Web.config- oder App.config-Datei ein- bzw. auszuschalten.  
  
 Die computerweite Einstellung wird `enableLoggingKnownPii` durch `true` `false`Festlegen auf `machineSettings` oder im Element in Machine.config gesteuert. Im Folgenden können Anwendungen z. B. die Protokollierung von PERSONENBEZOGENEn Daten aktivieren.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <machineSettings enableLoggingKnownPii="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
> Die Machine.config-Datei hat einen Standardspeicherort: %WINDIR%\Microsoft.NET\Framework\v2.0.50727\CONFIG.  
  
 Ist das `enableLoggingKnownPii`-Attribut nicht in "Machine.config" vorhanden, ist die Protokollierung von PII nicht zugelassen.  
  
 Die Aktivierung der Protokollierung von PII für eine Anwendung wird erreicht, indem man das `logKnownPii`-Attribut des Quellelements in der Web.config- oder App.config-Datei auf `true` oder `false` festlegt. Die Protokollierung von PII sowohl für Nachrichten- als auch für Ablaufverfolgungsprotokollierung wird beispielsweise folgendermaßen aktiviert.  
  
```xml  
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
  
 Wenn das `logKnownPii`-Attribut nicht festgelegt ist, wird PII nicht protokolliert.  
  
 PII wird nur protokolliert, wenn sowohl `enableLoggingKnownPii` auf `true` und `logKnownPii` auf `true` festgelegt ist.  
  
> [!NOTE]
> System.Diagnostics ignoriert alle Attribute auf allen Quellen, ausgenommen der zuerst in der Konfigurationsdatei aufgelisteten. Das Hinzufügen des `logKnownPii`-Attributs zur zweiten Quelle in der Konfigurationsdatei hat keine Auswirkungen.  
  
> [!IMPORTANT]
> Um dieses Beispiel auszuführen, wird Machine.config manuell geändert. Beim Ändern von Machine.config ist Vorsicht geboten, da falsche Werte oder Syntax die Ausführung aller .NET Framework-Anwendungen verhindern können.  
  
 Es ist auch möglich, Konfigurationsdateielemente mit DPAPI und RSA zu verschlüsseln. Weitere Informationen finden Sie unter den folgenden Links:  
  
- [Erstellen sicherer ASP.NET Anwendungen: Authentifizierung, Autorisierung und sichere Kommunikation](https://docs.microsoft.com/previous-versions/msp-n-p/ff649248(v=pandp.10))  
  
- [Gewusst wie: Verschlüsseln von Konfigurationsabschnitten in ASP.NET 2.0 mithilfe von RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Bearbeiten Sie "Machine.config", um das `enableLoggingKnownPii`-Attribut auf `true` festzulegen, wobei Sie, falls notwendig, die übergeordneten Knoten hinzufügen.  
  
3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
4. Um das Beispiel in einer Einzel- oder Computerkonfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
#### <a name="to-clean-up-the-sample"></a>So bereinigen Sie das Beispiel  
  
1. Bearbeiten Sie Machine.config, und legen Sie `enableLoggingKnownPii`-Attribut auf `false` fest.  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
