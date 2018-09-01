---
title: Bereitstellen eines IIS-gehosteten WCF-Diensts
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: b2b58de703a0864ac0666cb4738a95726e28bcaf
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395514"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts
Entwickeln und Bereitstellen eines Windows Communication Foundation (WCF)-Diensts, das in IIS (Internetinformationsdienste) gehostet wird umfasst die folgenden Aufgaben:  
  
-   Stellen Sie sicher, dass IIS, ASP.NET, WCF und der WCF-aktivierungskomponente ordnungsgemäß installiert und registriert werden.  
  
-   Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung.  
  
-   Erstellen Sie eine SVC-Datei für den WCF-Dienst.  
  
-   Bereitstellen der Dienstimplementierung für die IIS-Anwendung.  
  
-   Konfigurieren Sie den WCF-Dienst.  
  
 Eine ausführliche exemplarische Vorgehensweise zum Erstellen eines IIS-gehosteten WCF-Diensts finden Sie unter [Gewusst wie: Hosten eines WCF-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Sicherstellen, dass IIS, ASP.NET und WCF ordnungsgemäß installiert und registriert sind  
 WCF, IIS und ASP.NET müssen für IIS-gehosteten WCF-Dienste ordnungsgemäß installiert werden. Das Verfahren zum Installieren von WCF (als Teil der [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET und IIS variieren je nach Version des Betriebssystems, die verwendet wird. Weitere Informationen zum Installieren von WCF und [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], finden Sie unter [Microsoft .NET Framework 4-Webinstaller](https://go.microsoft.com/fwlink/?LinkId=201185). Anweisungen zum Installieren von IIS finden Sie unter [Installieren von IIS](https://go.microsoft.com/fwlink/?LinkId=201188).  
  
 Der Installationsvorgang für den [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] WCF automatisch bei IIS registriert wird, wenn IIS bereits auf dem Computer vorhanden ist. Wenn IIS installiert ist, nach der [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], ein zusätzlicher Schritt ist erforderlich, um WCF mit IIS zu registrieren und [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Gehen Sie hierzu je nach Betriebssystem wie folgt vor:  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], Windows 7 und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: Verwenden der [ServiceModel Registration-Tool (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) Tool zum Registrieren von WCF in IIS: um dieses Tool zu verwenden, geben **ServiceModelReg.exe/i / x** in Visual Studio -Eingabeaufforderung. Sie können diese Eingabeaufforderung öffnen, indem Sie auf die Schaltfläche „Start“ klicken und dann **Alle Programme**, **Microsoft Visual Studio 2012**, **Visual Studio Tools**und **Visual Studio-Eingabeaufforderung**auswählen.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: Installieren Sie die Unterkomponente „Windows Communication Foundation-Aktivierungskomponenten“ von [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Klicken Sie dazu in der Systemsteuerung auf **Programme hinzufügen oder entfernen Sie** und dann **hinzufügen\/Entfernen von Windows-Komponenten**. Dadurch wird der **Assistent für Windows-Komponenten**aktiviert.  
  
-   Windows 7:  
  
 Abschließend müssen Sie sich sicherstellen, dass ASP.NET für die Verwendung von .NET Framework Version 4 konfiguriert ist. Führen Sie hierzu das Tool ASPNET_Regiis mit der Option –i aus. Weitere Informationen finden Sie unter [ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=201186)  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen ASP.NET-Anwendung  
 IIS-gehosteten WCF-Dienste müssen innerhalb einer IIS‑Anwendung befinden. Sie können eine neue IIS‑Anwendung zum Hosten von WCF-Diensten ausschließlich erstellen. Alternativ können Sie einen WCF-Dienst bereitstellen, in eine vorhandene Anwendung, die bereits hostet [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] Inhalt (z. B. aspx-Seiten und ASP.NET-Webdienste [ASMX]). Weitere Informationen zu diesen Optionen finden Sie unter der "Hosting WCF Seite-an-Seite mit ASP.NET" und "Hosting WCF-Dienste im ASP.NET-Kompatibilitätsmodus" Abschnitten [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
 Beachten Sie, dass [!INCLUDE[iis601](../../../../includes/iis601-md.md)] und höhere Versionen in regelmäßigen Abständen eine isolierte objektorientierte Programmierungsanwendung neu starten. Der Standardwert ist 1740 Minuten. Der höchstmögliche Wert sind 71.582 Minuten. Dieser Neustart kann deaktiviert werden. Weitere Informationen zu dieser Eigenschaft finden Sie unter den [PeriodicRestartTime](https://go.microsoft.com/fwlink/?LinkId=109968).  
  
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
 In IIS gehosteten WCF-Dienste verwenden das gleiche dynamische Kompilierungsmodell wie [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]. Wie bei [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], Sie können den Implementierungscode für IIS-gehosteten WCF-Dienste auf verschiedene Weise an verschiedenen Speicherorten folgendermaßen bereitstellen:  
  
-   Als vorkompilierte DLL im globalen Assemblycache (GAC) oder im \bin-Verzeichnis der Anwendung. Vorkompilierte Binärdateien werden erst aktualisiert, wenn eine neue Version der Klassenbibliothek bereitgestellt wird.  
  
-   Während einer nicht kompilierten Quelldateien im Verzeichnis \App_Code der Anwendung befindet. Quelldateien in diesem Verzeichnis werden dynamisch angefordert, wenn die erste Anforderung der Anwendung verarbeitet wird. Änderungen an Dateien im \App_Code-Verzeichnis führen dazu, dass die gesamte Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.  
  
-   Wie nicht kompilierten Code direkt in der SVC-Datei eingefügt werden soll. Code zur Implementierung kann sich Inline in der SVC Datei, auch sein, nach der \@ServiceHost-Direktive. Änderungen an Inlinecode führen dazu, dass die Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.  
  
 Weitere Informationen zu den [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] -Kompilierungsmodell finden Sie unter [Übersicht über die ASP.NET-Kompilierung](https://go.microsoft.com/fwlink/?LinkId=94773).  
  
## <a name="configure-the-wcf-service"></a>Konfigurieren des WCF-Diensts  
 IIS-gehosteten WCF-Dienste speichern ihre Konfiguration in der Web.config-Datei der Anwendung. IIS-gehostete Dienste verwenden die gleichen Konfigurationselemente und die Syntax als WCF-Dienste, die außerhalb von IIS gehostet. Jedoch gelten die folgenden Einschränkungen nur für die IIS-Hostumgebung:  
  
-   Basisadressen für IIS-gehostete Dienste  
  
-   Anwendungen, die hosting außerhalb von IIS WCF-Dienste, die Basisadresse der Dienste, die sie hosten steuern können, übergeben Sie einen Satz Basisadressen-URIs zum zu befassen der <xref:System.ServiceModel.ServiceHost> Konstruktor oder durch Bereitstellen einer [ \<Host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) Element in der Konfiguration des Diensts. Dienste, die in IIS gehostet werden, können ihre Basisadressen nicht steuern. Die Basisadresse eines IIS-gehosteten Diensts ist die Adresse seiner SVC-Datei.  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a>Endpunktadressen für IIS-gehostete Dienste  
 Wenn ein Dienst in IIS gehostet wird, werden Endpunktadressen als relativ zur Adresse der SVC-Datei betrachtet, die den Dienst darstellt. Wenn die Basisadresse eines WCF-Diensts ist z. B. http://localhost/Application1/MyService.svc mit der folgenden Endpunktkonfiguration.  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 Dadurch wird ein Endpunkt, der zu erreichen unter "http://localhost/Application1/MyService.svc/anotherEndpoint".  
  
 Auf ähnliche Weise die Endpunkt-Konfigurationselement, das eine leere Zeichenfolge verwendet werden, da die relative Adresse einen Endpunkt unter bietet http://localhost/Application1/MyService.svc, dies ist die Basisadresse.  
  
```xml  
<endpoint address="" ... />  
```  
  
 Sie müssen immer relative Endpunktadressen für IIS-gehostete Dienstendpunkte verwenden. Angabe einer vollständig qualifizierten Endpunktadresse (z. B. http://localhost/MyService.svc) kann zu Fehlern bei der Bereitstellung des Diensts führen, wenn die Endpunktadresse nicht auf die IIS-Anwendung verweist, der den Endpunkt verfügbar machen Dienst hostet. Durch die Verwendung relativer Endpunktadressen für gehostete Dienste werden diese potenziellen Konflikte vermieden.  
  
### <a name="available-transports"></a>Verfügbare Transporte  
 WCF-Diensten in IIS 5.1 und [!INCLUDE[iis601](../../../../includes/iis601-md.md)] auf die Verwendung von HTTP-basierten Kommunikation beschränkt sind. Auf diesen IIS-Plattformen führt das Konfigurieren eines gehosteten Diensts für die Verwendung einer Nicht-HTTP-Bindung zu einem Fehler während der Dienstaktivierung. Die von [!INCLUDE[iisver](../../../../includes/iisver-md.md)]unterstützten Transporte umfassen HTTP, Net.TCP, Net.Pipe, Net.MSMQ und msmq.formatname für die Abwärtskompatibilität mit bestehenden MSMQ-Anwendungen.  
  
### <a name="http-transport-security"></a>HTTP-Transportsicherheit  
 IIS-gehosteten WCF-Dienste können verwenden der HTTP-transportsicherheit (z. B. HTTPS und HTTP-Authentifizierungsschemata wie Basic, Digest und integrierte Windows-Authentifizierung) als virtuelle IIS-Verzeichnis, das den Dienst enthält, die diese unterstützt Einstellungen. Die HTTP-Transportsicherheitseinstellungen der Bindung eines gehosteten Endpunkts müssen mit den Transportsicherheitseinstellungen im virtuellen IIS-Verzeichnis identisch sein, in dem sie enthalten ist.  
  
 Beispielsweise muss ein WCF-Endpunkt für die Verwendung von HTTP-Digestauthentifizierung konfiguriert in einem virtuellen IIS-Verzeichnis befinden, die auch zum Zulassen von HTTP-Digestauthentifizierung konfiguriert ist. Nicht übereinstimmende Kombinationen von Einstellungen für IIS und WCF-Endpunkt führt zu einem Fehler während der dienstaktivierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
