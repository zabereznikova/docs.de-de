---
title: Bereitstellen eines IIS-gehosteten WCF-Diensts
description: Informieren Sie sich über die erforderlichen Aufgaben zum entwickeln und Bereitstellen eines WCF-Dienstanbieter, der in IIS gehostet wird, beginnend mit der Überprüfung der Komponenteninstallation
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 5d9a0b80cc75baec2325b778cee7daa68531f2d5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557566"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts

Das entwickeln und Bereitstellen eines Windows Communication Foundation (WCF)-Dienstanbieter, der in Internetinformationsdienste (IIS) gehostet wird, umfasst die folgenden Aufgaben:

- Stellen Sie sicher, dass IIS, ASP.net, WCF und die WCF-Aktivierungs Komponente ordnungsgemäß installiert und registriert sind.

- Erstellen Sie eine neue IIS-Anwendung, oder verwenden Sie eine vorhandene ASP.NET-Anwendung erneut.

- Erstellen Sie eine SVC-Datei für den WCF-Dienst.

- Bereitstellen der Dienstimplementierung für die IIS-Anwendung.

- Konfigurieren Sie den WCF-Dienst.

Eine ausführliche Exemplarische Vorgehensweise zum Erstellen eines IIS-gehosteten WCF-Diensts finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in IIS](how-to-host-a-wcf-service-in-iis.md).

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Sicherstellen, dass IIS, ASP.NET und WCF ordnungsgemäß installiert und registriert sind

WCF, IIS und ASP.net müssen installiert sein, damit IIS-gehostete WCF-Dienste ordnungsgemäß funktionieren. Die Verfahren zum Installieren von WCF (als Teil des .NET Framework), ASP.net und IIS variieren je nach Betriebssystem. Weitere Informationen zum Installieren von WCF und der .NET Framework finden Sie unter [Installieren des .NET Framework für Entwickler](../../install/guide-for-developers.md). Um IIS unter Windows 10 zu installieren, öffnen Sie in der **Systemsteuerung** **Programme und Funktionen** , und wählen Sie dann Windows-Funktionen ein- **oder ausschalten aus**. Wählen Sie unter **Windows-Features** **Internetinformationsdienste** aus, und klicken Sie dann auf **OK**.

![Windows-Features mit hervorgehobenem IIS](./media/windows-features-iis.png)

Anweisungen zum Installieren von IIS unter anderen Betriebssystemen finden Sie unter [Installieren von IIS unter Windows Vista und Windows 7](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7) und [Installieren von IIS 8,5 unter Windows Server 2012 R2](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2).

Beim Installationsvorgang für .NET Framework wird WCF automatisch bei IIS registriert, wenn IIS bereits auf dem Computer vorhanden ist. Wenn IIS nach dem .NET Framework installiert wird, ist ein zusätzlicher Schritt erforderlich, um WCF bei IIS und ASP.net zu registrieren. Gehen Sie hierzu je nach Betriebssystem wie folgt vor:

- Windows 7 und Windows Server 2003: Verwenden Sie das [Service Model-Registrierungs Tool (ServiceModelReg.exe)](../servicemodelreg-exe.md) , um WCF bei IIS zu registrieren. Um dieses Tool zu verwenden, geben Sie im [Developer-Eingabeaufforderung für Visual Studio](../../tools/developer-command-prompt-for-vs.md) **ServiceModelReg.exe/i/x** ein.

- Windows 7: Schließlich müssen Sie überprüfen, ob ASP.net für die Verwendung der .NET Framework Version 4 oder höher konfiguriert ist. Dazu führen Sie das ASPNET_Regiis-Tool mit der- `–i` Option aus. Weitere Informationen finden Sie unter [ASP.NET IIS Registration Tool](/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90)).

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen ASP.NET-Anwendung

IIS-gehostete WCF-Dienste müssen sich innerhalb einer IIS-Anwendung befinden. Sie können eine neue IIS-Anwendung erstellen, um ausschließlich WCF-Dienste zu hosten. Alternativ können Sie einen WCF-Dienst in einer vorhandenen Anwendung bereitstellen, die bereits ASP.NET 2,0-Inhalte (z. b. aspx-Seiten und ASP.NET-Webdienste [ASMX]) gehostet. Weitere Informationen zu diesen Optionen finden Sie im Abschnitt "parallele Hosting von WCF mit ASP.net" und "Hosting von WCF-Diensten im ASP.NET-Kompatibilitätsmodus" unter [WCF-Dienste und ASP.net](wcf-services-and-aspnet.md).

Beachten Sie, dass IIS 6,0 und höhere Versionen regelmäßig eine isolierte objektorientierte Programmier Anwendung neu starten. Der Standardwert ist 1740 Minuten. Der höchstmögliche Wert sind 71.582 Minuten. Dieser Neustart kann deaktiviert werden. Weitere Informationen zu dieser Eigenschaft finden Sie unter [periodikrestarttime](/previous-versions/iis/6.0-sdk/ms525914(v=vs.90)).

## <a name="create-an-svc-file-for-the-wcf-service"></a>Erstellen einer SVC-Datei für den WCF-Dienst

In IIS gehostete WCF-Dienste werden in der IIS-Anwendung als spezielle Inhalts Dateien (SVC-Dateien) dargestellt. Dieses Modell ähnelt der Art und Weise, wie ASMX-Seiten in einer IIS-Anwendung als ASMX-Dateien dargestellt werden. Eine SVC-Datei enthält eine WCF-spezifische Verarbeitungs Direktive ([ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md)), die es der WCF-Hostinginfrastruktur ermöglicht, gehostete Dienste als Reaktion auf eingehende Nachrichten zu aktivieren. Die gebräuchlichste Syntax für eine SVC-Datei befindet sich in der folgenden Anweisung:

`<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>`

Er besteht aus der [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive und einem einzelnen Attribut, `Service` . Der Wert des `Service` -Attributs ist der CLR-Typname (Common Language Runtime) der Dienstimplementierung. Die Verwendung dieser Direktive ist praktisch mit der Erstellung eines Diensthosts mithilfe des folgenden Codes gleichzusetzen:

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

Zudem kann eine zusätzliche Hostkonfiguration vorgenommen werden, indem z.&#160;B. eine Liste mit Basisadressen für den Dienst erstellt wird. Sie können auch eine benutzerdefinierte <xref:System.ServiceModel.Activation.ServiceHostFactory> verwenden, um die Direktive zur Verwendung mit benutzerdefinierten Hostlösungen zu erweitern. Die IIS-Anwendungen, die WCF-Dienste hosten, sind nicht für die Verwaltung der Erstellung und Lebensdauer von- <xref:System.ServiceModel.ServiceHost> Instanzen verantwortlich. Die verwaltete WCF-Hostinginfrastruktur erstellt die erforderliche <xref:System.ServiceModel.ServiceHost> Instanz dynamisch, wenn die erste Anforderung für die SVC-Datei empfangen wird. Die Instanz wird erst freigegeben, wenn sie entweder explizit durch Code geschlossen oder die Anwendung wiederverwendet wird.

Weitere Informationen zur Syntax für SVC-Dateien finden Sie unter [ \@ Service Host](../../configure-apps/file-schema/wcf-directive/servicehost.md).

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Bereitstellen der Dienstimplementierung für die IIS-Anwendung

In IIS gehostete WCF-Dienste verwenden das gleiche dynamische Kompilierungs Modell wie ASP.NET 2,0. Ebenso wie bei ASP.net können Sie den Implementierungs Code für IIS-gehostete WCF-Dienste auf unterschiedliche Weise an verschiedenen Speicherorten bereitstellen, wie im folgenden dargestellt:

- Als vorkompilierte DLL im globalen Assemblycache (GAC) oder im \bin-Verzeichnis der Anwendung. Vorkompilierte Binärdateien werden erst aktualisiert, wenn eine neue Version der Klassenbibliothek bereitgestellt wird.

- Als nicht kompilierte Quelldateien, die sich im Verzeichnis \ App_Code der Anwendung befinden. Quelldateien in diesem Verzeichnis werden dynamisch angefordert, wenn die erste Anforderung der Anwendung verarbeitet wird. Änderungen an Dateien im \App_Code-Verzeichnis führen dazu, dass die gesamte Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.

- Als nicht kompilierter Code, der direkt in die SVC-Datei eingefügt wird. Implementierungs Code kann auch Inline in der SVC-Datei des Diensts nach der Service \@ Host-Direktive abgelegt werden. Änderungen an Inlinecode führen dazu, dass die Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.

Weitere Informationen zum ASP.NET 2,0-Kompilierungs Modell finden Sie unter [Übersicht über die ASP.NET-Kompilierung](/previous-versions/aspnet/ms178466(v=vs.100)).

## <a name="configure-the-wcf-service"></a>Konfigurieren des WCF-Diensts

IIS-gehostete WCF-Dienste speichern Ihre Konfiguration in der Anwendung Web.config Datei. IIS-gehostete Dienste verwenden die gleichen Konfigurationselemente und die gleiche Syntax wie WCF-Dienste, die außerhalb von IIS gehostet werden. Jedoch gelten die folgenden Einschränkungen nur für die IIS-Hostumgebung:

- Basisadressen für IIS-gehostete Dienste

- Anwendungen, die WCF-Dienste außerhalb von IIS hosten, können die Basisadresse der von Ihnen gehosteten Dienste steuern, indem Sie einen Satz von Basisadressen-URIs an den- <xref:System.ServiceModel.ServiceHost> Konstruktor übergeben oder ein- [\<host>](../../configure-apps/file-schema/wcf/host.md) Element in der Konfiguration des Diensts bereitstellen. Dienste, die in IIS gehostet werden, können ihre Basisadressen nicht steuern. Die Basisadresse eines IIS-gehosteten Diensts ist die Adresse seiner SVC-Datei.

### <a name="endpoint-addresses-for-iis-hosted-services"></a>Endpunktadressen für IIS-gehostete Dienste

Wenn ein Dienst in IIS gehostet wird, werden Endpunktadressen als relativ zur Adresse der SVC-Datei betrachtet, die den Dienst darstellt. Wenn die Basisadresse eines WCF-Dienstanbieter z. b. `http://localhost/Application1/MyService.svc` mit der folgenden Endpunkt Konfiguration erfolgt:

```xml
<endpoint address="anotherEndpoint" />
```

Dadurch wird ein Endpunkt bereitstellt, der bei erreicht werden kann `http://localhost/Application1/MyService.svc/anotherEndpoint` .

Ebenso stellt das Endpunkt Konfigurationselement, das eine leere Zeichenfolge als relative Adresse verwendet, einen Endpunkt bereit, der für erreichbar `http://localhost/Application1/MyService.svc` ist. Dies ist die Basisadresse.

```xml
<endpoint address="" />
```

Sie müssen immer relative Endpunktadressen für IIS-gehostete Dienstendpunkte verwenden. Das Bereitstellen einer voll qualifizierten Endpunkt Adresse (z. b. `http://localhost/MyService.svc` ) kann zu Fehlern bei der Bereitstellung des Diensts führen, wenn die Endpunkt Adresse nicht auf die IIS-Anwendung verweist, die den Dienst hostet, der den Endpunkt verfügbar macht. Durch die Verwendung relativer Endpunktadressen für gehostete Dienste werden diese potenziellen Konflikte vermieden.

### <a name="available-transports"></a>Verfügbare Transporte

WCF-Dienste, die in IIS 5,1 und IIS 6,0 gehostet werden, sind auf die Verwendung der HTTP-basierten Kommunikation beschränkt. Auf diesen IIS-Plattformen führt das Konfigurieren eines gehosteten Diensts für die Verwendung einer Nicht-HTTP-Bindung zu einem Fehler während der Dienstaktivierung. Für IIS 7,0 enthalten die unterstützten Transporte http, net. TCP, net. Pipe, net. MSMQ und MSMQ. Format Name für die Abwärtskompatibilität mit vorhandenen MSMQ-Anwendungen.

### <a name="http-transport-security"></a>HTTP-Transportsicherheit

IIS-gehostete WCF-Dienste können die HTTP-Transportsicherheit nutzen (z. b. HTTPS-und http-Authentifizierungs Schemas wie Standard, Digest und die integrierte Windows-Authentifizierung), sofern das virtuelle IIS-Verzeichnis, das den Dienst enthält, diese Einstellungen unterstützt. Die HTTP-Transportsicherheitseinstellungen der Bindung eines gehosteten Endpunkts müssen mit den Transportsicherheitseinstellungen im virtuellen IIS-Verzeichnis identisch sein, in dem sie enthalten ist.

Beispielsweise muss ein WCF-Endpunkt, der für die HTTP Digest-Authentifizierung konfiguriert ist, sich in einem virtuellen IIS-Verzeichnis befinden, das auch für die HTTP-Digestauthentifizierung konfiguriert ist. Nicht übereinstimmende Kombinationen von IIS-Einstellungen und WCF-Endpunkt Einstellungen führen bei der Dienst Aktivierung zu einem Fehler.

## <a name="see-also"></a>Siehe auch

- [Hosten in Internetinformationsdiensten](hosting-in-internet-information-services.md)
- [Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten](internet-information-services-hosting-best-practices.md)
- [Windows Server AppFabric-Hostingfunktionen](/previous-versions/appfabric/ee677189(v=azure.10))
