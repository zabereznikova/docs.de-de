---
title: "Änderungen der Neuzuweisungen in .NET Framework 4.6.2 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 76dc6849-8210-4e41-8731-20828c98b282
caps.latest.revision: 26
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 229ccf3fa4ff1029334641da350cfd040e4b286e
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-462"></a>Änderungen der Neuzuweisungen in .NET Framework 4.6.2
In seltenen Fällen wirken sich Neuausrichtungsänderungen auf Apps aus, die für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] neu kompiliert wurden. Sie wirken sich nicht auf Binärdateien aus, die auf eine frühere Version von .NET Framework abzielen, jedoch in Version 4.6.2 ausgeführt werden. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] umfasst Neuausrichtungsänderungen in den folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
 Die Spalte "Umfang" in den folgenden Tabellen gibt den Schweregrad der einzelnen Änderungen an:  
  
-   Schwerwiegend. Eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht. Beachten Sie, dass keine der Neuausrichtungsänderungen in diese Kategorie fallen.  
  
-   Gering. Eine Änderung, die entweder eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
-   Grenzfall. Eine Änderung, die nur Apps in sehr spezifischen Szenarien beeinflusst, die nicht üblich sind.  
  
-   Transparent. Eine Änderung, die keine nennenswerten Auswirkungen hat, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.  
  
<a name="Core"></a>   
## <a name="core"></a>Kernspeicher  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Unterstützung für lange Pfade|In Apps ab der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] werden lange Pfade (mit bis zu 32.000 Zeichen) unterstützt, und die 260-Zeichen- (oder `MAX_PATH`)-Einschränkung für die Pfadlänge ist entfallen.|Für Apps mit der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] lösen Codepfade, die zuvor eine <xref:System.IO.PathTooLongException>-Ausnahme auslösten, möglicherweise keine Ausnahme mehr aus. Weitere Informationen finden Sie unter [Entschärfung: Unterstützung für lange Pfade](~/docs/framework/migration-guide/mitigation-long-path-support.md).|Gering|  
|Pfadnormalisierung|Ab Apps mit der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wurde die Art der Normalisierung von Pfaden geändert, um dem Betriebssystem zu folgen und besseren Zugriff auf Pfade auf DOS-Geräten zu bieten.|Die Änderungen ermöglichen den Zugriff auf gültige Gerätepfade, die bisher nicht unterstützt wurden. Weitere Informationen finden Sie unter [Entschärfung: Pfadnormalisierung](~/docs/framework/migration-guide/mitigation-path-normalization.md).|Gering|  
|<xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>|Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade (sowohl hinsichtlich Länge als auch Format) zu unterstützen. Insbesondere wurden Prüfungen auf ordnungsgemäße Syntax von Laufwerkstrennzeichen (den Doppelpunkt) strenger definiert.|Durch diese Änderungen werden einige URI-Pfade blockiert, die von den beiden Methoden bisher unterstützt wurden. Weitere Informationen finden Sie unter [Entschärfung: Überprüfung des Doppelpunkts in Pfaden](~/docs/framework/migration-guide/mitigation-path-colon-checks.md).|Edge|  
|<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName>-Konstruktor|Von [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an stellt die durch einen Aufruf der Methode <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> erzeugte <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>-Eigenschaft eine neue <xref:System.Security.Claims.ClaimsIdentity>-Instanz dar. In früheren Versionen von .NET Framework handelt es sich bei <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> um einen vorhandenen Verweis.|In manchen Fällen gibt der Vergleich der <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>-Eigenschaft mit der <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>-Eigenschaft der <xref:System.Security.Principal.IIdentity> des Konstruktors abweichende Ergebnisse zurück.<br /><br /> Weitere Informationen finden Sie unter [Entschärfung: ClaimsIdentity-Konstruktor](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md).|Kante|  
|<xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor%2A?displayProperty=fullName>|Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an stellt der <xref:System.Security.Cryptography.AesCryptoServiceProvider>-Decryptor eine wiederverwendbare Transformation bereit.   Nach einem Aufruf von <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A> wird die Transformation erneut initialisiert und kann wiederverwendet werden.<br /><br /> Für Apps mit früheren Versionen von .NET Framework als Zielplattform wird bei Versuchen, den Decryptor durch Aufrufen von <xref:System.Security.Cryptography.ICryptoTransform.TransformBlock%2A> nach einem Aufruf von <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A> erneut zu verwenden, eine <xref:System.Security.Cryptography.CryptographicException>-Ausnahme ausgelöst, oder es werden beschädigte Daten erzeugt.|Die Auswirkungen sollten minimal sein, da dies das erwartete Verhalten darstellt.<br /><br /> Anwendungen, die vom bisherigen Verhalten abhängen, können sich gegen die Verwendung entscheiden, indem sie dem Abschnitt [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der Konfigurationsdatei der Anwendung die folgende Konfigurationseinstellung hinzufügen:<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/> </runtime>`<br /><br /> Für Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder einer höheren Version ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt der Konfigurationsdatei der Anwendung die folgende Konfigurationseinstellung hinzugefügt wird:<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/> </runtime>`|Gering|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|Unterstützung der WCF-Transportsicherheit für Zertifikate, die mithilfe der CNG gespeichert wurden|Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an unterstützt WCF-Transportsicherheit Zertifikate, die mithilfe der Windows-Kryptographiebibliothek (CNG) gespeichert wurden. Diese Unterstützung ist auf die Verwendung von Zertifikaten mit einem öffentlichen Schlüssel beschränkt, der über einen Exponent mit einer Länge von nicht mehr als 32 Bit verfügt. Wenn sich eine Anwendung auf den [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] bezieht, so ist diese Funktion standardmäßig aktiviert.<br /><br /> In früheren Versionen von .NET Framework löst der Versuch, X509-Zertifikate mit einem CSG-Schlüsselspeicheranbieter zu verwenden, eine Ausnahme aus.|Apps für die Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früher, die unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ausgeführt werden, können Unterstützung für CNG-Zertifikate aktivieren, indem sie dem runtime-Abschnitt der app.config- oder web.config-Datei die folgende Zeile hinzufügen.<br /><br /> `<AppContextSwitchOverrides     value="Switch.System.ServiceModel.DisableCngCertificates=false" />`<br /><br /> Dies kann mithilfe des folgenden Codes auch programmgesteuert erfolgen:<br /><br /> `private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate"; AppContext.SetSwitch(disableCngCertificates, false);`<br /><br /> `Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates" AppContext.SetSwitch(disableCngCertificates, False)`<br /><br /> Beachten Sie, dass aufgrund dieser Änderung jeglicher Code zur Ausnahmebehandlung, der von dem Versuch zur Einleitung von sicherer Kommunikation mit einem CNG-Zertifikat abhängt, nicht ausgeführt wird.|Gering|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, `System.ComponentModel.EventDescriptor.Equals` und `System.ComponentModel.PropertyDescriptor.Equals`|Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an hat sich die Implementierung der Basisklassenmethode <xref:System.ComponentModel.MemberDescriptor.Equals%2A> geändert.|Da die Prüfung auf Gleichheit jetzt das erwartete Ergebnis erzeugt, sollte die Änderung nur geringe Auswirkungen haben.<br /><br /> Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], die vom bisherigen Verhalten abhängen, können sich jedoch gegen diese Änderung entscheiden. Analog dazu können Apps für frühere Versionen von .NET Framework als Zielplattform, die unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ausgeführt werden, sich für diese Änderung entscheiden. Weitere Informationen finden Sie unter [Entschärfung: MemberDescriptor.Equals](~/docs/framework/migration-guide/mitigation-memberdescriptor-equals.md).|Edge|  
  
## <a name="see-also"></a>Siehe auch  
 [Anwendungskompatibilität in 4.6.2](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
