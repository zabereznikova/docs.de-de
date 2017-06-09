---
title: "Startzeit der Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungsstart [WPF]"
  - "Leistung [WPF], Startzeit"
  - "Begrüßungsbildschirm [WPF], Startzeit"
  - "Startzeit [WPF]"
  - "WPF, Startzeit"
ms.assetid: f0ec58d8-626f-4d8a-9873-c20f95e08b96
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Startzeit der Anwendung
Die Zeit, die zum Starten einer WPF\-Anwendung erforderlich ist, kann enorm variieren.  In diesem Thema werden verschiedene Methoden beschrieben, mit denen die wahrgenommene und tatsächliche Startzeit für eine WPF\-Anwendung \(Windows Presentation Foundation\) reduziert werden.  
  
## Grundlegendes zu Kalt\- und Warmstarts  
 Kaltstarts treten auf, wenn die Anwendung zum ersten Mal nach einem Systemneustart aufgerufen wird oder wenn Sie die Anwendung starten, schließen und nach einem längeren Zeitraum neu starten.  Wenn eine Anwendung gestartet wird, treten Seitenfehler auf, falls die notwendigen Seiten \(Code, statische Daten, Registrierung usw.\) nicht in der Standbyliste des Windows\-Speicher\-Managers enthalten sind.  Es ist ein Festplattenzugriff erforderlich, um die Seiten in den Arbeitsspeicher zu holen.  
  
 Ein Warmstart findet statt, wenn die meisten Seiten für die CLR\-Hauptkomponenten bereits im Arbeitsspeicher geladen sind, wodurch kostenintensive Festplattenzugriffszeit eingespart wird.  Dies ist der Grund, warum eine verwaltete Anwendung schneller startet, wenn sie ein zweites Mal ausgeführt wird.  
  
## Implementieren eines Begrüßungsbildschirms  
 In den Fällen, in denen es eine erhebliche, nicht zu vermeidende Verzögerung zwischen dem Starten einer Anwendung und dem Anzeigen der ersten Benutzeroberfläche gibt, können Sie die wahrgenommene Startzeit mithilfe eines *Begrüßungsbildschirms* optimieren.  Bei dieser Methode wird fast unmittelbar, nachdem der Benutzer die Anwendung gestartet hat, ein Bild angezeigt.  Wenn die Anwendung bereit ist, die erste Benutzeroberfläche anzuzeigen, wird der Begrüßungsbildschirm ausgeblendet.  Wenn Sie in [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] starten, können Sie für die Implementierung eines Begrüßungsbildschirms die <xref:System.Windows.SplashScreen>\-Klasse verwenden.  Weitere Informationen hierzu finden Sie unter [Hinzufügen eines Begrüßungsbildschirms zu einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
 Sie können auch einen eigenen Begrüßungsbildschirm mit systemeigenen Win32\-Grafiken implementieren.  Zeigen Sie die Implementierung an, bevor die <xref:System.Windows.Application.Run%2A>\-Methode aufgerufen wird.  
  
## Analysieren des Startcodes  
 Ermitteln Sie die Ursache für einen langsamen Kaltstart.  Ein Datenträger\-E\/A ist möglicherweise die Ursache, aber dies ist nicht immer der Fall.  Im Allgemeinen sollten Sie die Verwendung externer Ressourcen, wie z. B. Netzwerk, Webdienste oder Datenträger, minimieren.  
  
 Bevor Sie testen, überprüfen Sie, dass keine anderen ausgeführten Anwendungen oder Dienste verwalteten Code oder WPF\-Code verwenden.  
  
 Starten Sie sofort nach einem Neustart die WPF\-Anwendung, und notieren Sie, wie lange es dauert, bis die Anzeige erfolgt.  Falls alle nachfolgenden Starts der Anwendung \(Warmstart\) viel schneller sind, wird das Kaltstartproblem wahrscheinlich von E\/A ausgelöst.  
  
 Falls das Kaltstartproblem Ihrer Anwendung nicht auf E\/A zurückzuführen ist, kann es vorkommen, dass die Anwendung einige längere Initialisierungen oder Berechnungen benötigt, darauf wartet, dass einige Ereignisse beendet werden oder beim Start eine intensive JIT\-Kompilierung erforderlich ist.  In den folgenden Abschnitten werden einige dieser Situationen ausführlicher beschrieben.  
  
## Optimieren des Modulladevorgangs  
 Verwenden Sie Tools wie den Prozess\-Explorer \(Procexp.exe\) und Tlist.exe, um zu ermitteln, welche Module von der Anwendung geladen werden.  Der Befehl `Tlist <pid>` zeigt alle Module, die von einem Prozess geladen werden.  
  
 Wenn Sie z. B. keine Verbindung mit dem Web herstellen und Sie sehen, dass die System.Web.dll geladen wird, gibt es in Ihrer Anwendung ein Modul, das auf diese Assembly verweist.  Überprüfen Sie, ob der Verweis notwendig ist.  
  
 Wenn die Anwendung über mehrere Module verfügt, führen Sie sie in einem einzigen Modul zusammen.  Für diese Methode ist weniger Aufwand zum Laden der CLR\-Assembly erforderlich.  Weniger Assemblys bedeutet auch, dass die CLR einen niedrigeren Zustand aufweist.  
  
## Verzögern von Initialisierungsoperationen  
 Erwägen Sie, den Initialisierungscode solange zu verschieben, bis das Hauptanwendungsfenster gerendert wurde.  
  
 Beachten Sie, dass die Initialisierung in einem Klassenkonstruktor durchgeführt werden kann. Falls der Initialisierungscode auf andere Klassen verweist, kann dies einen Dominoeffekt auslösen, bei dem viele Klassenkonstruktoren ausgeführt werden.  
  
## Vermeiden der Anwendungskonfiguration  
 Versuchen Sie, eine Anwendungskonfiguration zu vermeiden.  Falls eine Anwendung z. B. einfache Konfigurationsanforderungen aufweist und strenge Ziele für den Programmstart verfolgt, können die Registrierungseinträge oder eine einfache INI\-Datei eine schnellere Startalternative darstellen.  
  
## Nutzen des GACs  
 Falls eine Assembly nicht im GAC \(Global Assembly Cache, Globaler Assemblycache\) installiert ist, treten Verzögerungen aufgrund der Hashüberprüfung von Assemblys mit starken Namen und der Ngen\-Bildvalidierung auf, vorausgesetzt, ein systemeigenes Bild für diese Assembly ist auf dem Computer verfügbar.  Die Überprüfung starker Namen wird für alle im GAC installierten Assemblys übersprungen.  Weitere Informationen hierzu finden Sie unter [Gacutil.exe \(Global Assembly Cache\-Tool\)](../../../../docs/framework/tools/gacutil-exe-gac-tool.md).  
  
## Verwendung von Ngen.exe  
 Ziehen Sie die Verwendung von Ngen.exe \(Native Image Generator\) für Ihre Anwendung in Erwägung.  Die Verwendung von Ngen.exe bedeutet, CPU\-Auslastung gegen mehr Festplattenspeicher einzutauschen, da das systemeigene, von Ngen.exe generierte Bild wahrscheinlich größer ist als das MSIL\-Bild.  
  
 Um die Warmstartzeit zu verbessern, sollten Sie für Ihre Anwendung immer Ngen.exe verwenden, da dadurch die CPU\-Kosten der JIT\-Kompilierung des Anwendungscodes vermieden werden.  
  
 Bei einigen Kaltstartszenarios kann auch die Verwendung von Ngen.exe hilfreich sein.  Das liegt daran, dass der JIT\-Compiler \(mscorjit.dll\) nicht geladen werden muss.  
  
 Die Verwendung von Ngen und JIT\-Modulen kann die negativsten Auswirkungen haben.  Dies hängt damit zusammen, dass mscorjit.dll geladen werden muss. Wenn der JIT\-Compiler dann für Ihren Code ausgeführt wird, müssen beim Lesen der Assembly\-Metadaten durch den JIT\-Compiler viele Seiten in den Ngen\-Bildern aufgerufen werden.  
  
### Ngen und ClickOnce  
 Die Art und Weise, wie Sie Ihre Anwendung bereitstellen, kann auch in der Ladezeit einen Unterschied machen.  Die [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Anwendungsbereitstellung unterstützt Ngen nicht.  Falls Sie Ngen.exe für Ihre Anwendung verwenden möchten, müssen Sie einen anderen Bereitstellungsmechanismus verwenden, z. B. Windows Installer.  
  
 Weitere Informationen hierzu finden Sie unter [Ngen.exe \(Native Image Generator\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
### Zurücksetzung und DLL\-Adresskonflikte  
 Falls Sie Ngen.exe verwenden, kann eine Zurücksetzung beim Laden der systemeigenen Bilder in den Arbeitsspeicher auftreten.  Falls eine DLL nicht an der bevorzugten Basisadresse geladen werden kann, weil dieser Adressbereich bereits zugewiesen ist, lädt das Windows\-Ladeprogramm sie an einer anderen Adresse, was einen zeitaufwändigen Vorgang darstellen kann.  
  
 Sie können das Vadump.exe\-Tool \(Virtual Address Dump\) verwenden, um zu überprüfen, ob Module vorhanden sind, in denen alle Seiten privat sind.  Ist dies der Fall, wurde das Modul möglicherweise auf eine andere Adresse zurückgesetzt.  Deshalb können die Seiten nicht freigegeben werden.  
  
 Weitere Informationen zum Festlegen der Basisadresse finden Sie unter [Ngen.exe \(Native Image Generator\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
## Optimieren von Authenticode  
 Die Zeit, die eine Authenticode\-Überprüfung benötigt, wird der Startzeit hinzugefügt.  Authenticode\-signierte Assemblys müssen bei der Zertifizierungsstelle \(CA\) überprüft werden.  Diese Überprüfung kann zeitaufwändig sein, da eventuell mehrmals eine Netzwerkverbindung hergestellt werden muss, um die aktuellen Zertifikatsperrlisten \(Certificate Revocation Lists, CRLs\) herunterzuladen.  Es wird außerdem sichergestellt, dass eine vollständige Kette mit gültigen Zertifikaten im Pfad eines vertrauenswürdigen Stamms vorhanden ist.  Dies kann mehrere Sekunden Verzögerung bedeuten, während die Assembly geladen wird.  
  
 Erwägen Sie die Installation des CA\-Zertifikats auf dem Client\-Computer oder vermeiden Sie, sofern möglich, die Verwendung von Authenticode.  Falls für Sie klar ist, dass Ihre Anwendung den Herausgeberbeweis nicht benötigt, müssen Sie die Kosten der Signaturüberprüfung nicht tragen.  
  
 Wenn Sie in [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] starten, gibt es eine Konfigurationsoption, mit der die Authenticode\-Überprüfung umgangen werden kann.  Fügen Sie dazu der Datei app.exe.config die folgende Einstellung hinzu:  
  
```  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>   
    </runtime>  
</configuration>  
```  
  
 Weitere Informationen hierzu finden Sie unter [\<generatePublisherEvidence\>\-Element](../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md).  
  
## Vergleichen der Leistung unter Windows Vista  
 Der Speicher\-Manager in Windows Vista bietet eine Technologie namens SuperFetch.  SuperFetch analysiert Speicherauslastungsmuster über einen längeren Zeitraum hinweg, um den optimalen Arbeitsspeicherinhalt für einen bestimmten Benutzer zu ermitteln.  Er versucht kontinuierlich, diesen Inhalt jederzeit beizubehalten.  
  
 Diese Methode weicht von der in Windows XP verwendeten Methode ab, bei der der Inhalt vorab abgerufen wird und die Daten vorab ohne Analyse der Verwendungsmuster in den Arbeitsspeicher geladen werden.  Falls der Benutzer die WPF\-Anwendung unter Windows Vista häufig verwendet, kann sich die Kaltstartzeit Ihrer Anwendung verbessern.  
  
## Effiziente Verwendung von AppDomains  
 Laden Sie, falls möglich, Assemblys in einen domänenneutralen Codebereich, um sicherzustellen, dass das systemeigene Bild, falls vorhanden, in allen in der Anwendung erstellten AppDomains verwendet wird.  
  
 Erzwingen Sie für die optimale Leistung die domänenübergreifende Kommunikation durch die Reduzierung der domänenübergreifenden Aufrufe.  Verwenden Sie, falls möglich, Aufrufe ohne Argumente oder mit primitiven Typargumenten.  
  
## Verwenden des NeutralResourcesLanguage\-Attributs  
 Verwenden Sie das <xref:System.Resources.NeutralResourcesLanguageAttribute>, um die neutrale Kultur für den <xref:System.Resources.ResourceManager> anzugeben.  Bei dieser Methode werden erfolglose Assemblysuchen vermieden.  
  
## Verwenden der BinaryFormatter\-Klasse für die Serialisierung  
 Falls Sie die Serialisierung verwenden müssen, verwenden Sie die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>\-Klasse statt der <xref:System.Xml.Serialization.XmlSerializer>\-Klasse.  Die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>\-Klasse wird in der BCL \(Base Class Library, Basisklassenbibliothek\) der mscorlib.dll\-Assembly in der Basisklassenbibliothek implementiert.  Der <xref:System.Xml.Serialization.XmlSerializer> wird in der System.Xml.dll\-Assembly implementiert, die eine zusätzliche DLL zum Laden darstellen könnte.  
  
 Falls Sie die <xref:System.Xml.Serialization.XmlSerializer>\-Klasse verwenden müssen, erreichen Sie eine höhere Leistung, wenn Sie die Serialisierungsassembly zuvor generieren.  
  
## Konfigurieren von ClickOnce zum Suchen nach Updates nach dem Starten  
 Falls Ihre Anwendung [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] verwendet, vermeiden Sie beim Starten einen Netzwerkzugriff. Konfigurieren Sie dazu [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] so, dass die Bereitstellungssite nach Updates durchsucht wird, nachdem die Anwendung gestartet wurde.  
  
 Falls Sie das XAML\-Browseranwendungsmodell \(XBAP\) verwenden, vergessen Sie nicht, dass [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] die Bereitstellungssite nach Updates durchsucht, auch wenn XBAP bereits im [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]\-Cache vorhanden ist.  Weitere Informationen hierzu finden Sie unter [ClickOnce\-Sicherheit und Bereitstellung](../Topic/ClickOnce%20Security%20and%20Deployment.md).  
  
## Konfigurieren des PresentationFontCache\-Diensts zum automatischen Starten  
 Die erste WPF\-Anwendung, die nach einem Neustart ausgeführt wird, ist der PresentationFontCache\-Dienst.  Der Dienst speichert die Systemschriftarten, verbessert den Schriftartzugriff und die Gesamtleistung.  Beim Starten des Diensts entsteht ein zusätzlicher Aufwand. Deshalb sollten Sie bei einigen gesteuerten Umgebungen in Erwägung ziehen, den Dienst für das automatische Starten beim Systemneustart zu konfigurieren.  
  
## Festlegen der programmgesteuerten Datenbindung  
 Anstatt XAML für die deklarative Festlegung von <xref:System.Windows.FrameworkElement.DataContext%2A> für das Hauptfenster zu verwenden, sollten Sie es programmgesteuert in der <xref:System.Windows.Application.OnActivated%2A>\-Methode festlegen.  
  
## Siehe auch  
 <xref:System.Windows.SplashScreen>   
 <xref:System.AppDomain>   
 <xref:System.Resources.NeutralResourcesLanguageAttribute>   
 <xref:System.Resources.ResourceManager>   
 [Hinzufügen eines Begrüßungsbildschirms zu einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)   
 [Ngen.exe \(Native Image Generator\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)   
 [\<generatePublisherEvidence\>\-Element](../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)