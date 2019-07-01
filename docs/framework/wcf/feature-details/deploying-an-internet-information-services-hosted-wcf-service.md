---
title: Bereitstellen eines IIS-gehosteten WCF-Diensts
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: fcfad4c6cd7ffb0bf1233bab842b57a10bcc7f87
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486926"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts

Entwickeln und Bereitstellen eines Windows Communication Foundation (WCF)-Diensts, das in IIS (Internetinformationsdienste) gehostet wird umfasst die folgenden Aufgaben:

- Stellen Sie sicher, dass IIS, ASP.NET, WCF und der WCF-aktivierungskomponente ordnungsgemäß installiert und registriert werden.

- Erstellen einer neuen IIS‑Anwendung oder wiederverwenden einer vorhandenen ASP.NET-Anwendung.

- Erstellen Sie eine SVC-Datei für den WCF-Dienst.

- Bereitstellen der Dienstimplementierung für die IIS-Anwendung.

- Konfigurieren Sie den WCF-Dienst.

Eine ausführliche exemplarische Vorgehensweise zum Erstellen eines IIS-gehosteten WCF-Diensts finden Sie unter [Vorgehensweise: Hosten ein WCF-Diensts in IIS](how-to-host-a-wcf-service-in-iis.md).

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Sicherstellen, dass IIS, ASP.NET und WCF ordnungsgemäß installiert und registriert sind

WCF, IIS und ASP.NET müssen für IIS-gehosteten WCF-Dienste ordnungsgemäß installiert werden. Die Verfahren zum Installieren von WCF (als Teil von .NET Framework), ASP.NET und IIS variieren je nach Betriebssystem. Weitere Informationen zum Installieren von WCF und .NET Framework finden Sie unter [Installieren von .NET Framework für Entwickler](../../install/guide-for-developers.md). Öffnen Sie zum Installieren von IIS unter Windows 10 **Programme und Funktionen** in **Systemsteuerung** und wählen Sie dann **Aktivieren von Windows-Funktionen ein- oder ausschalten**. In **Windows Features**Option **Internet Information Services** und wählen Sie dann **OK**.

![Windows-Features mit IIS hervorgehoben](media/windows-features-iis.png)

Anweisungen zum Installieren von IIS unter anderen Betriebssystemen finden Sie unter [installieren Sie IIS auf Windows Vista und Windows 7](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7) und [installieren Sie IIS 8.5 unter Windows Server 2012 R2](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2).

Der Installationsvorgang für .NET Framework wird WCF automatisch mit IIS registriert, wenn IIS bereits auf dem Computer vorhanden ist. Wenn IIS nach .NET Framework installiert ist, ist ein zusätzlicher Schritt erforderlich, zum Registrieren von WCF mit IIS und ASP.NET. Gehen Sie hierzu je nach Betriebssystem wie folgt vor:

- Windows 7 und WindowsServer 2003: Verwenden der [ServiceModel Registration-Tool (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) Tool, um WCF bei IIS registrieren. Um dieses Tool zu verwenden, geben **ServiceModelReg.exe/i / x** in die [Developer-Eingabeaufforderung für Visual Studio](../../tools/developer-command-prompt-for-vs.md).

- Windows 7: Abschließend müssen Sie sicherstellen, dass ASP.NET für die Verwendung von .NET Framework, Version 4 oder höher konfiguriert ist. Zu diesem Zweck das Tool ASPNET_Regiis mit der Ausführung der `–i` Option. Weitere Informationen finden Sie unter [ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=201186).

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen ASP.NET-Anwendung

IIS-gehosteten WCF-Dienste müssen innerhalb einer IIS‑Anwendung befinden. Sie können eine neue IIS‑Anwendung zum Hosten von WCF-Diensten ausschließlich erstellen. Alternativ können Sie einen WCF-Dienst in eine vorhandene Anwendung bereitstellen, die bereits mit ASP.NET 2.0-Inhalt (z. B. aspx-Seiten und ASP.NET-Webdienste [ASMX]) dient. Weitere Informationen zu diesen Optionen finden Sie unter der "Hosting WCF Seite-an-Seite mit ASP.NET" und "Hosting WCF-Dienste im ASP.NET-Kompatibilitätsmodus" Abschnitten [WCF-Dienste und ASP.NET](wcf-services-and-aspnet.md).

Beachten Sie, dass IIS 6.0 und spätere Versionen in regelmäßigen Abständen eine isolierte objektorientierte Programmierung-Anwendung neu gestartet. Der Standardwert ist 1740 Minuten. Der höchstmögliche Wert sind 71.582 Minuten. Dieser Neustart kann deaktiviert werden. Weitere Informationen zu dieser Eigenschaft finden Sie unter den [PeriodicRestartTime](https://go.microsoft.com/fwlink/?LinkId=109968).

## <a name="create-an-svc-file-for-the-wcf-service"></a>Erstellen einer SVC-Datei für den WCF-Dienst

In IIS gehosteten WCF-Dienste werden als spezielle Inhaltsdateien (SVC-Dateien) in der IIS-Anwendung dargestellt. Dieses Modell ähnelt der Art und Weise, wie ASMX-Seiten in einer IIS-Anwendung als ASMX-Dateien dargestellt werden. Eine SVC-Datei enthält eine WCF-spezifische verarbeitungsanweisung ([\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)), ermöglicht WCF Hostinginfrastruktur gehostete Dienste als Reaktion auf eingehende Nachrichten zu aktivieren. Die gebräuchlichste Syntax für eine SVC-Datei befindet sich in der folgenden Anweisung:

```
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>
```

Es besteht aus den [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive und einem einzelnen Attribut: `Service`. Der Wert des `Service` -Attributs ist der CLR-Typname (Common Language Runtime) der Dienstimplementierung. Die Verwendung dieser Direktive ist praktisch mit der Erstellung eines Diensthosts mithilfe des folgenden Codes gleichzusetzen:

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

Zudem kann eine zusätzliche Hostkonfiguration vorgenommen werden, indem z.&#160;B. eine Liste mit Basisadressen für den Dienst erstellt wird. Sie können auch eine benutzerdefinierte <xref:System.ServiceModel.Activation.ServiceHostFactory> verwenden, um die Direktive zur Verwendung mit benutzerdefinierten Hostlösungen zu erweitern. Die IIS-Anwendungen, die WCF-Dienste hosten sind nicht verantwortlich für die Verwaltung von die Erstellung und Lebensdauer der <xref:System.ServiceModel.ServiceHost> Instanzen. Die verwaltete hosting-Infrastruktur von WCF erstellt die erforderlichen <xref:System.ServiceModel.ServiceHost> -Instanz dynamisch, sobald die erste Anforderung für die SVC-Datei empfangen wird. Die Instanz wird erst freigegeben, wenn sie entweder explizit durch Code geschlossen oder die Anwendung wiederverwendet wird.

Weitere Informationen über die Syntax für SVC-Dateien finden Sie unter [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Bereitstellen der Dienstimplementierung für die IIS-Anwendung

In IIS gehosteten WCF-Dienste verwenden das gleiche dynamische Kompilierungsmodell wie ASP.NET 2.0. Genau wie bei ASP.NET können Sie den Implementierungscode für IIS-gehosteten WCF-Dienste auf verschiedene Weise an verschiedenen Speicherorten folgendermaßen bereitstellen:

- Als vorkompilierte DLL im globalen Assemblycache (GAC) oder im \bin-Verzeichnis der Anwendung. Vorkompilierte Binärdateien werden erst aktualisiert, wenn eine neue Version der Klassenbibliothek bereitgestellt wird.

- Während einer nicht kompilierten Quelldateien im Verzeichnis \App_Code der Anwendung befindet. Quelldateien in diesem Verzeichnis werden dynamisch angefordert, wenn die erste Anforderung der Anwendung verarbeitet wird. Änderungen an Dateien im \App_Code-Verzeichnis führen dazu, dass die gesamte Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.

- Wie nicht kompilierten Code direkt in der SVC-Datei eingefügt werden soll. Code zur Implementierung kann sich Inline in der SVC Datei, auch sein, nach der \@ServiceHost-Direktive. Änderungen an Inlinecode führen dazu, dass die Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.

Weitere Informationen über das Kompilierungsmodell von ASP.NET 2.0 finden Sie unter [Übersicht über die ASP.NET-Kompilierung](https://go.microsoft.com/fwlink/?LinkId=94773).

## <a name="configure-the-wcf-service"></a>Konfigurieren des WCF-Diensts

IIS-gehosteten WCF-Dienste speichern ihre Konfiguration in der Web.config-Datei der Anwendung. IIS-gehostete Dienste verwenden die gleichen Konfigurationselemente und die Syntax als WCF-Dienste, die außerhalb von IIS gehostet. Jedoch gelten die folgenden Einschränkungen nur für die IIS-Hostumgebung:

- Basisadressen für IIS-gehostete Dienste

- Anwendungen, die hosting außerhalb von IIS WCF-Dienste, die Basisadresse der Dienste, die sie hosten steuern können, übergeben Sie einen Satz Basisadressen-URIs zum zu befassen der <xref:System.ServiceModel.ServiceHost> Konstruktor oder durch Bereitstellen einer [ \<Host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) Element in der Konfiguration des Diensts. Dienste, die in IIS gehostet werden, können ihre Basisadressen nicht steuern. Die Basisadresse eines IIS-gehosteten Diensts ist die Adresse seiner SVC-Datei.

### <a name="endpoint-addresses-for-iis-hosted-services"></a>Endpunktadressen für IIS-gehostete Dienste

Wenn ein Dienst in IIS gehostet wird, werden Endpunktadressen als relativ zur Adresse der SVC-Datei betrachtet, die den Dienst darstellt. Wenn die Basisadresse eines WCF-Diensts ist z. B. `http://localhost/Application1/MyService.svc` mit die Endpunktkonfiguration folgendermaßen:

```xml
<endpoint address="anotherEndpoint" .../>
```

Dadurch wird ein Endpunkt, der zu erreichen unter `http://localhost/Application1/MyService.svc/anotherEndpoint`.

Auf ähnliche Weise die Endpunkt-Konfigurationselement, das eine leere Zeichenfolge verwendet werden, da die relative Adresse einen Endpunkt unter bietet `http://localhost/Application1/MyService.svc`, dies ist die Basisadresse.

```xml
<endpoint address="" ... />
```

Sie müssen immer relative Endpunktadressen für IIS-gehostete Dienstendpunkte verwenden. Angabe einer vollständig qualifizierten Endpunktadresse (z. B. `http://localhost/MyService.svc`) kann zu Fehlern bei der Bereitstellung des Diensts führen, wenn die Endpunktadresse nicht auf die IIS-Anwendung verweist, der den Endpunkt verfügbar machen Dienst hostet. Durch die Verwendung relativer Endpunktadressen für gehostete Dienste werden diese potenziellen Konflikte vermieden.

### <a name="available-transports"></a>Verfügbare Transporte

WCF-Dienste in IIS gehostet 5.1 und IIS 6.0 auf die Verwendung von HTTP-basierten Kommunikation beschränkt sind. Auf diesen IIS-Plattformen führt das Konfigurieren eines gehosteten Diensts für die Verwendung einer Nicht-HTTP-Bindung zu einem Fehler während der Dienstaktivierung. Für IIS 7.0 enthalten die unterstützten Transporte HTTP, Net.TCP, Net.Pipe, Net.MSMQ und msmq.formatname für Abwärtskompatibilität Kompatibilität mit vorhandenen MSMQ-Anwendungen.

### <a name="http-transport-security"></a>HTTP-Transportsicherheit

IIS-gehosteten WCF-Dienste können verwenden der HTTP-transportsicherheit (z. B. HTTPS und HTTP-Authentifizierungsschemata wie Basic, Digest und integrierte Windows-Authentifizierung) als virtuelle IIS-Verzeichnis, das den Dienst enthält, die diese unterstützt Einstellungen. Die HTTP-Transportsicherheitseinstellungen der Bindung eines gehosteten Endpunkts müssen mit den Transportsicherheitseinstellungen im virtuellen IIS-Verzeichnis identisch sein, in dem sie enthalten ist.

Beispielsweise muss ein WCF-Endpunkt für die Verwendung von HTTP-Digestauthentifizierung konfiguriert in einem virtuellen IIS-Verzeichnis befinden, die auch zum Zulassen von HTTP-Digestauthentifizierung konfiguriert ist. Nicht übereinstimmende Kombinationen von Einstellungen für IIS und WCF-Endpunkt führt zu einem Fehler während der dienstaktivierung.

## <a name="see-also"></a>Siehe auch

- [Hosten in IIS (Internetinformationsdienste)](hosting-in-internet-information-services.md)
- [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](internet-information-services-hosting-best-practices.md)
- [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
