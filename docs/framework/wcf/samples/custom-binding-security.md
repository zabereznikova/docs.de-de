---
title: Sicherheit mit benutzerdefinierten Bindungen
ms.date: 03/30/2017
ms.assetid: a6383dff-4308-46d2-bc6d-acd4e18b4b8d
ms.openlocfilehash: eb575594cec9ea714578bc104344acc14b00e9df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592462"
---
# <a name="custom-binding-security"></a>Sicherheit mit benutzerdefinierten Bindungen

In diesem Beispiel wird veranschaulicht, wie die Sicherheitsfunktion mit einer benutzerdefinierten Bindung konfiguriert wird. Es zeigt, wie Sicherheit auf Nachrichtenebene und ein sicherer Transport mithilfe einer benutzerdefinierten Bindung aktiviert wird. Dies ist hilfreich, wenn ein sicherer Transport zum Übertragen von Nachrichten zwischen Client und Dienst erforderlich ist und daher die Nachrichten auf Nachrichtenebene gesichert werden müssen. Diese Konfiguration wird nicht von Bindungen unterstützt, die vom System bereitgestellt werden.

Dieses Beispiel besteht aus einem Clientkonsolenprogramm (EXE) und einem Dienstkonsolenprogramm (EXE). Der Dienst implementiert einen Duplexvertrag. Der Vertrag wird von der `ICalculatorDuplex`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht. Durch die `ICalculatorDuplex`-Schnittstelle kann der Client mathematische Operationen ausführen (Berechnen eines laufenden Ergebnisses über eine Sitzung). Unabhängig davon kann der Dienst Ergebnisse auf der `ICalculatorDuplexCallback`-Schnittstelle zurückgeben. Ein Duplexvertrag erfordert eine Sitzung, da ein Kontext eingerichtet werden muss, um die zwischen dem Client und dem Dienst gesendeten Nachrichten in Beziehung zu setzen. Es wird eine benutzerdefinierte Bindung definiert, die Duplexkommunikation unterstützt und sicher ist.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Die Dienstkonfiguration definiert eine benutzerdefinierte Bindung, die Folgendes unterstützt:

- TCP-Kommunikation mit Schutz durch Verwendung des TLS/SSL-Protokolls.

- Windows-Nachrichtensicherheit.

Durch die benutzerdefinierte Bindungskonfiguration wird der sichere Transport ermöglicht, da gleichzeitig die Sicherheit auf Nachrichtenebene aktiviert wird. Die Reihenfolge der Bindungs Elemente ist beim Definieren einer benutzerdefinierten Bindung wichtig, da jede eine Ebene im Kanal Stapel darstellt (siehe [benutzerdefinierte Bindungen](../extending/custom-bindings.md)). Die benutzerdefinierte Bindung wird in den Dienst- und Clientkonfigurationsdateien definiert, wie in der folgenden Beispielkonfiguration dargestellt.

```xml
<bindings>
  <!-- Configure a custom binding. -->
  <customBinding>
    <binding name="Binding1">
      <security authenticationMode="SecureConversation"
                 requireSecurityContextCancellation="true">
      </security>
      <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>
      <sslStreamSecurity requireClientCertificate="false"/>
      <tcpTransport/>
    </binding>
  </customBinding>
</bindings>
```

Die benutzerdefinierte Bindung verwendet ein Dienstzertifikat zum Authentifizieren des Diensts auf Transportebene und zum Sichern der Nachrichten während der Übertragung zwischen Client und Dienst. Dies wird durch das `sslStreamSecurity`-Bindungselement umgesetzt. Das Zertifikat des Diensts wird mit einem Dienstverhalten konfiguriert, wie in der folgenden Beispielkonfiguration dargestellt.

```xml
<behaviors>
    <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
        <serviceMetadata />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>
        </serviceCredentials>
    </behavior>
    </serviceBehaviors>
</behaviors>
```

Außerdem verwendet die benutzerdefinierte Bindung Nachrichtensicherheit mit dem Windows-Anmeldeinformationstyp. Dies ist der Standard-Anmeldeinformationstyp. Dies wird durch das `security`-Bindungselement umgesetzt. Sowohl der Client als auch der Dienst werden mithilfe von Sicherheitsfunktionen auf Nachrichtenebene authentifiziert, wenn der Kerberos-Authentifizierungsmechanismus verfügbar ist. Dies geschieht, wenn das Beispiel in der Active Directory-Umgebung ausgeführt wird. Ist der Kerberos-Authentifizierungsmechanismus nicht verfügbar, wird die NTLM-Authentifizierung verwendet. NTLM authentifiziert den Client für den Dienst, authentifiziert aber nicht den Dienst für den Client. Das `security` Bindungs Element ist für die Verwendung `SecureConversation` `authenticationType` von konfiguriert, was zur Erstellung einer Sicherheits Sitzung auf dem Client und dem Dienst führt. Dies ist erforderlich, damit der Duplexvertrag des Diensts funktioniert.

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Konsolenfenster des Clients angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

```console
Press <ENTER> to terminate client.
Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

Wenn Sie das Beispiel ausführen, werden die vom Client zurückgegebenen Nachrichten in der vom Dienst gesendeten Rückrufschnittstelle angezeigt. Alle Zwischenergebnisse werden angezeigt, gefolgt von der ganzen Formel nach Abschluss aller Vorgänge. Drücken Sie die EINGABETASTE, um den Client zu schließen.

Mit der in diesem Beispiel enthaltenen Datei Setup.bat können Sie Client und Server mit relevanten Dienstzertifikaten zum Ausführen einer gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert. Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.

Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien für dieses Beispiel, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden:

- Erstellen des Serverzertifikats.

  Mit den folgenden Zeilen aus der Datei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt. Die Variable `%SERVER_NAME%` gibt den Servernamen an. Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an. In dieser Batchdatei ist der Servername standardmäßig auf localhost festgelegt.

  Das Zertifikat wird im Speicher CurrentUser für im Internet gehostete Dienste gespeichert.

  ```bat
  echo ************
  echo Server cert setup starting
  echo %SERVER_NAME%
  echo ************
  echo making server cert
  echo ************
  makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
  ```

- Installieren Sie das Serverzertifikat im Speicher für vertrauenswürdige Zertifikate des Clients.

  Mit den folgenden Zeilen in der Datei "Setup.bat" wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.

  ```console
  certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
  ```

  > [!NOTE]
  > Die Batchdatei Setup.bat ist darauf ausgelegt, an einer Visual Studio-Eingabeaufforderung (2010) ausgeführt zu werden. Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist. Diese Umgebungsvariable ist innerhalb einer Visual Studio-Eingabeaufforderung (2010) automatisch festgelegt.

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.

3. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus

1. Öffnen Sie eine Developer-Eingabeaufforderung für das Visual Studio-Fenster mit Administratorrechten, und führen Sie Setup. bat aus dem Beispiel Installationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.

    > [!NOTE]
    > Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie über eine Visual Studio 2012-Eingabeaufforderung ausgeführt wird. Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Skript "Setup. bat" erforderlich sind.

2. Starten Sie Service.exe aus dem Ordner \service\bin.

3. Starten Sie Client.exe aus dem Ordner \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.

4. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.

### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus

1. Auf dem Dienstcomputer:

    1. Erstellen Sie auf dem Dienstcomputer ein virtuelles Verzeichnis mit dem Namen servicemodelsamples.

    2. Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer. Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren.

    3. Kopieren Sie die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.

    4. Führen Sie den folgenden Befehl in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde: `Setup.bat service` . Hiermit wird das Dienstzertifikat erstellt, dessen Antragstellername mit dem Namen des Computers übereinstimmt, auf dem die Batchdatei ausgeführt wurde.

        > [!NOTE]
        > Die Batchdatei Setup.bat ist darauf ausgelegt, an einer Visual Studio-Eingabeaufforderung (2010) ausgeführt zu werden. Die PATH-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist. Diese Umgebungsvariable ist innerhalb einer Visual Studio-Eingabeaufforderung (2010) automatisch festgelegt.

    5. Ändern [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) Sie in der Datei Service. exe. config den Antragsteller Namen des Zertifikats, das Sie im vorherigen Schritt generiert haben.

    6. Führen Sie Service.exe an einer Eingabeaufforderung aus.

2. Auf dem Clientcomputer:

    1. Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ auf den Clientcomputer. Kopieren Sie auch die Datei Cleanup.bat.

    2. Führen Sie Cleanup.bat aus, um alte Zertifikate aus vorherigen Beispielen zu entfernen.

    3. Exportieren Sie das Zertifikat des Diensts, indem Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten öffnen und den folgenden Befehl auf dem Dienstcomputer ausführen (ersetzen Sie durch `%SERVER_NAME%` den voll qualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird):

        ```console
        certmgr -put -r LocalMachine -s My -c -n %SERVER_NAME% %SERVER_NAME%.cer
        ```

    4. Kopieren Sie %SERVER_NAME%.cer auf den Clientcomputer (ersetzen Sie %SERVER_NAME% durch den vollqualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird).

    5. Importieren Sie das Dienst Zertifikat, indem Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten öffnen und den folgenden Befehl auf dem Client Computer ausführen (ersetzen Sie% server_name% durch den voll qualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird):

        ```console
        certmgr.exe -add -c %SERVER_NAME%.cer -s -r CurrentUser TrustedPeople
        ```

        Die Schritte c, d und e sind nicht erforderlich, wenn das Zertifikat von einem vertrauenswürdigen Aussteller stammt.

    6. Ändern Sie die Datei App.config des Clients wie folgt:

        ```xml
        <client>
            <endpoint name="default"
                address="net.tcp://ReplaceThisWithServiceMachineName:8000/ServiceModelSamples/Service"
                binding="customBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex"
                behaviorConfiguration="CalculatorClientBehavior" />
        </client>
        ```

    7. Wenn der Dienst unter einem anderen Konto als NetworkService oder LocalSystem in einer Domänenumgebung ausgeführt wird, müssen Sie möglicherweise die Endpunktidentität für den Dienstendpunkt in der Datei App.config des Clients ändern und den entsprechenden UPN oder SPN für das Konto angeben, unter dem der Dienst ausgeführt wird. Weitere Informationen zur Endpunkt Identität finden Sie im Thema [Dienst Identität und Authentifizierung](../feature-details/service-identity-and-authentication.md) .

    8. Führen Sie an einer Eingabeaufforderung Client.exe aus.

### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her

- Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.
