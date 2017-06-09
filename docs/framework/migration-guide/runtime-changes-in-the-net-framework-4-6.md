---
title: "Runtime-&#196;nderungen in .NET Framework 4.6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Runtime-&#196;nderungen in .NET Framework 4.6
In seltenen Fällen können sich Laufzeitänderungen auf vorhandene Apps auswirken, die auf frühere Versionen von .NET Framework abzielen, jedoch in einer älteren .NET Framework\-Laufzeit ausgeführt werden. Sie umfassen auch Unterschiede im Verhalten zwischen Anwendungen, die in verschiedenen .NET Framework\-Laufzeitumgebungen ausgeführt werden. Dazu zählen Änderungen in folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
-   [Netzwerk](#Networking)  
  
-   [Windows Presentation Foundation \(WPF\)](#WPF)  
  
-   [Setup und Bereitstellung](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Der neue 64\-Bit\-JIT\-Compiler](#RyuJIT)  
  
<a name="Core"></a>   
## Kernspeicher  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|Ab [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] verwendet die <xref:System.Globalization.PersianCalendar>\-Klasse den Hijri\-Solaralgorithmus.|Der Hijri\-Solaralgorithmus gibt Ergebnisse zurück, die identisch mit denen des persischen Kalenders sind, der derzeit im Iran und in Afghanistan verwendet wird. Darüber hinaus sind die von diesem Algorithmus zurückgegebenen Ergebnisse für Datumsangaben von 1800 im gregorianischen Kalender bis 2023 im gregorianischen Kalender identisch mit denen des vorherigen Algorithmus. Datumsangaben außerhalb dieses Bereichs können abweichen, wenn die <xref:System.Globalization.PersianCalendar>\-Klasse verwendet wird, um Datumsangaben zu konvertieren \(z. B. von Datumsangaben im gregorianischen Kalender zu Datumsangaben im persischen Kalender\) oder um zu bestimmen, ob ein bestimmtes Jahr ein Schaltjahr ist.<br /><br /> Aufgrund dieser Änderung wurde der <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName>Eigenschaftswert für Systeme, auf denen [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] installiert ist, vom 21. März 0622 zum 22. März 0622 geändert.<br /><br /> Weitere Informationen finden Sie im Thema <xref:System.Globalization.PersianCalendar>.|Gering|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|Für die Standardanwendungsdomäne wird der Wert der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>\-Eigenschaft vom <xref:System.Runtime.Versioning.TargetFrameworkAttribute> abgeleitet, sofern eins vorhanden ist, es sei denn, sie wird explizit definiert, indem der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>\-Eigenschaft ein Name zugewiesen wird.  In früheren Versionen von .NET Framework ist der Wert des <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>\-Attributs `null`, wenn nicht eine Reihe von speziellen Codepfaden ausgeführt wird oder eine nicht standardmäßige App\-Domäne erstellt wird, ohne explizite Angabe ihres Zielframeworks in der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>\-Eigenschaft.<br /><br /> Für nicht standardmäßige Anwendungsdomänen gibt es keine Änderung bei der Art, in der der Wert der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>\-Eigenschaft bestimmt wird. Wenn der <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>\-Eigenschaft kein Wert explizit zugewiesen ist, erbt die nicht standardmäßige Anwendungsdomäne den Namen des Zielframeworks von der Standardanwendungsdomäne.|Für die Standardanwendungsdomäne kann <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> einen Wert ungleich Null zurückgeben, wenn zuvor `null` zurückgegeben wurde. Dies ist das erwünschte Verhalten.|Rand|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|Wenn auf dem System installierte Zertifikate von .NET Framework nicht unterstützt werden, gibt die Übergabe des Werts `True` für das `verbose`\-Argument eine gültige Zeichenfolge zurück. In früheren Versionen von .NET Framework löst der Versuch, auf Informationen des öffentlichen Schlüssels für nicht unterstützte Zertifikate zuzugreifen in einigen Fällen eine Ausnahme aus.|Diese Methode dient nur zu Informationszwecken; die Dokumentation vermerkt, dass Ausgaben verschiedener .NET Framework\-Versionen möglicherweise nicht konsistent sind. Diese Änderung betrifft nur Apps, die die `ToString(True)`\-Methode aufrufen und Zertifikate installiert haben, die von .NET Framework nicht unterstützt werden. Durch das Zurückgeben einer Zeichenfolge, anstatt eine Ausnahme auszulösen, wird die Methode durch diese Änderung robuster.|Rand|  
|"Reflection" und verteiltes COM \(DCOM\)|Reflection\-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM\-Clients übergeben werden. Die folgenden Typen sind betroffen: <xref:System.Reflection.Assembly>; <xref:System.Reflection.MemberInfo> und die abgeleiteten Typen, einschließlich <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Type> und <xref:System.Reflection.TypeInfo>; <xref:System.Reflection.MethodBody>; <xref:System.Reflection.Module> und <xref:System.Reflection.ParameterInfo>.|Aufrufe von [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx) für das Objekt geben `E_NOINTERFACE` zurück.|Gering|  
  
<a name="Networking"></a>   
## Netzwerk  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|Datums\- und Uhrzeitwerte in der <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>\-Klasse.|Zur Einhaltung von [RFC822](http://www.ietf.org/rfc/rfc0822.txt) und [RFC2822](http://www.ietf.org/rfc/rfc2822.txt) verfügt ein formatierter Datums\- und Uhrzeitwert jetzt über eine zweistellige Stundenangabe. Zuvor enthielt er für Zeiten vor 10 Uhr einen einstelligen Stundenwert.|Diese Änderung wirkt sich auf folgende Verwendungsszenarios aus:<br /><br /> -   Vergleichen der Länge oder der Hashcodes von serialisierten <xref:System.Net.Mime.ContentDisposition>\-Objekten über .NET Framework\-Versionen hinweg.<br />-   Vergleichen des Rückgabewerts der <xref:System.Net.Mime.ContentDisposition.ToString%2A>\-Methode oder der Zeichenfolgendarstellung von <xref:System.Net.Mime.ContentDisposition>\-Eigenschaftswerte für Datum und Uhrzeit zwischen .NET Framework\-Versionen.|Gering|  
  
<a name="WPF"></a>   
## Windows Presentation Foundation \(WPF\)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|Fensterrendering in einem Szenario mit mehreren Monitoren|Das gesamte Fenster wird ohne Clipping gerendert, wenn es außerhalb einer Anzeige in einem Szenario mit mehreren Monitoren erweitert wird.|Siehe [Minderung: Rendern von WPF\-Fenstern](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md).|Gering|  
|Die Rechtschreibprüfung für textfähige WPF\-Steuerelemente|Bei der Ausführung von Windows 10 funktioniert die Rechtschreibprüfung möglicherweise nicht, da die Plattform\-Rechtschreibungsfunktionen nur für Sprachen zur Verfügung stehen, die in der Eingabesprachenliste vorhanden sind.|Wenn der Liste der verfügbaren Tastaturen in Windows 10 eine Sprache hinzugefügt wird, lädt Windows automatisch ein entsprechendes FOD\-Paket \(Feature\-On\-Demand\) herunter, das die entsprechenden Rechtschreibprüfungsfunktionen bereitstellt, und installiert es. Durch das Hinzufügen der Sprache zur Eingabesprachenliste wird die Rechtschreibprüfung unterstützt.|Gering|  
  
<a name="Setup"></a>   
## Setup und Bereitstellung  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|Produktversionsverwaltung|Die Produktversionsverwaltung wurde gegenüber früheren Versionen von .NET Framework geändert, insbesondere gegenüber .NET Framework 4, 4.5, 4.5.1 und 4.5.2. Weitere Informationen finden Sie unter [Migration: Produktversionsverwaltung](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Siehe [Migration: Produktversionsverwaltung](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Mittel|  
  
<a name="ClickOnce"></a>   
## ClickOnce  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|Mit ClickOnce veröffentlichte Apps, die ein SHA\-256\-Codesignaturzertifikat verwenden.|ClickOnce\-Apps, die auf [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] oder frühere Versionen abzielen und mit einem SHA\-256\-Zertifikat signiert sind, besitzen keine Laufzeitabhängigkeit mehr von [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder einer höheren Version.|Zuvor erforderte die Signierung einer ClickOnce\-App, die auf [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] oder frühere Versionen mit einem SHA\-256\-Zertifikat ausgerichtet war, dass [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder eine höhere Version auf dem Zielsystem vorhanden war. Dies führte zu Fehlern in Fällen, in denen sie nicht vorhanden war. Diese Änderung beseitigt diese Abhängigkeit und gestattet die Verwendung von SHA\-256\-Zertifikaten zum Signieren von ClickOnce\-Apps, die auf [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] und frühere Versionen abzielen.|Gering|  
  
<a name="RyuJIT"></a>   
## Der neue 64\-Bit\-JIT\-Compiler  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|--------------|--------------|------------------|-------------|  
|Ausnahmebehandlung \(Zurückgeben aus einem `try`\-Bereich\)|Im Gegensatz zum älteren JIT64 \(Just\-In\-Time\)\-Compiler lässt der neue 64\-Bit\-JIT\-Compiler keine IL [ret](http://msdn.microsoft.com/library/system.reflection.emit.opcodes.ret.aspx)\-Anweisung in einer `try`\-Region zu.|Zurückgeben aus einem `try`\-Bereich ist durch die ECMA\-335\-Spezifikation nicht zulässig, und kein bekannter verwalteter Compiler generiert eine solche IL. Allerdings führt der JIT64\-Compiler solche IL aus, wenn sie mithilfe von Reflektionsausgabe generiert wurde.|Rand|