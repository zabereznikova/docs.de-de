---
title: Startzeit der Anwendung
ms.date: 03/30/2017
helpviewer_keywords:
- splash screen [WPF], startup time
- WPF [WPF], startup time
- startup time [WPF]
- application startup [WPF]
- performance [WPF], startup time
ms.assetid: f0ec58d8-626f-4d8a-9873-c20f95e08b96
ms.openlocfilehash: 0fae3ac1769163101dcdb183f4c5c2135354b1fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145422"
---
# <a name="application-startup-time"></a>Startzeit der Anwendung
Die Zeitspanne, die zum Starten einer WPF-Anwendung erforderlich ist, kann erheblich variieren. Dieses Thema beschreibt verschiedene Verfahren zur Reduzierung der wahrgenommenen und tatsächlichen Startzeit für eine WPF-Anwendung (Windows Presentation Foundation).  
  
## <a name="understanding-cold-startup-and-warm-startup"></a>Grundlegendes zu Kalt- und Warmstart  
 Kaltstarts treten auf, wenn die Anwendung zum ersten Mal nach einem Systemneustart gestartet wird, oder wenn Sie die Anwendung starten, schließen und sie nach längerer Zeit erneut starten. Wenn eine Anwendung startet, wenn die notwendigen Seiten (Code, statische Daten, Registrierung usw.) nicht in der Standbyliste des Speicher-Managers von Windows vorhanden sind, treten Seitenfehler auf. Zum Verschieben der Seiten in den Speicher ist Datenträgerzugriff erforderlich.  
  
 Warmstarts treten auf, wenn die meisten Seiten für die Hauptkomponenten der Common Language Runtime (CLR) bereits im Arbeitsspeicher geladen sind. Dies spart wertvolle Festplattenzugriffszeit. Dadurch startet eine verwaltete Anwendung schneller, wenn sie ein zweites Mal ausgeführt wird.  
  
## <a name="implement-a-splash-screen"></a>Implementieren eines Begrüßungsbildschirms  
 In Fällen, in denen eine erhebliche unvermeidliche Verzögerung zwischen dem Starten einer Anwendung und dem Anzeigen der ersten Benutzeroberfläche besteht, können Sie die wahrgenommene Startzeit optimieren, indem Sie einen *Begrüßungsbildschirm* verwenden. Dieser Ansatz zeigt ein Bild fast unmittelbar nachdem der Benutzer die Anwendung startet. Wenn die Anwendung zum Anzeigen der ersten Benutzeroberfläche bereit ist, wird der Begrüßungsbildschirm ausgeblendet. Ab .NET Framework 3.5 SP1 können <xref:System.Windows.SplashScreen> Sie die Klasse verwenden, um einen Begrüßungsbildschirm zu implementieren. Weitere Informationen finden Sie unter [Add a Splash Screen to a WPF Application (Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung)](../app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
 Sie können auch einen eigenen Begrüßungsbildschirm mit nativen Win32-Grafiken implementieren. Zeigen Sie Ihre <xref:System.Windows.Application.Run%2A> Implementierung an, bevor die Methode aufgerufen wird.  
  
## <a name="analyze-the-startup-code"></a>Analysieren des Startcodes  
 Bestimmen Sie die Ursache für einen langsamen Kaltstart. Datenträger-E/A kann dafür verantwortlich sein, dies ist aber nicht immer der Fall. Im Allgemeinen sollten Sie die Verwendung externer Ressourcen, z.B. Netzwerk, Webdienste oder Datenträger minimieren.  
  
 Stellen Sie vor dem Testen sicher, dass keine anderen ausgeführten Anwendungen oder Dienste verwalteten Code oder WPF-Code verwenden.  
  
 Starten Sie die WPF-Anwendung sofort nach einem Neustart, und bestimmen Sie, wie viel Zeit bis zur Anzeige vergeht. Wenn alle nachfolgenden Starts der Anwendung (Warmstart) viel schneller sind, wird das Problem mit den Kaltstarts höchstwahrscheinlich durch E/A verursacht.  
  
 Wenn die Probleme Ihrer Anwendung mit Kaltstarts nicht von E/A verursacht werden, ist es wahrscheinlich, dass Ihre Anwendung eine lange Initialisierung oder Berechnung durchführt, auf den Abschluss eines Ergebnisses wartet oder beim Start viel JIT-Kompilierung benötigt. In den folgenden Abschnitten werden einige dieser Situationen ausführlicher beschrieben.  
  
## <a name="optimize-module-loading"></a>Optimierung des Ladens von Modulen  
 Verwenden Sie Tools wie Process Explorer (Procexp.exe) und „Tlist.exe“, um zu bestimmen, welche Module die Anwendung lädt. Der Befehl `Tlist <pid>` zeigt alle Module an, die von einem Prozess geladen werden.  
  
 Wenn Sie z.B. keine Verbindung mit dem Internet herstellen und Sie sehen, dass „System.Web.dll“ geladen wird, verweist ein Modul in Ihrer Anwendung auf diese Assembly. Stellen Sie sicher, dass der Verweis erforderlich ist.  
  
 Verfügt die Anwendung über mehrere Module, führen Sie diese in ein einzelnes Modul zusammen. Diese Vorgehensweise erfordert weniger Aufwand beim Laden einer CLR-Assembly. Weniger Assemblys bedeutet auch, dass die CLR weniger Status verwaltet.  
  
## <a name="defer-initialization-operations"></a>Verzögern von Initialisierungsvorgängen  
 Ziehen Sie in Betracht, Initialisierungscode zurückzustellen, bis das Hauptanwendungsfenster gerendert wird.  
  
 Denken Sie daran, dass die Initialisierung möglicherweise in einem Klassenkonstruktor durchgeführt wird. Wenn der Initialisierungscode auf andere Klassen verweist, kann dies einen überlappenden Effekt verursachen, bei dem viele Konstruktoren ausgeführt werden.  
  
## <a name="avoid-application-configuration"></a>Vermeiden von Anwendungskonfiguration  
 Ziehen Sie in Betracht, die Anwendungskonfiguration zu vermeiden. Wenn eine Anwendung z.B. einfache Anforderungen an die Konfiguration und strenge Startzeitziele hat, sind Registrierungseinträge oder eine einfache INI-Datei möglicherweise eine schnellere Alternative für den Start.  
  
## <a name="utilize-the-gac"></a>Verwenden des GAC  
 Wenn eine Assembly nicht im globalen Assemblycache (Global Assembly Cache, GAC) installiert ist, kommt es zu Verzögerungen durch die Hashüberprüfung von Assemblys mit starken Namen und durch die Verifizierung von NGen-Images, wenn ein natives Image für diese Assembly auf dem Computer vorhanden ist. Die Verifizierung starker Namen wird für alle im GAC installierten Assemblys übersprungen. Weitere Informationen finden Sie unter [Gacutil.exe (Global Assembly Cache-Tool)](../../tools/gacutil-exe-gac-tool.md).  
  
## <a name="use-ngenexe"></a>Verwenden von „Ngen.exe“  
 Sie sollten die Verwendung von Native Image Generator („Ngen.exe“) für Ihre Anwendung in Betracht ziehen. Die Verwendung von „Ngen.exe“ bedeutet, dass CPU-Auslastung für mehr Datenträgerzugriff eingetauscht wird, da das von „Ngen.exe“ erzeugte Image wahrscheinlich größer ist als das MSIL-Image.  
  
 Sie sollten „Ngen.exe“ immer für Ihre Anwendung verwenden, um die Warmstartzeit zu verbessern, da dadurch die CPU-Kosten der JIT-Kompilierung des Anwendungscodes vermieden werden.  
  
 In einigen kalten Startszenarien kann die Verwendung von Ngen.exe ebenfalls hilfreich sein. Dies liegt daran, dass der JIT-Compiler (mscorjit.dll) nicht geladen werden muss.  
  
 Es kann schlimme Auswirkungen haben, gleichzeitig über NGen- und JIT-Module zu verfügen. Der Grund hierfür ist, dass „mscorjit.dll“ geladen werden muss. Wenn der JIT-Compiler auf Ihren Code ausgeführt wird, muss auf viele Seiten in den NGen-Images zugegriffen werden, wenn der JIT-Compiler die Metadaten der Assembly liest.  
  
### <a name="ngen-and-clickonce"></a>NGen und ClickOnce  
 Die Planung der Bereitstellung Ihrer Anwendung kann ebenfalls die Ladedauer beeinflussen. ClickOnce-Anwendungsbereitstellung unterstützt Ngen nicht. Wenn Sie „Ngen.exe“ für Ihre Anwendung verwenden möchten, müssen Sie einen anderen Bereitstellungsmechanismus verwenden, z.B. Windows Installer.  
  
 Weitere Informationen finden Sie unter [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).  
  
### <a name="rebasing-and-dll-address-collisions"></a>Rebase und DLL-Adresskonflikte  
 Wenn Sie „Ngen.exe“ verwenden, müssen Sie sich bewusst sein, dass die Ausführung eines Rebase auftreten kann, wenn die nativen Images in den Speicher geladen werden. Wenn eine DLL nicht an ihrer bevorzugten Basisadresse geladen wird, da dieser Adressbereich bereits zugewiesen wurde, wird das Windows-Ladeprogramm sie an einer anderen Adresse laden. Das kann viel Zeit in Anspruch nehmen.  
  
 Sie können das Tool „Virtual Address Dump“ (Vadump.exe) verwenden, um zu überprüfen, ob Module bestehen, in denen alle Seiten privat sind. Wenn dies der Fall ist, wurde das Modul möglicherweise auf eine andere Adresse zurückgesetzt. Aus diesem Grund können die Seiten nicht freigegeben werden.  
  
 Weitere Informationen zum Festlegen der Basisadresse finden Sie unter [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).  
  
## <a name="optimize-authenticode"></a>Optimieren von Authenticode  
 Überprüfen von Authenticode erhöht die Startzeit. Assemblys mit Authenticode-Signatur müssen durch die Zertifizierungsstelle (certification authority, CA) verifiziert werden. Diese Überprüfung kann zeitaufwendig sein, da es erforderlich sein kann, mehrmals mit dem Netzwerk eine Verbindung herzustellen, um die aktuellen Zertifikatssperrlisten herunterzuladen. Es wird außerdem sichergestellt, dass eine vollständige Kette mit gültigen Zertifikaten auf dem Pfad zu einer vertrauenswürdigen Stammzertifizierungsstelle besteht. Dies kann mehrere Sekunden Verzögerung bedeuten, während die Assembly geladen wird.  
  
 Installieren Sie das Zertifikat der Zertifizierungsstelle auf dem Clientcomputer oder verwenden Sie Authenticode wenn möglich nicht. Wenn Sie wissen, dass für Ihre Anwendung kein Herausgeberbeweis erforderlich ist, müssen Sie nicht die Kosten für die Überprüfung der Signatur tragen.  
  
 Ab .NET Framework 3.5 gibt es eine Konfigurationsoption, mit der die Authenticode-Überprüfung umgangen werden kann. Fügen Sie hierzu die folgende Einstellung zur Datei „app.exe.config“ hinzu:  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>
    </runtime>  
</configuration>  
```  
  
 Weitere Informationen finden Sie [ \<unter generatePublisherEvidence> Element](../../configure-apps/file-schema/runtime/generatepublisherevidence-element.md).  
  
## <a name="compare-performance-on-windows-vista"></a>Vergleichen der Leistung unter Windows Vista  
 Der Speicher-Manager in Windows Vista verfügt über eine Technologie namens SuperFetch. SuperFetch analysiert im Lauf der Zeit Speicherauslastungsmuster, um den optimalen Speicherinhalt für einen bestimmten Benutzer zu bestimmen. SuperFetch arbeitet fortlaufend, um diesen Inhalt jederzeit beizubehalten.  
  
 Dieser Ansatz unterscheidet sich von der in Windows XP verwendeten Vorabruf-Technik, bei der Daten ohne Analyse der Verwendungsmuster in den Speicher geladen werden. Wenn der Benutzer Ihre WPF-Anwendung häufig unter Windows Vista verwendet, kann sich die Kaltstartzeit Ihrer Anwendung mit der Zeit verbessern.  
  
## <a name="use-appdomains-efficiently"></a>Effiziente Verwendung von AppDomains  
 Laden Sie Assemblys wenn möglich in einen domänenneutralen Codebereich, um sicherzustellen, dass das native Image (falls vorhanden) in allen AppDomains verwendet wird, die in der Anwendung erstellt wurden.  
  
 Erzwingen Sie für die beste Leistung effiziente domänenübergreifende Kommunikation durch Reduzierung von domänenübergreifenden Aufrufen. Verwenden Sie nach Möglichkeit Aufrufe ohne Argumente oder mit primitiven Typargumenten.  
  
## <a name="use-the-neutralresourceslanguage-attribute"></a>Verwenden des NeutralResourcesLanguage-Attributs  
 Verwenden <xref:System.Resources.NeutralResourcesLanguageAttribute> Sie die , um <xref:System.Resources.ResourceManager>die neutrale Kultur für die anzugeben. Dadurch werden nicht erfolgreiche Assembly-Suchvorgänge vermieden.  
  
## <a name="use-the-binaryformatter-class-for-serialization"></a>Verwenden der BinaryFormatter-Klasse für die Serialisierung  
 Wenn Sie die Serialisierung <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> verwenden müssen, <xref:System.Xml.Serialization.XmlSerializer> verwenden Sie die Klasse anstelle der Klasse. Die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Klasse wird in der Basisklassenbibliothek (Base Class Library, BCL) in der Assembly mscorlib.dll implementiert. Die <xref:System.Xml.Serialization.XmlSerializer> ist in der Assembly System.Xml.dll implementiert, die möglicherweise eine zusätzliche DLL zum Laden darstellt.  
  
 Wenn Sie die <xref:System.Xml.Serialization.XmlSerializer> Klasse verwenden müssen, können Sie eine bessere Leistung erzielen, wenn Sie die Serialisierungsassembly vorab generieren.  
  
## <a name="configure-clickonce-to-check-for-updates-after-startup"></a>Konfigurieren von ClickOnce zum Suchen nach Updates nach dem Start  
 Wenn Ihre Anwendung ClickOnce verwendet, vermeiden Sie den Netzwerkzugriff beim Start, indem Sie ClickOnce so konfigurieren, dass die Bereitstellungssite nach dem Start der Anwendung auf Updates überprüft wird.  
  
 Wenn Sie das XBAP-Modell (XAML-Browseranwendung) verwenden, beachten Sie, dass ClickOnce die Bereitstellungssite auf Updates überprüft, auch wenn sich der XBAP bereits im ClickOnce-Cache befindet. Weitere Informationen finden Sie unter [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="configure-the-presentationfontcache-service-to-start-automatically"></a>Automatische Konfiguration des PresentationFontCache-Dienstes zum Automatischen Start  
 Die erste WPF-Anwendung, die nach einem Neustart ausgeführt wird, ist der PresentationFontCache-Dienst. Der Dienst speichert die Systemschriftarten zwischen, verbessert den Zugriff auf Schriftarten und verbessert die allgemeine Leistung. Es besteht ein Mehraufwand beim Starten des Dienstes. In manchen gesteuerten Umgebungen sollten Sie den Dienst so konfigurieren, dass er automatisch bei Neustart des Systems startet.  
  
## <a name="set-data-binding-programmatically"></a>Festlegen von programmgesteuerter Datenbindung  
 Anstatt XAML zum Deklarieren des <xref:System.Windows.FrameworkElement.DataContext%2A> Deklarativs für das Hauptfenster <xref:System.Windows.Application.OnActivated%2A> zu verwenden, sollten Sie es programmgesteuert in der Methode festlegen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.SplashScreen>
- <xref:System.AppDomain>
- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- <xref:System.Resources.ResourceManager>
- [Add a Splash Screen to a WPF Application (Hinzufügen eines Begrüßungsbildschirms zu einer WPF-Anwendung)](../app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)
- [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md)
- [\<generatePublisherEvidence> Element](../../configure-apps/file-schema/runtime/generatepublisherevidence-element.md)
