---
title: Bereitstellen eines IIS-gehosteten WCF-Diensts
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 59f18d8487deb52f5ecb5b5c814ec9bdbc74e2cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496379"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts
Entwickeln und Bereitstellen eines Windows Communication Foundation (WCF)-Diensts, das in Internet Information Services (IIS) gehostet wird umfasst die folgenden Aufgaben:  
  
-   Stellen Sie sicher, dass IIS, ASP.NET, WCF und WCF-Aktivierung-Komponente ordnungsgemäß installiert und registriert sind.  
  
-   Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung.  
  
-   Erstellen Sie eine SVC-Datei für den WCF-Dienst.  
  
-   Bereitstellen der Dienstimplementierung für die IIS-Anwendung.  
  
-   Konfigurieren Sie den WCF-Dienst.  
  
 Eine ausführliche exemplarische Vorgehensweise zum Erstellen eines IIS-gehosteten WCF-Diensts finden Sie unter [Gewusst wie: Hosten eines WCF-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Sicherstellen, dass IIS, ASP.NET und WCF ordnungsgemäß installiert und registriert sind  
 WCF, IIS und ASP.NET müssen für IIS-gehosteten WCF-Dienste ordnungsgemäß installiert werden. Das Verfahren zum Installieren von WCF (als Teil der [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET und IIS variiert je nach der Version des Betriebssystems verwendet wird. Weitere Informationen zum Installieren von WCF und die [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], finden Sie unter [Microsoft .NET Framework 4-Webinstaller](http://go.microsoft.com/fwlink/?LinkId=201185). Anweisungen zum Installieren von IIS finden Sie unter [Installieren von IIS](http://go.microsoft.com/fwlink/?LinkId=201188).  
  
 Der Installationsvorgang für den [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] WCF automatisch bei IIS registriert, wenn IIS bereits auf dem Computer vorhanden ist. Wenn IIS installiert ist, nach der [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], ein zusätzlicher Schritt ist erforderlich, um WCF bei IIS registrieren und [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Gehen Sie hierzu je nach Betriebssystem wie folgt vor:  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], Windows 7 und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: Verwenden der [ServiceModel Registration-Tool (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) Tool WCF mit IIS zu registrieren: um dieses Tool verwenden zu können, geben **ServiceModelReg.exe/i/x** in Visual Studio eine Eingabeaufforderung. Sie können diese Eingabeaufforderung öffnen, indem Sie auf die Schaltfläche „Start“ klicken und dann **Alle Programme**, **Microsoft Visual Studio 2012**, **Visual Studio Tools**und **Visual Studio-Eingabeaufforderung**auswählen.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: Installieren Sie die Unterkomponente „Windows Communication Foundation-Aktivierungskomponenten“ von [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Klicken Sie hierzu in der Systemsteuerung auf **Software** und dann **hinzufügen\/Windows-Komponenten entfernen**. Dadurch wird der **Assistent für Windows-Komponenten**aktiviert.  
  
-   Windows 7:  
  
 Abschließend müssen Sie sich sicherstellen, dass ASP.NET für die Verwendung von .NET Framework Version 4 konfiguriert ist. Führen Sie hierzu das Tool ASPNET_Regiis mit der Option –i aus. Weitere Informationen finden Sie unter [ASP.NET IIS-Registrierungstool](http://go.microsoft.com/fwlink/?LinkId=201186)  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen ASP.NET-Anwendung  
 IIS-gehostete WCF-Dienste müssen innerhalb einer iisanwendung befinden. Sie können eine neue IIS‑Anwendung zum Hosten von WCF-Diensten ausschließlich erstellen. Alternativ können Sie einen WCF-Dienst bereitstellen, in eine vorhandene Anwendung, die bereits hostet [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] Inhalt (z. B. aspx-Seiten und ASP.NET-Webdienste [ASMX]). Weitere Informationen zu diesen Optionen finden Sie unter die "Hosting WCF Seite-an-Seite mit ASP.NET" und "Hosting WCF-Dienste im ASP.NET-Kompatibilitätsmodus" im Berichtsbereiche [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
 Beachten Sie, dass [!INCLUDE[iis601](../../../../includes/iis601-md.md)] und höhere Versionen in regelmäßigen Abständen eine isolierte objektorientierte Programmierungsanwendung neu starten. Der Standardwert ist 1740 Minuten. Der höchstmögliche Wert sind 71.582 Minuten. Dieser Neustart kann deaktiviert werden. Weitere Informationen zu dieser Eigenschaft finden Sie unter der [PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968).  
  
## <a name="create-an-svc-file-for-the-wcf-service"></a>Erstellen einer SVC-Datei für den WCF-Dienst  
 In IIS gehostete WCF-Dienste werden als spezielle Inhaltsdateien (SVC-Dateien) in der IIS-Anwendung dargestellt. Dieses Modell ähnelt der Art und Weise, wie ASMX-Seiten in einer IIS-Anwendung als ASMX-Dateien dargestellt werden. Eine SVC-Datei enthält einen WCF-spezifische verarbeitungsanweisung ([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)), mit der die WCF-Hostinfrastruktur gehostete Dienste als Reaktion auf eingehende Nachrichten zu aktivieren. Die gebräuchlichste Syntax für eine SVC-Datei befindet sich in der folgenden Anweisung:  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 Sie besteht aus der [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive und einem einzelnen Attribut: `Service`. Der Wert des `Service` -Attributs ist der CLR-Typname (Common Language Runtime) der Dienstimplementierung. Die Verwendung dieser Direktive ist praktisch mit der Erstellung eines Diensthosts mithilfe des folgenden Codes gleichzusetzen:  
  
```  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 Zudem kann eine zusätzliche Hostkonfiguration vorgenommen werden, indem z.&#160;B. eine Liste mit Basisadressen für den Dienst erstellt wird. Sie können auch eine benutzerdefinierte <xref:System.ServiceModel.Activation.ServiceHostFactory> verwenden, um die Direktive zur Verwendung mit benutzerdefinierten Hostlösungen zu erweitern. Die IIS-Anwendungen, die WCF-Dienste hosten sind nicht verantwortlich für die Verwaltung der Erstellung und Gültigkeitsdauer von <xref:System.ServiceModel.ServiceHost> Instanzen. Die verwaltete WCF-Hostinfrastruktur erstellt die notwendige <xref:System.ServiceModel.ServiceHost> -Instanz dynamisch, sobald die erste Anforderung für die SVC-Datei empfangen wird. Die Instanz wird erst freigegeben, wenn sie entweder explizit durch Code geschlossen oder die Anwendung wiederverwendet wird.  
  
 Weitere Informationen zur Syntax für SVC-Dateien finden Sie unter [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).  
  
## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Bereitstellen der Dienstimplementierung für die IIS-Anwendung  
 In IIS gehostete WCF-Dienste verwenden das gleiche dynamische Kompilierungsmodell wie [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]. Wie bei [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], können Sie den Implementierungscode für IIS-gehosteten WCF-Dienste auf unterschiedliche Weise an verschiedenen Speicherorten folgendermaßen bereitstellen:  
  
-   Als vorkompilierte DLL im globalen Assemblycache (GAC) oder im \bin-Verzeichnis der Anwendung. Vorkompilierte Binärdateien werden erst aktualisiert, wenn eine neue Version der Klassenbibliothek bereitgestellt wird.  
  
-   Als nichtkompilierte Quelldateien im \App_Code-Verzeichnis der Anwendung. Quelldateien in diesem Verzeichnis werden dynamisch angefordert, wenn die erste Anforderung der Anwendung verarbeitet wird. Änderungen an Dateien im \App_Code-Verzeichnis führen dazu, dass die gesamte Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.  
  
-   Als nichtkompilierter Code, der direkt in die SVC-Datei eingefügt wird. Implementierungscode kann auch sich Inline in der SVC Datei, nach der @ServiceHost Richtlinie. Änderungen an Inlinecode führen dazu, dass die Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.  
  
 Weitere Informationen zu den [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] -Kompilierungsmodell finden Sie unter [Übersicht über die ASP.NET-Kompilierung](http://go.microsoft.com/fwlink/?LinkId=94773).  
  
## <a name="configure-the-wcf-service"></a>Konfigurieren des WCF-Diensts  
 IIS-gehostete WCF-Dienste speichern ihre Konfiguration in der Datei "Web.config" der Anwendung. IIS-gehostete Dienste verwenden die gleichen Konfigurationselemente und die Syntax als WCF-Dienste, die außerhalb von IIS gehostet. Jedoch gelten die folgenden Einschränkungen nur für die IIS-Hostumgebung:  
  
-   Basisadressen für IIS-gehostete Dienste  
  
-   Hosting außerhalb von IIS WCF-Dienste können die Basisadresse der Dienste, die sie hosten, indem Sie einen Satz Basisadressen übergeben steuern Anwendungen behandeln URIs der <xref:System.ServiceModel.ServiceHost> Konstruktor oder durch Eingabe einer [ \<Host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) Element in der Konfiguration des Diensts. Dienste, die in IIS gehostet werden, können ihre Basisadressen nicht steuern. Die Basisadresse eines IIS-gehosteten Diensts ist die Adresse seiner SVC-Datei.  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a>Endpunktadressen für IIS-gehostete Dienste  
 Wenn ein Dienst in IIS gehostet wird, werden Endpunktadressen als relativ zur Adresse der SVC-Datei betrachtet, die den Dienst darstellt. Wenn die Basisadresse eines WCF-Diensts ist z. B. http://localhost/Application1/MyService.svc mit Endpunktkonfiguration.  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 Dies bietet einen Endpunkt, der am erreicht werden kann "http://localhost/Application1/MyService.svc/anotherEndpoint".  
  
 Auf ähnliche Weise die Endpunkt-Konfigurationselement, das eine leere Zeichenfolge verwendet wird, wie die relative Adresse erreichbar am Endpunkt stellt http://localhost/Application1/MyService.svc, dies ist die Basisadresse.  
  
```xml  
<endpoint address="" ... />  
```  
  
 Sie müssen immer relative Endpunktadressen für IIS-gehostete Dienstendpunkte verwenden. Eine vollständig qualifizierten Endpunktadresse angeben (z. B. http://localhost/MyService.svc) kann zu Fehlern bei der Bereitstellung des Diensts führen, wenn die Endpunktadresse nicht auf die IIS-Anwendung verweist, der den Endpunkt verfügbar macht Dienst hostet. Durch die Verwendung relativer Endpunktadressen für gehostete Dienste werden diese potenziellen Konflikte vermieden.  
  
### <a name="available-transports"></a>Verfügbare Transporte  
 In IIS 5.1 gehosteten WCF-Diensten und [!INCLUDE[iis601](../../../../includes/iis601-md.md)] auf die Verwendung von HTTP-basierten Kommunikation beschränkt sind. Auf diesen IIS-Plattformen führt das Konfigurieren eines gehosteten Diensts für die Verwendung einer Nicht-HTTP-Bindung zu einem Fehler während der Dienstaktivierung. Die von [!INCLUDE[iisver](../../../../includes/iisver-md.md)]unterstützten Transporte umfassen HTTP, Net.TCP, Net.Pipe, Net.MSMQ und msmq.formatname für die Abwärtskompatibilität mit bestehenden MSMQ-Anwendungen.  
  
### <a name="http-transport-security"></a>HTTP-Transportsicherheit  
 IIS-gehostete WCF-Dienste können Nutzen des HTTP-transportsicherheit (beispielsweise https- und HTTP-Authentifizierungsschemata wie Basic, Digest und integrierte Windows-Authentifizierung) als das virtuelle IIS-Verzeichnis mit dem Dienst die unterstützt Einstellungen. Die HTTP-Transportsicherheitseinstellungen der Bindung eines gehosteten Endpunkts müssen mit den Transportsicherheitseinstellungen im virtuellen IIS-Verzeichnis identisch sein, in dem sie enthalten ist.  
  
 Beispielsweise muss ein WCF-Endpunkt für die Verwendung von HTTP-Digestauthentifizierung konfiguriert in einem virtuellen IIS-Verzeichnis befinden, die auch so konfiguriert ist, dass die HTTP-Digestauthentifizierung zulässt. Nicht übereinstimmende Kombinationen von IIS-Einstellungen und WCF-Endpunkt führen zu einem Fehler während der dienstaktivierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
