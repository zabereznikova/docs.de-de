---
title: "Laufzeitänderungen in .NET Framework 4.6 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6
- application compatibility
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 77002c3d1b6553156c225b3efba9a2f29009915a
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-46"></a>Runtime-Änderungen in .NET Framework 4.6
In seltenen Fällen können sich Laufzeitänderungen auf vorhandene Apps auswirken, die auf frühere Versionen von .NET Framework abzielen, jedoch in einer älteren .NET Framework-Laufzeit ausgeführt werden. Sie umfassen auch Unterschiede im Verhalten zwischen Anwendungen, die in verschiedenen .NET Framework-Laufzeitumgebungen ausgeführt werden. Dazu zählen Änderungen in folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
-   [Data](#Data)  
  
-   [Netzwerk](#Networking)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [Setup und Bereitstellung](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Der neue 64-Bit-JIT-Compiler](#RyuJIT)  
  
<a name="Core"></a>   
## <a name="core"></a>Kernspeicher  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|Ab [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] verwendet die <xref:System.Globalization.PersianCalendar>-Klasse den Hijri-Solaralgorithmus.|Der Hijri-Solaralgorithmus gibt Ergebnisse zurück, die identisch mit denen des persischen Kalenders sind, der derzeit im Iran und in Afghanistan verwendet wird. Darüber hinaus sind die von diesem Algorithmus zurückgegebenen Ergebnisse für Datumsangaben von 1800 im gregorianischen Kalender bis 2023 im gregorianischen Kalender identisch mit denen des vorherigen Algorithmus. Datumsangaben außerhalb dieses Bereichs können abweichen, wenn die <xref:System.Globalization.PersianCalendar>-Klasse verwendet wird, um Datumsangaben zu konvertieren (z. B. von Datumsangaben im gregorianischen Kalender zu Datumsangaben im persischen Kalender) oder um zu bestimmen, ob ein bestimmtes Jahr ein Schaltjahr ist.<br /><br /> Aufgrund der Änderung hat sich der <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName>-Eigenschaftswert von 21. März, 0622 in 22. März, 0622 für Systeme geändert, auf denen [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] installiert ist.<br /><br /> Weitere Informationen finden Sie im Abschnitt <xref:System.Globalization.PersianCalendar>.|Nebenversion|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|Für die Standardanwendungsdomäne wird der Wert der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>-Eigenschaft von <xref:System.Runtime.Versioning.TargetFrameworkAttribute> abgeleitet (sofern vorhanden), außer es ist explizit durch Zuweisen eines Namens zur <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>-Eigenschaft definiert.  In früheren Versionen von .NET Framework ist der Wert des <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>-Attributs `null`, sofern nicht eine Reihe spezieller Codepfade ausgeführt oder eine nicht standardmäßige Anwendungsdomäne erstellt wird, ohne ihr Zielframework explizit in der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>-Eigenschaft anzugeben.<br /><br /> Für nicht standardmäßige Anwendungsdomänen ergibt sich keine Änderung hinsichtlich der Art und Weise, wie der Wert der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>-Eigenschaft bestimmt wird. Wenn der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>-Eigenschaft kein Wert explizit zugewiesen ist, erbt die nicht standardmäßige Anwendungsdomäne den Namen des Zielframeworks von der Standardanwendungsdomäne.|Für die Standardanwendungsdomäne gibt <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> möglicherweise einen Nicht-NULL-Wert zurück, als es zuvor `null` zurückgegeben hat. Dies ist das erwünschte Verhalten.|Kante|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|Wenn auf dem System installierte Zertifikate von .NET Framework nicht unterstützt werden, gibt die Übergabe des Werts `True` für das `verbose`-Argument eine gültige Zeichenfolge zurück. In früheren Versionen von .NET Framework löst der Versuch, auf Informationen des öffentlichen Schlüssels für nicht unterstützte Zertifikate zuzugreifen in einigen Fällen eine Ausnahme aus.|Diese Methode dient nur zu Informationszwecken; die Dokumentation vermerkt, dass Ausgaben verschiedener .NET Framework-Versionen möglicherweise nicht konsistent sind. Diese Änderung betrifft nur Apps, die die `ToString(True)`-Methode aufrufen und Zertifikate installiert haben, die von .NET Framework nicht unterstützt werden. Durch das Zurückgeben einer Zeichenfolge, anstatt eine Ausnahme auszulösen, wird die Methode durch diese Änderung robuster.|Kante|  
|Ereignisablaufverfolgung für Windows (ETW)|In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und 4.6.1 löst die Runtime eine <xref:System.ArgumentException> aus, wenn zwei Ereignisnamen lediglich hinsichtlich des Suffixes „Start“ oder „Stop“ abweichen (ein Ereignis namens `LogUser` und ein anderes Ereignis namens `LogUserStart`). In diesem Fall kann die Runtime die Ereignisquelle nicht erstellen, die dann keine Protokollierung durchführen kann.|Stellen Sie sicher, dass sich zwei Ereignisnamen nicht nur durch das Suffix „Start“ oder „Stop“ unterscheiden.<br /><br /> Diese Anforderung wird ab [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] entfernt. Die Runtime kann Ereignisnamen unterscheiden, die lediglich durch das Suffix „Start“ abweichen.|Kante|  
|"Reflection" und verteiltes COM (DCOM)|Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden. Folgende Typen sind betroffen: <xref:System.Reflection.Assembly>; <xref:System.Reflection.MemberInfo> und seine abgeleiteten Typen, einschließlich <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Type> und <xref:System.Reflection.TypeInfo>, <xref:System.Reflection.MethodBody>, <xref:System.Reflection.Module> und <xref:System.Reflection.ParameterInfo>.|Aufrufe von [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx) für das Objekt geben `E_NOINTERFACE` zurück.|Nebenversion|  
  
<a name="Data"></a>   
## <a name="data"></a>Daten  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Eine TCP/IP-Verbindung mit einer SQL Server-Datenbank, die zu `localhost` aufgelöst wird.|Ab [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] tritt beim Verbindungsversuch der Fehler „Beim Einrichten einer Verbindung mit SQL Server ist ein netzwerk- oder instanzenabhängiger Fehler aufgetreten. Der Server wurde nicht gefunden oder es konnte nicht auf ihn zugegriffen werden. Stellen Sie sicher, dass der Instanzname richtig und SQL Server so konfiguriert ist, das Remoteverbindungen zulässig sind. (Anbieter: SQL-Netzwerkschnittstellen, Fehler: 26 – Fehler beim Suchen des angegebenen Servers/der angegebenen Instanz.)“|Dieses Problem wurde behandelt und das vorherige Verhalten in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wiederhergestellt. Führen Sie ein Upgrade auf [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] durch, um eine Verbindung mit einer SQL Server-Datenbank herzustellen, die zu `localhost` aufgelöst wird.|Nebenversion|  
  
<a name="Networking"></a>   
## <a name="networking"></a>Netzwerk  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Datums- und Uhrzeitwerte in der <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>-Klasse.|Zur Einhaltung von [RFC822](http://www.ietf.org/rfc/rfc0822.txt) und [RFC2822](http://www.ietf.org/rfc/rfc2822.txt) verfügt ein formatierter Datums- und Uhrzeitwert jetzt über eine zweistellige Stundenangabe. Zuvor enthielt er für Zeiten vor 10 Uhr einen einstelligen Stundenwert.|Diese Änderung wirkt sich auf folgende Verwendungsszenarios aus:<br /><br /> – Vergleichen der Länge oder der Hashcodes von serialisierten <xref:System.Net.Mime.ContentDisposition>-Objekten über .NET Framework-Versionen hinweg.<br />– Vergleichen des Rückgabewerts der <xref:System.Net.Mime.ContentDisposition.ToString%2A>-Methode oder der Zeichenfolgendarstellung von <xref:System.Net.Mime.ContentDisposition>-Eigenschaftswerten für Datum und Uhrzeit zwischen .NET Framework-Versionen.|Nebenversion|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|WCF-Dienste, die NETTCP mit SSL-Sicherheit und zertifikatsbasierte Authentifizierung verwenden|.NET Framework 4.6 fügt TLS 1.1 und TLS 1.2 zur WCF-SSL-Standardprotokolliste hinzu. Wenn sowohl auf dem Client- als auch auf dem Servercomputer .NET Framework 4.6 oder höher installiert ist, wird TLS 1.2 für die Aushandlung verwendet.|TLS 1.2 unterstützt die MD5-Zertifikatauthentifizierung nicht. Wenn ein Kunde daher ein MD5-Zertifikat verwendet, kann der WCF-Client keine Verbindung mit dem WCF-Dienst herstellen. Weitere Informationen finden Sie unter [Entschärfung: WCF-Dienste und Zertifikatauthentifizierung](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).|Nebenversion|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Fensterrendering in einem Szenario mit mehreren Monitoren|Das gesamte Fenster wird ohne Clipping gerendert, wenn es außerhalb einer Anzeige in einem Szenario mit mehreren Monitoren erweitert wird.|Siehe [Entschärfung: Rendern von WPF-Fenstern](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md).|Nebenversion|  
|Die Rechtschreibprüfung für textfähige WPF-Steuerelemente|Bei der Ausführung von Windows 10 funktioniert die Rechtschreibprüfung möglicherweise nicht, da die Plattform-Rechtschreibungsfunktionen nur für Sprachen zur Verfügung stehen, die in der Eingabesprachenliste vorhanden sind.|Wenn der Liste der verfügbaren Tastaturen in Windows 10 eine Sprache hinzugefügt wird, lädt Windows automatisch ein entsprechendes FOD-Paket (Feature-On-Demand) herunter, das die entsprechenden Rechtschreibprüfungsfunktionen bereitstellt, und installiert es. Durch das Hinzufügen der Sprache zur Eingabesprachenliste wird die Rechtschreibprüfung unterstützt.|Gering|  
  
<a name="Setup"></a>   
## <a name="setup-and-deployment"></a>Setup und Bereitstellung  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Produktversionsverwaltung|Die Produktversionsverwaltung wurde gegenüber früheren Releases von .NET Framework geändert, insbesondere gegenüber .NET Framework 4, 4.5, 4.5.1 und 4.5.2. Weitere Informationen finden Sie unter [Entschärfung: Produktversionsverwaltung](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Siehe [Entschärfung: Produktversionsverwaltung](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Mittel|  
  
<a name="ClickOnce"></a>   
## <a name="clickonce"></a>ClickOnce  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Mit ClickOnce veröffentlichte Apps, die ein SHA-256-Codesignaturzertifikat verwenden.|ClickOnce-Apps, die auf [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] oder frühere Versionen abzielen und mit einem SHA-256-Zertifikat signiert sind, besitzen keine Laufzeitabhängigkeit mehr von [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder einer höheren Version.|Zuvor erforderte die Signierung einer ClickOnce-App, die auf [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] oder frühere Versionen mit einem SHA-256-Zertifikat ausgerichtet war, dass [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder eine höhere Version auf dem Zielsystem vorhanden war. Dies führte zu Fehlern in Fällen, in denen sie nicht vorhanden war. Diese Änderung beseitigt diese Abhängigkeit und gestattet die Verwendung von SHA-256-Zertifikaten zum Signieren von ClickOnce-Apps, die auf [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] und frühere Versionen abzielen.|Gering|  
  
<a name="RyuJIT"></a>   
## <a name="the-new-64-bit-jit-compiler"></a>Der neue 64-Bit-JIT-Compiler  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|64-Bit-JIT-Kompilierung|Ab .NET Framework 4.6 wird ein neuer 64-Bit-JIT-Compiler für die Just-in-Time-Kompilierung verwendet. Diese Änderung wirkt sich nicht auf den 32-Bit-JIT-Compiler aus.|In einigen Fällen wird eine unerwartete Ausnahme ausgelöst oder ein anderes Verhalten beobachtet als bei der Ausführung eines 32-Bit-Compilers oder des älteren 64-Bit-JIT-Compilers. **Hinweis:** Alle genannten Probleme wurden im neuen 64-Bit-Compiler behoben, der mit .NET Framework 4.6.2 veröffentlicht wurde. Die meisten wurden auch in Service Releases von .NET Framework 4.6 und 4.6.1 behoben, die in Windows Update enthalten sind. <br /><br /> Weitere Informationen finden Sie unter [Entschärfung: Neuer 64-Bit-JIT-Compiler](../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md).|Kante|  
|Ausnahmebehandlung (Zurückgeben aus einem `try`-Bereich)|Im Gegensatz zum älteren JIT64 (Just-In-Time)-Compiler lässt der neue 64-Bit-JIT-Compiler keine IL-`ret`-Anweisung in einer `try`-Region zu.|Zurückgeben aus einem `try`-Bereich ist durch die ECMA-335-Spezifikation nicht zulässig, und kein bekannter verwalteter Compiler generiert eine solche IL. Allerdings führt der JIT64-Compiler solche IL aus, wenn sie mithilfe von Reflektionsausgabe generiert wurde.<br /><br /> Wenn die Anwendung IL generiert, die einen `ret`-Opcode in einer `try`-Region enthält, können Sie Folgendes durchführen:<br /><br /> – Ausrichtung auf .NET Framework 4.5 oder das [\<useLegacyJIT>](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)-Element zur Konfigurationsdatei der Anwendung hinzufügen, um den alten JIT-Compiler zu verwenden und die Änderung zu vermeiden.<br />– Aktualisierung der generierten IL, die nach der `try`-Region zurückgegeben wird.<br />-|Kante|
