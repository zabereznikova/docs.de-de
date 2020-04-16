---
title: Bereitstellen eines IIS-gehosteten WCF-Diensts
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 67f6877546951bd92b235218f10f6ccc7011ef5c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463852"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts

Das Entwickeln und Bereitstellen eines WCF-Dienstes (Windows Communication Foundation), der in Internetinformationsdiensten (Internet Information Services, IIS) gehostet wird, umfasst die folgenden Aufgaben:

- Stellen Sie sicher, dass IIS, ASP.NET, WCF und die WCF-Aktivierungskomponente ordnungsgemäß installiert und registriert sind.

- Erstellen Sie eine neue IIS-Anwendung, oder verwenden Sie eine vorhandene ASP.NET Anwendung.

- Erstellen Sie eine .svc-Datei für den WCF-Dienst.

- Bereitstellen der Dienstimplementierung für die IIS-Anwendung.

- Konfigurieren Sie den WCF-Dienst.

Ausführliche Informationen zum Erstellen eines von IIS gehosteten WCF-Dienstes finden Sie unter [Gewusst wie: Hosten eines WCF-Dienstes in IIS](how-to-host-a-wcf-service-in-iis.md).

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Sicherstellen, dass IIS, ASP.NET und WCF ordnungsgemäß installiert und registriert sind

WCF- und IIS-ASP.NET müssen installiert sein, damit die von IIS gehosteten WCF-Dienste ordnungsgemäß funktionieren. Die Verfahren zum Installieren von WCF (als Teil von .NET Framework), ASP.NET und IIS variieren je nach Betriebssystem. Weitere Informationen zum Installieren von WCF und .NET Framework finden Sie unter [Installieren von .NET Framework für Entwickler](../../install/guide-for-developers.md). Um IIS unter Windows 10 zu installieren, öffnen Sie **Programme und Features** in der **Systemsteuerung,** und wählen Sie dann **Windows-Features ein- oder ausschalten**aus. Wählen Sie in **Windows-Features** **Internetinformationsdienste** aus, und wählen Sie dann **OK**aus.

![Windows-Features mit IIS hervorgehoben](./media/windows-features-iis.png)

Anweisungen zum Installieren von IIS auf anderen Betriebssystemen finden Sie unter Installieren von [IIS unter Windows Vista und Windows 7](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7) und Installieren von [IIS 8.5 unter Windows Server 2012 R2](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2).

Der Installationsvorgang für .NET Framework registriert WCF automatisch bei IIS, wenn IIS bereits auf dem Computer vorhanden ist. Wenn IIS nach .NET Framework installiert wird, ist ein zusätzlicher Schritt erforderlich, um WCF bei IIS und ASP.NET zu registrieren. Gehen Sie hierzu je nach Betriebssystem wie folgt vor:

- Windows 7 und Windows Server 2003: Verwenden Sie das [ServiceModel-Registrierungstool (ServiceModelReg.exe),](../../../../docs/framework/wcf/servicemodelreg-exe.md) um WCF bei IIS zu registrieren. Um dieses Tool zu verwenden, geben Sie **ServiceModelReg.exe /i /x** in die [Developer-Eingabeaufforderung für Visual Studio ein.](../../tools/developer-command-prompt-for-vs.md)

- Windows 7: Schließlich müssen Sie überprüfen, ob ASP.NET für die Verwendung von .NET Framework Version 4 oder höher konfiguriert ist. Dazu führen Sie das ASPNET_Regiis-Tool mit der `–i` Option aus. Weitere Informationen finden Sie [unter ASP.NET IIS-Registrierungstool](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90)).

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen ASP.NET-Anwendung

IIS-gehostete WCF-Dienste müssen sich innerhalb einer IIS-Anwendung befinden. Sie können eine neue IIS-Anwendung erstellen, um WCF-Dienste ausschließlich zu hosten. Alternativ können Sie einen WCF-Dienst in einer vorhandenen Anwendung bereitstellen, die bereits ASP.NET 2.0-Inhalten hostet (z. B. ASPX-Seiten und ASP.NET Webdienste [ASMX]). Weitere Informationen zu diesen Optionen finden Sie in den Abschnitten "Hosten von WCF Side-by-Side with ASP.NET" und "Hosting WCF Services in ASP.NET Compatibility Mode" in [WCF Services und ASP.NET](wcf-services-and-aspnet.md).

Beachten Sie, dass IIS 6.0 und neuere Versionen eine isolierte objektorientierte Programmieranwendung regelmäßig neu starten. Der Standardwert ist 1740 Minuten. Der höchstmögliche Wert sind 71.582 Minuten. Dieser Neustart kann deaktiviert werden. Weitere Informationen zu dieser Eigenschaft finden Sie unter [PeriodicRestartTime](https://docs.microsoft.com/previous-versions/iis/6.0-sdk/ms525914(v=vs.90)).

## <a name="create-an-svc-file-for-the-wcf-service"></a>Erstellen einer SVC-Datei für den WCF-Dienst

In IIS gehostete WCF-Dienste werden als spezielle Inhaltsdateien (.svc-Dateien) innerhalb der IIS-Anwendung dargestellt. Dieses Modell ähnelt der Art und Weise, wie ASMX-Seiten in einer IIS-Anwendung als ASMX-Dateien dargestellt werden. Eine .svc-Datei enthält eine WCF-spezifische Verarbeitungsdirektive ([\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)), mit der die WCF-Hostinginfrastruktur gehostete Dienste als Reaktion auf eingehende Nachrichten aktivieren kann. Die gebräuchlichste Syntax für eine SVC-Datei befindet sich in der folgenden Anweisung:

`<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>`

Sie besteht aus der `Service` [ \@ServiceHost-Direktive](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) und einem einzelnen Attribut , . Der Wert des `Service` -Attributs ist der CLR-Typname (Common Language Runtime) der Dienstimplementierung. Die Verwendung dieser Direktive ist praktisch mit der Erstellung eines Diensthosts mithilfe des folgenden Codes gleichzusetzen:

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

Zudem kann eine zusätzliche Hostkonfiguration vorgenommen werden, indem z.&#160;B. eine Liste mit Basisadressen für den Dienst erstellt wird. Sie können auch eine benutzerdefinierte <xref:System.ServiceModel.Activation.ServiceHostFactory> verwenden, um die Direktive zur Verwendung mit benutzerdefinierten Hostlösungen zu erweitern. Die IIS-Anwendungen, die WCF-Dienste hosten, <xref:System.ServiceModel.ServiceHost> sind nicht für die Verwaltung der Erstellung und Lebensdauer von Instances verantwortlich. Die verwaltete WCF-Hostinginfrastruktur erstellt die erforderliche <xref:System.ServiceModel.ServiceHost> Instanz dynamisch, wenn die erste Anforderung für die .svc-Datei empfangen wird. Die Instanz wird erst freigegeben, wenn sie entweder explizit durch Code geschlossen oder die Anwendung wiederverwendet wird.

Weitere Informationen zur Syntax für .svc-Dateien finden Sie unter [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Bereitstellen der Dienstimplementierung für die IIS-Anwendung

WCF-Dienste, die in IIS gehostet werden, verwenden dasselbe dynamische Kompilierungsmodell wie ASP.NET 2.0. Wie bei ASP.NET können Sie den Implementierungscode für IIS-gehostete WCF-Dienste auf verschiedene Weise an verschiedenen Standorten bereitstellen:

- Als vorkompilierte DLL im globalen Assemblycache (GAC) oder im \bin-Verzeichnis der Anwendung. Vorkompilierte Binärdateien werden erst aktualisiert, wenn eine neue Version der Klassenbibliothek bereitgestellt wird.

- Als unkompilierte Quelldateien, die sich im Verzeichnis "App_Code" der Anwendung befinden. Quelldateien in diesem Verzeichnis werden dynamisch angefordert, wenn die erste Anforderung der Anwendung verarbeitet wird. Änderungen an Dateien im \App_Code-Verzeichnis führen dazu, dass die gesamte Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.

- Als unkompilierter Code, der direkt in der .svc-Datei abgelegt wird. Implementierungscode kann auch inline in der .svc-Datei \@des Dienstes nach der ServiceHost-Direktive gespeichert werden. Änderungen an Inlinecode führen dazu, dass die Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.

Weitere Informationen zum ASP.NET 2.0-Kompilierungsmodell finden Sie unter [ASP.NET Compilation Overview](https://docs.microsoft.com/previous-versions/aspnet/ms178466(v=vs.100)).

## <a name="configure-the-wcf-service"></a>Konfigurieren des WCF-Diensts

IIS-gehostete WCF-Dienste speichern ihre Konfiguration in der Datei "Anwendungen Web.config". IIS-gehostete Dienste verwenden dieselben Konfigurationselemente und Syntaxwie WCF-Dienste, die außerhalb von IIS gehostet werden. Jedoch gelten die folgenden Einschränkungen nur für die IIS-Hostumgebung:

- Basisadressen für IIS-gehostete Dienste

- Anwendungen, die WCF-Dienste außerhalb von IIS hosten, können die Basisadresse der <xref:System.ServiceModel.ServiceHost> von ihnen gehosteten Dienste steuern, indem sie eine Reihe von Basisadress-URIs an den Konstruktor übergeben oder ein [ \<Host->-Element](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) in der Konfiguration des Dienstes bereitstellen. Dienste, die in IIS gehostet werden, können ihre Basisadressen nicht steuern. Die Basisadresse eines IIS-gehosteten Diensts ist die Adresse seiner SVC-Datei.

### <a name="endpoint-addresses-for-iis-hosted-services"></a>Endpunktadressen für IIS-gehostete Dienste

Wenn ein Dienst in IIS gehostet wird, werden Endpunktadressen als relativ zur Adresse der SVC-Datei betrachtet, die den Dienst darstellt. Wenn sich z. B. die Basisadresse eines WCF-Dienstes `http://localhost/Application1/MyService.svc` mit der folgenden Endpunktkonfiguration befindet:

```xml
<endpoint address="anotherEndpoint" />
```

Dies stellt einen Endpunkt `http://localhost/Application1/MyService.svc/anotherEndpoint`bereit, der unter erreicht werden kann.

Ebenso stellt das Endpunktkonfigurationselement, das eine leere Zeichenfolge als relative `http://localhost/Application1/MyService.svc`Adresse verwendet, einen Endpunkt bereit, der unter erreichbar ist, d. h. die Basisadresse.

```xml
<endpoint address="" />
```

Sie müssen immer relative Endpunktadressen für IIS-gehostete Dienstendpunkte verwenden. Das Bereitstellen einer vollqualifizierten Endpunktadresse `http://localhost/MyService.svc`(z. B. ) kann zu Fehlern bei der Bereitstellung des Dienstes führen, wenn die Endpunktadresse nicht auf die IIS-Anwendung zeigt, die den Dienst hostet, der den Endpunkt offenlegt. Durch die Verwendung relativer Endpunktadressen für gehostete Dienste werden diese potenziellen Konflikte vermieden.

### <a name="available-transports"></a>Verfügbare Transporte

WCF-Dienste, die in IIS 5.1 und IIS 6.0 gehostet werden, sind auf die Verwendung von HTTP-basierter Kommunikation beschränkt. Auf diesen IIS-Plattformen führt das Konfigurieren eines gehosteten Diensts für die Verwendung einer Nicht-HTTP-Bindung zu einem Fehler während der Dienstaktivierung. Für IIS 7.0 umfassen die unterstützten Transporte HTTP, Net.TCP, Net.Pipe, Net.MSMQ und msmq.formatname für die Abwärtskompatibilität mit vorhandenen MSMQ-Anwendungen.

### <a name="http-transport-security"></a>HTTP-Transportsicherheit

IIS-gehostete WCF-Dienste können die HTTP-Transportsicherheit nutzen (z. B. HTTPS- und HTTP-Authentifizierungsschemata wie Basic, Digest und Integrierte Windows-Authentifizierung), solange das virtuelle IIS-Verzeichnis, das den Dienst enthält, diese Einstellungen unterstützt. Die HTTP-Transportsicherheitseinstellungen der Bindung eines gehosteten Endpunkts müssen mit den Transportsicherheitseinstellungen im virtuellen IIS-Verzeichnis identisch sein, in dem sie enthalten ist.

Beispielsweise muss sich ein WCF-Endpunkt, der für die Verwendung der HTTP-Digest-Authentifizierung konfiguriert ist, in einem virtuellen IIS-Verzeichnis befinden, das ebenfalls für die HTTP-Digest-Authentifizierung konfiguriert ist. Unübertroffene Kombinationen aus IIS-Einstellungen und WCF-Endpunkteinstellungen führen zu einem Fehler während der Dienstaktivierung.

## <a name="see-also"></a>Weitere Informationen

- [Hosten in Internetinformationsdiensten](hosting-in-internet-information-services.md)
- [Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten](internet-information-services-hosting-best-practices.md)
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
