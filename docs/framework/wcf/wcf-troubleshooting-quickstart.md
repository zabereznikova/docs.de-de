---
title: Schnelleinstieg zur Problembehandlung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
ms.openlocfilehash: f85d37fde19767d7fd1e3002776b4816666cc7e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183053"
---
# <a name="wcf-troubleshooting-quickstart"></a>Schnelleinstieg zur Problembehandlung in WCF
In diesem Thema wird eine Reihe bekannter Probleme aufgeführt, denen Kunden beim Entwickeln von WCF-Clients und -Diensten begegnet sind. Wenn Ihr spezifisches Problem nicht in dieser Liste enthalten ist, sollten Sie die Ablaufverfolgung für den Dienst konfigurieren. Dadurch wird eine Ablaufverfolgungsdatei generiert, die Sie im Ablaufverfolgungsdatei-Viewer anzeigen können, um detaillierte Informationen zu Ausnahmen im Dienst zu erhalten. Weitere Informationen zum Konfigurieren der Ablaufverfolgung finden Sie unter [Configuring Tracing](./diagnostics/tracing/configuring-tracing.md). Weitere Informationen zum Ablaufverfolgungsdatei-Viewer finden Sie unter [Service Trace Viewer Tool (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md).  
  
1. [Wenn ich nach dem Installieren von Windows 7 und IIS versuche, auf einen WCF-Dienst zuzugreifen, erhalte ich die folgende Fehlermeldung: HTTP-Fehler 404.3 – Nicht gefunden.](#bkmk_0)  
  
     HTTP Fehler 404.3 – Nicht gefunden. Die angeforderte Seite kann aufgrund einer Konfigurationserweiterung nicht angezeigt werden. Wenn es sich bei der Seite um ein Skript handelt, müssen Sie einen Handler hinzufügen. Wenn die Datei heruntergeladen werden soll, müssen Sie eine MIME-Zuordnung hinzufügen. Detaillierte Fehlerinformationen finden Sie unter dem Modul StaticFileModule.  
  
2. [Manchmal erhalte ich eine MessageSecurityException für die zweite Anforderung, wenn sich mein Client nach der ersten Anforderung für eine Weile im Leerlauf befindet. Was passiert?](#BKMK_q1)  
  
3. [Mein Dienst beginnt, neue Clients abzulehnen, nachdem etwa 10 Clients mit ihm interagieren. Was passiert?](#BKMK_q2)  
  
4. [Kann ich die Dienstkonfiguration aus einer anderen Quelle laden als der Konfigurationsdatei der WCF-Anwendung?](#BKMK_q3)  
  
5. [Mein Dienst und Mein Client funktionieren hervorragend, aber ich kann sie nicht dazu bringen, zu arbeiten, wenn sich der Client auf einem anderen Computer befindet? Was passiert?](#BKMK_q4)  
  
6. [Wenn ich eine\<FaultException-Ausnahme auslösen>, bei der der Typ eine Ausnahme ist, erhalte ich immer einen allgemeinen FaultException-Typ auf dem Client und nicht den generischen Typ. Was passiert?](#BKMK_q5)  
  
7. [Es scheint, als ob einwegige und Anforderungs-Antwort-Vorgänge mit ungefähr der gleichen Geschwindigkeit zurückkehren, wenn die Antwort keine Daten enthält. Was passiert?](#BKMK_q6)  
  
8. [Ich verwende ein X.509-Zertifikat mit meinem Dienst und erhalte eine System.Security.Cryptography.CryptographicException. Was passiert?](#BKMK_q77)  
  
9. [Ich habe den ersten Parameter einer Operation von Groß- in Kleinbuchstaben geändert; Jetzt löst mein Client eine Ausnahme aus. Was passiert?](#BKMK_q88)  
  
10. [Ich verwende eines meiner Ablaufverfolgungstools und erhalte eine EndpointNotFoundException. Was passiert?](#BKMK_q99)  
  
11. [Beim Aufruf einer WCF-Web HTTP-Anwendung aus einer WCF-SOAP-Anwendung gibt der Dienst die folgende Fehlermeldung zurück: 405 "Method Not Allowed"](#BK_MK99)  
  
 [Was ist die Basisadresse? In wie steht es zu einer Endpunktadresse?](#BKMK_q10)  
  
<a name="bkmk_0"></a>
## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a>Wenn ich nach dem Installieren von Windows 7 und IIS versuche, auf einen WCF-Dienst zuzugreifen, erhalte ich die folgende Fehlermeldung: HTTP-Fehler 404.3 – Nicht gefunden.  
 Die vollständige Fehlermeldung lautet:  
  
 HTTP Fehler 404.3 – Nicht gefunden. Die angeforderte Seite kann aufgrund einer Konfigurationserweiterung nicht angezeigt werden. Wenn es sich bei der Seite um ein Skript handelt, müssen Sie einen Handler hinzufügen. Wenn die Datei heruntergeladen werden soll, müssen Sie eine MIME-Zuordnung hinzufügen. Detaillierte Fehlerinformationen finden Sie unter dem Modul StaticFileModule.  
  
 Diese Fehlermeldung tritt auf, wenn "Windows Communication Foundation HTTP Activation" nicht explizit in der Systemsteuerung festgelegt ist. Um dies festzulegen, klicken Sie in der unteren linken Ecke des Fensters auf Programme. Klicken Sie auf "Windows-Funktionen ein- oder ausschalten". Erweitern Sie "Microsoft .NET Framework 3.5.1", und wählen Sie "Windows Communication Foundation-Http-Aktivierung" aus.  
  
<a name="BKMK_q1"></a>
## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a>Manchmal wird eine MessageSecurityException bei der zweiten Anforderung ausgelöst, wenn sich der Client nach der ersten Anforderung eine Weile im Leerlauf befunden hat. Was passiert?  
 Die zweite Anforderung kann in erster Linie aus zwei Gründen fehlschlagen: (1) Das Timeout der Sitzung wurde überschritten. (2) Der Webserver, der diesen Dienst hostet, wird wiederverwendet. Im ersten Fall ist die Sitzung gültig, bis der Dienst ein Zeitvertreib hat. Wenn der Dienst innerhalb des in der Bindung des Dienstes angegebenen Zeitraums<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>( ) keine Anforderung vom Client empfängt, beendet der Dienst die Sicherheitssitzung. Nachfolgende Clientnachrichten führen zu <xref:System.ServiceModel.Security.MessageSecurityException>. Der Code muss erneut eine Sicherheitssitzung mit dem Dienst herstellen, um weitere Nachrichten senden oder ein Token für den Sicherheitszustandskontext verwenden zu können. Token für den Sicherheitszustandskontext sorgen auch dafür, dass eine Sicherheitssitzung das Wiederverwenden eines Webservers überdauert. Weitere Informationen zur Verwendung zustandsbehafteter sicherer Kontexttoken in einer sicheren Sitzung finden Sie unter [Gewusst wie: Erstellen eines Sicherheitskontexttokens für eine sichere Sitzung](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md). Stattdessen können Sie Sicherheitssitzungen auch deaktivieren. Wenn Sie [ \<die-Bindung>](../configure-apps/file-schema/wcf/wshttpbinding.md) verwenden, können `establishSecurityContext` Sie `false` die Eigenschaft so festlegen, dass sichere Sitzungen deaktiviert werden. Wenn Sie Sicherheitssitzungen für andere Bindungen deaktivieren möchten, müssen Sie eine benutzerdefinierte Bindung erstellen. Ausführliche Informationen zum Erstellen einer benutzerdefinierten Bindung finden Sie unter [How to: Create a Custom Binding Using the SecurityBindingElement](./feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md). Bevor Sie eine dieser Optionen anwenden, müssen Sie die Sicherheitsanforderungen der Anwendung kennen.  
  
<a name="BKMK_q2"></a>
## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a>Der Dienst lehnt nach einer Interaktion mit ungefähr 10 Clients weitere Clients ab. Was passiert?  
 Standardmäßig können Dienste nur 10 Sitzungen gleichzeitig verarbeiten. Wenn die Dienstbindungen Sitzungen verwenden, akzeptiert der Dienst neue Clientverbindungen folglich, bis diese Zahl erreicht ist. Anschließend lehnt er neue Clientverbindungen ab, bis eine der aktuellen Sitzungen beendet wird. Es gibt verschiedene Möglichkeiten, mehr Clients zu unterstützen. Wenn der Dienst keine Sitzungen erfordert, verwenden Sie keine sitzungsbasierte Bindung. (Weitere Informationen finden Sie unter [Verwenden von Sitzungen](using-sessions.md).) Eine weitere Möglichkeit besteht darin, das Sitzungslimit zu erhöhen, indem Sie den Wert der <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> Eigenschaft in die Anzahl ändern, die Ihren Umständen entspricht.  
  
<a name="BKMK_q3"></a>
## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a>Kann ich die Dienstkonfiguration aus einer anderen Quelle laden als der Konfigurationsdatei der WCF-Anwendung?  
 Ja. Sie müssen jedoch eine benutzerdefinierte <xref:System.ServiceModel.ServiceHost> -Klasse erstellen, die die <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> -Methode überschreibt. In dieser Methode können Sie die Basisklasse aufrufen und zuerst die Konfiguration laden (wenn Sie die Standardkonfigurationsinformationen ebenfalls laden möchten). Sie können jedoch auch das gesamte Konfigurationsladesystem ersetzen. Wenn Sie die Konfiguration aus einer Konfigurationsdatei laden möchten, die sich von der Anwendungskonfigurationsdatei unterscheidet, müssen Sie die Konfigurationsdatei selbst analysieren und die Konfiguration laden.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> -Methode überschrieben und ein Endpunkt direkt konfiguriert wird.  
  
```csharp
public class MyServiceHost : ServiceHost  
{  
    public MyServiceHost(Type serviceType, params Uri[] baseAddresses)
      : base(serviceType, baseAddresses)  
    {
        Console.WriteLine("MyServiceHost Constructor");
    }  
  
    protected override void ApplyConfiguration()  
    {  
        string straddress = GetAddress();  
        Uri address = new Uri(straddress);  
        Binding binding = GetBinding();  
        base.AddServiceEndpoint(typeof(IData), binding, address);  
    }  
  
    string GetAddress()  
    {
        return "http://MyMachine:7777/MyEndpointAddress/";
    }  
  
    Binding GetBinding()  
    {  
        WSHttpBinding binding = new WSHttpBinding();  
        binding.Security.Mode = SecurityMode.None;  
        return binding;  
    }  
}  
```  
  
<a name="BKMK_q4"></a>
## <a name="my-service-and-client-work-great-but-i-cant-get-them-to-work-when-the-client-is-on-another-computer-whats-happening"></a>Dienst und Client funktionieren hervorragend, nicht jedoch, wenn sich der Client auf einem anderen Computer befindet. Woran liegt das?  
 Je nach Ausnahme können verschiedene Probleme vorliegen:  
  
- Möglicherweise müssen Sie die Clientendpunktadressen von localhost auf den Hostnamen ändern.  
  
- Sie müssen gegebenenfalls den Anschluss zur Anwendung öffnen. Weitere Informationen finden Sie unter [Firewall Instructions](./samples/firewall-instructions.md) in den SDK-Beispielen.  
  
- Weitere mögliche Probleme finden Sie im Beispielthema [Ausführen der Windows Communication Foundation-Beispiele](./samples/running-the-samples.md).  
  
- Wenn der Client Windows-Anmeldeinformationen verwendet und es sich bei der Ausnahme um <xref:System.ServiceModel.Security.SecurityNegotiationException>handelt, konfigurieren Sie Kerberos wie folgt.  
  
    1. Fügen Sie die Anmeldeinformationen für die Identität dem Endpunktelement in der Datei App.config des Clients hinzu:  
  
        ```xml
        <endpoint
          address="http://MyServer:8000/MyService/"
          binding="wsHttpBinding"
          bindingConfiguration="WSHttpBinding_IServiceExample"
          contract="IServiceExample"
          behaviorConfiguration="ClientCredBehavior"
          name="WSHttpBinding_IServiceExample">  
          <identity>  
            <userPrincipalName value="name@corp.contoso.com"/>  
          </identity>  
        </endpoint>  
        ```  
  
    2. Führen Sie den selbst gehosteten Dienst unter dem System- oder dem Netzwerkdienstkonto aus. Sie können diesen Befehl ausführen, um unter dem Systemkonto ein Befehlsfenster zu erstellen:  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3. Hosten Sie den Dienst unter Internetinformationsdienste (IIS). Standardmäßig wird hier das Dienstprinzipalnamenkonto verwendet.  
  
    4. Registrieren Sie mit SetSPN einen neuen Dienstprinzipalnamen bei der Domäne. Dazu müssen Sie Domänenadministrator sein.  
  
 Weitere Informationen zum Kerberos-Protokoll finden [Sie unter Sicherheitskonzepte, die in WCF verwendet werden,](./feature-details/security-concepts-used-in-wcf.md) und:  
  
- [Debuggen von Windows-Authentifizierungsfehlern](./feature-details/debugging-windows-authentication-errors.md)  
  
- [Registrieren von Kerberos-Dienstprinzipalnamen mithilfe von HTTP.SYS.](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms178119(v=sql.105))  
  
- [Informationen zu Kerberos](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/bb742516(v%3dtechnet.10))  
  
<a name="BKMK_q5"></a>
## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a>Wenn ich eine\<FaultException-Ausnahme auslösen>, bei der der Typ eine Ausnahme ist, erhalte ich immer einen allgemeinen FaultException-Typ auf dem Client und nicht den generischen Typ. Woran liegt das?  
 Erstellen Sie unbedingt einen eigenen benutzerdefinierten Fehlerdatentyp und deklarieren Sie ihn als Detailtyp in ihrem Fehlervertrag. Das Problem entsteht, weil Folgendes geschieht, wenn vom System bereitgestellter Ausnahmetypen verwendet werden:  
  
- Eine Typabhängigkeit wird erstellt, die eine der größten Stärken dienstorientierter Anwendungen entfernt.  
  
- Ausnahmen werden nicht notwendigerweise standardmäßig serialisiert. Einige – wie <xref:System.Security.SecurityException>– sind vielleicht überhaupt nicht serialisierbar.  
  
- Interne Implementierungsdetails werden für Clients verfügbar gemacht. Weitere Informationen finden Sie unter [Angeben und Behandeln von Fehlern in Verträgen und Dienstleistungen](specifying-and-handling-faults-in-contracts-and-services.md).  
  
 Wenn Sie eine Anwendung debuggen, können Sie jedoch mit der <xref:System.ServiceModel.Description.ServiceDebugBehavior> -Klasse Ausnahmeinformationen serialisieren und an den Client zurückgeben.  
  
<a name="BKMK_q6"></a>
## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a>Unidirektionale und Anforderung-Antwort-Vorgänge scheinen nahezu mit der gleichen Geschwindigkeit zurückgegeben zu werden, wenn die Antwort keine Daten enthält. Woran liegt das?  
 Einen Vorgang als unidirektional anzugeben, bedeutet, dass der Vorgangsvertrag lediglich eine Eingabenachricht akzeptiert und keine Ausgabenachricht zurückgibt. In WCF werden alle Clientaufrufe zurückgegeben, wenn die ausgehenden Daten in den Draht geschrieben wurden oder eine Ausnahme ausgelöst wird. Unidirektionale Vorgänge funktionieren genauso. Außerdem können sie eine Ausnahme auslösen, falls der Dienst nicht gefunden wird, oder sie können blockiert werden, falls der Dienst nicht zur Annahme der Daten aus dem Netzwerk bereit ist. In der Regel führt dies in WCF dazu, dass unwegsame Aufrufe schneller an den Client zurückgegeben werden als Anforderungsantworten. Jedoch verlangsamt jede Bedingung, die das Senden der ausgehenden Daten über das Netzwerk verlangsamt, unidirektionazige Vorgänge sowie Anforderungs-Antwort-Vorgänge. Weitere Informationen finden Sie unter Einwegdienste und [Zugriff auf Dienste mithilfe eines WCF-Clients](./feature-details/accessing-services-using-a-client.md). [One-Way Services](./feature-details/one-way-services.md)  
  
<a name="BKMK_q77"></a>
## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a>Ich verwende ein X.509-Zertifikat mit dem Dienst und erhalte eine System.Security.Cryptography.CryptographicException. Woran liegt das?  
 Das Problem tritt in der Regel nach einer Änderung des Benutzerkontos auf, unter dem der IIS-Arbeitsprozess ausgeführt wird. Wenn Sie beispielsweise in Windows XP das Standardbenutzerkonto ändern, unter dem Aspnet_wp.exe von ASPNET ausgeführt wird, in ein benutzerdefiniertes Benutzerkonto, wird dieser Fehler möglicherweise angezeigt. Bei der Verwendung eines privaten Schlüssels benötigt der entsprechende Prozess die Berechtigungen für den Zugriff auf die Datei, in der der Schlüssel gespeichert ist.  
  
 In diesem Fall müssen Sie dem Konto des Prozesses Leseberechtigungen für die Datei mit dem Schlüssel erteilen. Wenn z. B. der IIS-Arbeitsprozess unter dem Konto Bob ausgeführt wird, müssen Sie Bob den Lesezugriff auf die Datei erteilen, die den privaten Schlüssel enthält.  
  
 Weitere Informationen dazu, wie Sie dem richtigen Benutzerkonto Zugriff auf die Datei gewähren, die den privaten Schlüssel für ein bestimmtes X.509-Zertifikat enthält, finden Sie unter [Gewusst wie: Machen Sie X.509-Zertifikate für WCF zugänglich.](./feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md)  
  
<a name="BKMK_q88"></a>
## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a>Ich habe den ersten Parameter eines Vorgangs von Groß- in Kleinbuchstaben geändert, und der Client löst nun eine Ausnahme aus. Woran liegt das?  
 Die Werte der Parameternamen in der Vorgangssignatur sind Teil des Vertrags und berücksichtigen die Groß-/Kleinschreibung. Verwenden Sie das <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> -Attribut, wenn der lokale Parametername von den Metadaten unterschieden werden muss, die den Vorgang für Clientanwendungen beschreiben.  
  
<a name="BKMK_q99"></a>
## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a>Bei der Verwendung eines meiner Ablaufverfolgungstools wird EndpointNotFoundException ausgelöst. Woran liegt das?  
 Wenn Sie ein Ablaufverfolgungstool verwenden, das nicht der vom System <xref:System.ServiceModel.EndpointNotFoundException> bereitgestellte WCF-Ablaufverfolgungsmechanismus ist, und <xref:System.ServiceModel.Description.ClientViaBehavior> Sie einen erhalten, der darauf hinweist, dass ein Adressfilternichtstimmt war, müssen Sie die Klasse verwenden, um die Nachrichten an das Ablaufverfolgungsdienstprogramm weiterzuleiten, und das Dienstprogramm diese Nachrichten an die Dienstadresse umleiten lassen. Die <xref:System.ServiceModel.Description.ClientViaBehavior> -Klasse ändert den Adressierungsheader `Via` und gibt die nächste Netzwerkadresse unabhängig vom endgültigen Empfänger an, der mit dem Adressierungsheader `To` angegeben wird. Ändern Sie dabei jedoch nicht die Endpunktadresse, die den `To` -Wert festlegt.  
  
 Das folgende Codebeispiel zeigt eine standardmäßige Konfigurationsdatei für einen Beispielclient.  
  
```xml
<endpoint
  address="http://localhost:8000/MyServer/"  
  binding="wsHttpBinding"  
  bindingConfiguration="WSHttpBinding_IMyContract"  
  behaviorConfiguration="MyClient"
  contract="IMyContract"
  name="WSHttpBinding_IMyContract">  
</endpoint>  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="MyClient">  
      <clientVia viaUri="http://localhost:8001/MyServer/"/>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
<a name="BKMK_q10"></a>
## <a name="what-is-the-base-address-how-does-it-relate-to-an-endpoint-address"></a>Was ist die Basisadresse? Worin besteht die Beziehung zu einer Endpunktadresse?  
 Eine Basisadresse ist die Stammadresse für eine <xref:System.ServiceModel.ServiceHost> -Klasse. Wenn Sie der Dienstkonfiguration eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior> -Klasse hinzufügen, werden standardmäßig die WSDL (Web Services Description Language) für alle vom Host veröffentlichten Endpunkte aus der HTTP-Basisadresse und alle relativen Adressen, die für das Metadatenverhalten bereitgestellt werden, sowie "?wsdl" abgerufen. Wenn Sie mit ASP.NET und IIS vertraut sind, entspricht die Basisadresse dem virtuellen Verzeichnis.  
  
## <a name="sharing-a-port-between-a-service-endpoint-and-a-mex-endpoint-using-the-nettcpbinding"></a>Gemeinsames Verwenden eines Ports durch einen Dienstendpunkt und einen mex-Endpunkt mithilfe der NetTcpBinding  
 Wenn Sie die Basisadresse für einen Dienst als net.tcp://MyServer:8080/MyService angeben und die folgenden Endpunkte hinzufügen:  
  
```xml  
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
 Und wenn Sie eine der NetTcpBinding-Einstellungen wie im folgenden Konfigurationsausschnitt veranschaulicht ändern:  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="10" maxBufferPoolSize="524288" maxBufferSize="65536" maxConnections="11" maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384"/>  
      <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false"/>  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign"/>  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 Ein Fehler ähnlich dem folgenden wird angezeigt: Unbehandelte Ausnahme: System.ServiceModel.AddressAlreadyInUseException: Für den IP-Endpunkt 0.0.0.0:9000 ist bereits ein Listener vorhanden. Sie können diesen Fehler beheben, indem Sie eine vollqualifizierte URL mit einem anderen Port für den MEX-Endpunkt angeben. Dies wird im folgenden Konfigurationsausschnitt veranschaulicht:  
  
```xml
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="net.tcp://localhost:9001/servicemodelsamples/mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
<a name="BK_MK99"></a>
## <a name="when-calling-a-wcf-web-http-application-from-a-wcf-soap-application-the-service-returns-the-following-error-405-method-not-allowed"></a>Beim Aufruf einer WCF-Web HTTP-Anwendung aus einer WCF-SOAP-Anwendung gibt der Dienst die folgende Fehlermeldung zurück: 405 "Method Not Allowed"  
 Das Aufrufen einer WCF-WebHTTP-Anwendung <xref:System.ServiceModel.WebHttpBinding> <xref:System.ServiceModel.Description.WebHttpBehavior>(ein Dienst, der den and ``Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: The remote server returned an unexpected response: (405) Method Not Allowed.`` verwendet) von einem WCF-Dienst kann die folgende Ausnahme generieren: Diese Ausnahme tritt auf, weil WCF die ausgehende <xref:System.ServiceModel.OperationContext> mit der eingehenden <xref:System.ServiceModel.OperationContext>überschreibt. Um dieses Problem zu <xref:System.ServiceModel.OperationContextScope> beheben, erstellen Sie einen WCF-WebHTTP-Dienstvorgang. Beispiel:  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Windows-Authentifizierungsfehlern](./feature-details/debugging-windows-authentication-errors.md)
