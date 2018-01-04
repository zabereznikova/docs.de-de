---
title: Bereitstellen eines IIS-gehosteten WCF-Diensts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 869e3b81e94e6efaa8d6cd9f4f021b52b6b43f48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts
Das Entwickeln und Bereitstellen eines [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] -Diensts, der in Internetinformationsdienste (IIS) gehostet wird, umfasst die folgenden Aufgaben:  
  
-   Sicherstellen, dass IIS, ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]und die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Aktivierungskomponente ordnungsgemäß installiert und registriert sind  
  
-   Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung.  
  
-   Erstellen einer SVC-Datei für den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienst.  
  
-   Bereitstellen der Dienstimplementierung für die IIS-Anwendung.  
  
-   Konfigurieren des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensts.  
  
 Eine ausführliche exemplarische Vorgehensweise zur Erstellung eines IIS-gehosteten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensts finden Sie unter [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>Sicherstellen, dass IIS, ASP.NET und WCF ordnungsgemäß installiert und registriert sind  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], IIS und ASP.NET müssen installiert sein, damit IIS-gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste einwandfrei funktionieren. Die Vorgehensweise zur Installation von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (als Teil von [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET und IIS variiert je nach verwendeter Betriebssystemversion. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Installation von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]finden Sie unter [Microsoft .NET Framework 4 (Web Installer)](http://go.microsoft.com/fwlink/?LinkId=201185). Anweisungen zum Installieren von IIS finden Sie unter [Installieren von IIS](http://go.microsoft.com/fwlink/?LinkId=201188).  
  
 Beim Installationsprozess für [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] wird [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatisch für IIS registriert, wenn IIS bereits auf dem Computer installiert ist. Wenn IIS nach [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]installiert wird, ist ein zusätzlicher Schritt erforderlich, um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] für IIS und [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]zu registrieren. Gehen Sie hierzu je nach Betriebssystem wie folgt vor:  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], Windows 7 und [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: Verwenden der [ServiceModel Registration-Tool (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) Tool registrieren [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit IIS: um dieses Tool verwenden zu können, geben **ServiceModelReg.exe/i/x** in der Visual Studio-Eingabeaufforderung. Sie können diese Eingabeaufforderung öffnen, indem Sie auf die Schaltfläche „Start“ klicken und dann **Alle Programme**, **Microsoft Visual Studio 2012**, **Visual Studio Tools**und **Visual Studio-Eingabeaufforderung**auswählen.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: Installieren Sie die Unterkomponente „Windows Communication Foundation-Aktivierungskomponenten“ von [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]. Klicken Sie hierzu in der Systemsteuerung auf **Software** und dann **hinzufügen\/Windows-Komponenten entfernen**. Dadurch wird der **Assistent für Windows-Komponenten**aktiviert.  
  
-   Windows 7:  
  
 Abschließend müssen Sie sich sicherstellen, dass ASP.NET für die Verwendung von .NET Framework Version 4 konfiguriert ist. Führen Sie hierzu das Tool ASPNET_Regiis mit der Option –i aus. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ASP.NET IIS-Registrierungstool](http://go.microsoft.com/fwlink/?LinkId=201186)  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen ASP.NET-Anwendung  
 IIS-gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste müssen sich innerhalb einer IIS-Anwendung befinden. Sie können eine neue IIS-Anwendung erstellen, um ausschließlich [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste zu hosten. Alternativ können Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienst in einer vorhandenen Anwendung bereitstellen, die bereits [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] -Inhalt hostet (z. B. ASPX-Seiten und ASP.NET-Webdienste [ASMX]). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] über diese Optionen finden Sie in den Abschnitten „Paralleles Hosten in WCF und in ASP.NET“ und „Hosten von WCF-Diensten im ASP.NET-Kompatibilitätsmodus“ unter [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
 Beachten Sie, dass [!INCLUDE[iis601](../../../../includes/iis601-md.md)] und höhere Versionen in regelmäßigen Abständen eine isolierte objektorientierte Programmierungsanwendung neu starten. Der Standardwert ist 1740 Minuten. Der höchstmögliche Wert sind 71.582 Minuten. Dieser Neustart kann deaktiviert werden. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu dieser Eigenschaft finden Sie unter [PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968)(möglicherweise in englischer Sprache).  
  
## <a name="create-an-svc-file-for-the-wcf-service"></a>Erstellen einer SVC-Datei für den WCF-Dienst  
 In IIS gehostete[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste werden in der IIS-Anwendung als spezielle Inhaltsdateien (SVC-Dateien) dargestellt. Dieses Modell ähnelt der Art und Weise, wie ASMX-Seiten in einer IIS-Anwendung als ASMX-Dateien dargestellt werden. Eine SVC-Datei enthält eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-spezifische Verarbeitungsdirektive ([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)), die es der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Hostinfrastruktur ermöglicht, gehostete Dienste als Reaktion auf eingehende Nachrichten zu aktivieren. Die gebräuchlichste Syntax für eine SVC-Datei befindet sich in der folgenden Anweisung:  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 Sie besteht aus der [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) -Direktive und einem einzelnen Attribut: `Service`. Der Wert des `Service` -Attributs ist der CLR-Typname (Common Language Runtime) der Dienstimplementierung. Die Verwendung dieser Direktive ist praktisch mit der Erstellung eines Diensthosts mithilfe des folgenden Codes gleichzusetzen:  
  
```  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 Zudem kann eine zusätzliche Hostkonfiguration vorgenommen werden, indem z.&#160;B. eine Liste mit Basisadressen für den Dienst erstellt wird. Sie können auch eine benutzerdefinierte <xref:System.ServiceModel.Activation.ServiceHostFactory> verwenden, um die Direktive zur Verwendung mit benutzerdefinierten Hostlösungen zu erweitern. Die IIS-Anwendungen, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste hosten, sind nicht für die Verwaltung der Erstellung und der Lebensdauer von <xref:System.ServiceModel.ServiceHost> -Instanzen verantwortlich. Die verwaltete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Hostinfrastruktur erstellt die notwendige <xref:System.ServiceModel.ServiceHost> -Instanz dynamisch, sobald die erste Anforderung für die SVC-Datei empfangen wird. Die Instanz wird erst freigegeben, wenn sie entweder explizit durch Code geschlossen oder die Anwendung wiederverwendet wird.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] über die Syntax für SVC-Dateien finden Sie unter [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md).  
  
## <a name="deploy-the-service-implementation-to-the-iis-application"></a>Bereitstellen der Dienstimplementierung für die IIS-Anwendung  
 In IIS gehostete[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste verwenden das gleiche dynamische Kompilierungsmodell wie [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]. Wie bei [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]können Sie den Implementierungscode für IIS-gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste auf unterschiedliche Weise an verschiedenen Speicherorten folgendermaßen bereitstellen:  
  
-   Als vorkompilierte DLL im globalen Assemblycache (GAC) oder im \bin-Verzeichnis der Anwendung. Vorkompilierte Binärdateien werden erst aktualisiert, wenn eine neue Version der Klassenbibliothek bereitgestellt wird.  
  
-   Als nichtkompilierte Quelldateien im \App_Code-Verzeichnis der Anwendung. Quelldateien in diesem Verzeichnis werden dynamisch angefordert, wenn die erste Anforderung der Anwendung verarbeitet wird. Änderungen an Dateien im \App_Code-Verzeichnis führen dazu, dass die gesamte Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.  
  
-   Als nichtkompilierter Code, der direkt in die SVC-Datei eingefügt wird. Implementierungscode kann auch sich Inline in der SVC Datei, nach der @ServiceHost Richtlinie. Änderungen an Inlinecode führen dazu, dass die Anwendung wiederverwendet und neu kompiliert wird, wenn die nächste Anforderung empfangen wird.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] über das [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] -Kompilierungsmodell finden Sie unter [Übersicht über die ASP.NET-Kompilierung](http://go.microsoft.com/fwlink/?LinkId=94773)(möglicherweise in englischer Sprache).  
  
## <a name="configure-the-wcf-service"></a>Konfigurieren des WCF-Diensts  
 IIS-gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste speichern ihre Konfiguration in der Web.config-Datei der Anwendung. IIS-gehostete Dienste verwenden die gleichen Konfigurationselemente und die gleiche Syntax wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste, die außerhalb von IIS gehostet werden. Jedoch gelten die folgenden Einschränkungen nur für die IIS-Hostumgebung:  
  
-   Basisadressen für IIS-gehostete Dienste  
  
-   Hosten von Anwendungen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienste außerhalb von IIS können die Basisadresse der Dienste, die sie hosten, indem Sie übergeben ein Satz Basisadressen-URIs zum Steuern der <xref:System.ServiceModel.ServiceHost> Konstruktor oder durch Bereitstellen einer [ \<Host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) Element in der Konfiguration des Diensts. Dienste, die in IIS gehostet werden, können ihre Basisadressen nicht steuern. Die Basisadresse eines IIS-gehosteten Diensts ist die Adresse seiner SVC-Datei.  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a>Endpunktadressen für IIS-gehostete Dienste  
 Wenn ein Dienst in IIS gehostet wird, werden Endpunktadressen als relativ zur Adresse der SVC-Datei betrachtet, die den Dienst darstellt. Beispiel: Die Basisadresse eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensts ist http://localhost/Application1/MyService.svc und die Endpunktkonfiguration folgendermaßen:  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 Dadurch wird ein Endpunkt bereitgestellt, der unter http://localhost/Application1/MyService.svc/anotherEndpoint erreichbar ist.  
  
 Ähnlich stellt das Endpunktkonfigurationselement, das eine leere Zeichenfolge als relative Adresse verwendet, einen Endpunkt bereit, der unter http://localhost/Application1/MyService.svc (der Basisadresse) erreichbar ist.  
  
```xml  
<endpoint address="" ... />  
```  
  
 Sie müssen immer relative Endpunktadressen für IIS-gehostete Dienstendpunkte verwenden. Durch die Angabe einer vollständig qualifizierten Endpunktadresse (z.&#160;B. http://localhost/MyService.svc) kann es zu Fehlern bei der Bereitstellung des Diensts kommen, wenn die Endpunktadresse nicht auf die IIS-Anwendung verweist, die den Dienst hostet, der den Endpunkt verfügbar macht. Durch die Verwendung relativer Endpunktadressen für gehostete Dienste werden diese potenziellen Konflikte vermieden.  
  
### <a name="available-transports"></a>Verfügbare Transporte  
 In IIS&#160;5.1 und[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gehostete [!INCLUDE[iis601](../../../../includes/iis601-md.md)] -Dienste sind auf die Verwendung der HTTP-basierten Kommunikation beschränkt. Auf diesen IIS-Plattformen führt das Konfigurieren eines gehosteten Diensts für die Verwendung einer Nicht-HTTP-Bindung zu einem Fehler während der Dienstaktivierung. Die von [!INCLUDE[iisver](../../../../includes/iisver-md.md)]unterstützten Transporte umfassen HTTP, Net.TCP, Net.Pipe, Net.MSMQ und msmq.formatname für die Abwärtskompatibilität mit bestehenden MSMQ-Anwendungen.  
  
### <a name="http-transport-security"></a>HTTP-Transportsicherheit  
 IIS-gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste können die http-Transportsicherheit nutzen (beispielsweise HTTPS- und HTTP-Authentifizierungsschemata wie Basic, Digest und die integrierte Windows-Authentifizierung), sofern das virtuelle IIS-Verzeichnis, das den Dienst enthält, diese Einstellungen unterstützt. Die HTTP-Transportsicherheitseinstellungen der Bindung eines gehosteten Endpunkts müssen mit den Transportsicherheitseinstellungen im virtuellen IIS-Verzeichnis identisch sein, in dem sie enthalten ist.  
  
 Ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Endpunkt, der zur Verwendung von HTTP-Digestauthentifizierung konfiguriert wurde, muss beispielsweise in einem virtuellen IIS-Verzeichnis enthalten sein, dessen Konfiguration ebenfalls die HTTP-Digestauthentifizierung zulässt. Kombinationen von IIS-Einstellungen und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Endpunkteinstellungen ohne Entsprechung führen während der Dienstaktivierung zu einem Fehler.  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
