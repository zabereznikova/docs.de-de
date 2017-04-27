---
title: "Änderungen der Neuzuweisungen in .NET Framework 4.7 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes,.NET Framework
- retargeting changes,.NET Framework 4.7
- application compatibility
ms.assetid: d98bf1e3-0017-4933-8e7b-191ac3542fcc
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2881049ee490bf0abdd8b2f0651ca3703ccae76a
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-47"></a>Änderungen der Neuzuweisungen in .NET Framework 4.7

In seltenen Fällen wirken sich Neuausrichtungsänderungen auf Apps aus, die für das .NET Framework 4.7 neu kompiliert wurden. Sie wirken sich nicht auf Binärdateien aus, die auf eine frühere Version von .NET Framework abzielen, jedoch unter Version 4.7 ausgeführt werden. Das .NET Framework 4.7 umfasst Neuausrichtungsänderungen in den folgenden Bereichen:  

-   [Kernspeicher](#Core)  
-   [ASP.NET](#asp) 
-   [Windows Communication Foundation (WCF)](#WCF)  
-   [Windows Presentation Foundation (WPF)](#WPF)
 
 Die Spalte "Umfang" in den folgenden Tabellen gibt den Schweregrad der einzelnen Änderungen an:  
  
-   Schwerwiegend. Eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht. Beachten Sie, dass keine der Neuausrichtungsänderungen in diese Kategorie fallen.  
  
-   Gering. Eine Änderung, die entweder eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
-   Grenzfall. Eine Änderung, die nur Apps in sehr spezifischen Szenarien beeinflusst, die nicht üblich sind.  
  
-   Transparent. Eine Änderung, die keine nennenswerten Auswirkungen hat, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.  
  
## <a name="a-namecore--core"></a><a name="Core" /> Kern

| Funktion | Änderung | Auswirkungen | Bereich |
|----|----|----|----|
|<xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> | Anwendungen mit .NET Framework 4.6.2 und früheren Versionen als Zielplattform erwarten in dem dieser Eigenschaft zugewiesenen Wert einen <xref:System.IntPtr> zu dem angegebenen Speicherort im Arbeitsspeicher, an dem sich der HWND-Wert befindet.<br/></br>Bei Apps mit .NET Framework 4.7 und höher als Zielplattform kann eine Windows Forms-Anwendung den Wert dieser Eigenschaft mit Code wie dem folgenden festlegen: <br/><br/>` cspParameters.ParentWindowHandle = form.Handle; ` | Apps, für die diese Verhaltensänderung unkomfortabel ist, können sich gegen das neue Verhalten entscheiden. Analog dazu können Apps mit früheren Versionen von .NET Framework als Zielplattform, die in .NET Framework 4.7 ausgeführt werden, sich für das neue Verhalten entscheiden. Weitere Informationen finden Sie unter [Entschärfung: CspParameters.ParentWindowHandle erwartet ein HWND](../../../docs/framework/migration-guide/mitigation-cspparameters-parentwindowhandle-expects-an-hwnd.md). | Gering |
| Serialisierung mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> | Für Apps mit .NET Framework 4.7 und höher als Zielplattform ist die Serialisierung von Steuerzeichen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> jetzt kompatibel mit ECMAScript V6 und V8 | Diese Änderung ist zum ECMAScript-Standard konform und sollte wenig Einfluss haben. Wenn ein Einfluss festgestellt wird, kann das vorherige Verhalten mithilfe eines Kompatibilitätsschalters wiederhergestellt werden. Weitere Informationen finden Sie unter [Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer](../../../docs/framework/migration-guide/mitigation-serialization-control-characters.md)  | Edge |

## <a name="a-nameasp--aspnet"></a><a name="asp" /> ASP.NET

| Funktion  |Änderung  |Auswirkungen | Bereich | 
---------|---------|---------|-----|
Einschränken von gleichzeitigen Anforderungen pro Sitzung | In .NET Framework 4.6.2 und früher führt ASP.NET Anforderungen mit der gleichen <xref:System.Web.SessionState.HttpSessionState.SessionID%2A> sequenziell aus, und ASP.NET gibt die <xref:System.Web.SessionState.HttpSessionState.SessionID%2A> standardmäßig immer in Form eines Cookies aus. Wenn eine Seite viel Zeit zum Laden beansprucht, wird die Serverleistung durch Drucken von <kbd>F5</kbd> im Browser erheblich beeinträchtigt.<br/><br/>Ab .NET Framework 4.7 verfolgt ein Zähler die in die Warteschlange eingestellten Anforderungen nach und beendet die Anforderungen, wenn sie einen angegebenen Grenzwert überschreiten. Der Standardwert ist 50. Wenn der Grenzwert erreicht wird, wird eine Warnung in das Ereignisprotokoll geschrieben, und möglicherweise wird eine HTTP 500-Antwort im IIS-Protokoll aufgezeichnet.|Diese Änderung kann sich positiv auf die Gesamtleistung des Servers auswirken.<br/><br/>Um das alte Verhalten wiederherzustellen, können Sie Ihrer web.config-Datei die folgende Einstellung hinzufügen, um sich gegen das neue Verhalten zu entscheiden.<br/><br/>`<appSettings>`<br/>&nbsp;&nbsp;&nbsp;`<add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>`<br/>`</appSettings>` | Edge |

## <a name="a-namewcf--windows-communication-foundation"></a><a name="WCF" /> Windows Communication Foundation

| Funktion  |Änderung  |Auswirkungen | Bereich | 
---------|---------|---------|-----|
| WCF-Nachrichtensicherheit | Apps, die unter .NET Framework 4.7 oder höher ausgeführt werden, können durch Einstellungen der Anwendungskonfiguration TLS 1.1 und TLS 1.2 in WCF-Nachrichtensicherheit verwenden. Dies ist eine optionale Funktion; standardmäßig ist die Unterstützung für TLS 1.1 und TLS 1.2 in WCF-Nachrichtensicherheit deaktiviert. | Das Standardverhalten der WCF-Nachrichtensicherheit bleibt unverändert. <br/><br/> Um die Unterstützung für TLS 1.1 und TLS 1.2 zu aktivieren, fügen Sie die folgende Konfigurationseinstellung zum Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der `app.config`- oder `web.config`-Datei hinzu:  <br/><br/>`<runtime>` <br/> &nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;`<br/>&nbsp;&nbsp;&nbsp;`Switch.System.Net.DontEnableSchUseStrongCrypto=false" />`<br/>`</runtime>` | Edge |         

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" /> Windows Presentation Foundation (WPF)  

| Funktion | Änderung | Auswirkungen | Bereich |
|---|---|---|---|
| Die Platzzuweisung des <xref:System.Windows.Controls.Grid>-Steuerelements an mit einem Stern markierte Spalten | Bei Apps mit .NET Framework 4.7 und höher als Zielplattform ersetzt WPF den Algorithmus, den das <xref:System.Windows.Controls.Grid>-Steuerelement verwendet, um Platz für \*-columns.md) zuzuweisen | Bei Anwendungen mit Versionen von .NET Framework ab .NET Framework 4.7 wirkt sich diese Änderung in einer Reihe von Fällen auf die tatsächliche Breite aus, die \*-Spalten zugewiesen wird. Wenn diese Änderung nicht wünschenswert ist, kann der vorhergehende Algorithmus weiterhin angewendet werden, indem der Anwendungskonfigurationsdatei ein Eintrag hinzugefügt wird. Weitere Informationen finden Sie unter [Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement](../../../docs/framework/migration-guide/mitigation-grid-control.md). | Gering |
| <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> | In Anwendungen mit .NET Framework 4.6.2 und früheren Versionen als Zielplattform hat ein Fehler im Ausnahmebehandlungscode für die <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A>-Methode die Auslösung einer [NullReferenceException](assetId:///T:System.NullReferenceException] anstelle der beabsichtigten Ausnahme (wie etwa [DirectoryNotFoundException](assetId:///T:System.IO.DirectoryNotFoundException) oder [FileNotFoundException](assetId:///T:System.IO.FileNotFoundException) bewirkt.<br/><br/>Bei Apps mit Zielplattform .NET Framework 4.7 oder höher wird die richtige Ausnahme ausgelöst.  | Für Anwendungen mit der Zielplattform .NET Framework 4.7, die von der Behandlung einer [NullReferenceException](assetId:///T:System.NullReferenceException) abhängen, kann das vorherige Verhalten wiederhergestellt werden, indem der Konfigurationseinstellung im Abschnitt [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der `app.config`-Datei Folgendes hinzugefügt wird: <br/><br/>`<runtime>`<br/>&nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true"/>`<br/>`</runtime>`| Edge | 
| Optionale Unterstützung für einen `WM_POINTER`-basierten Touch/Stift-Stapel | Bei Apps mit Zielplattform .NET Framework 4.7 oder höher wird Unterstützung für optionale `WM_POINTER-basierte Touch-Unterstützung durch WPF hinzugefügt.  | Dies ist eine optionale Funktion, die auf Windows-Systemen ab Windows 10 Creators Update verfügbar ist. Für WPF-Apps, die sich nicht explizit für zeigerbasierte Touch/Stift-Unterstützung entscheiden, hat das keine Auswirkungen. Weitere Informationen finden Sie unter [Entschärfung: Zeigerbasierte Touch- und Stiftunterstützung](../Topic/Mitigation:%20Pointer-based%20Touch%20and%20Stylus%20Support.md). | Kante |
| [PrintQueue](assetId:///T:System.Printing.PrintQueue)-Klasse | Ab .NET Framework 4.7 rufen WPF-Druck-APIs, die [PrintQueue](assetId:///T:System.Printing.PrintQueue) verwenden, standardmäßig die Windows Print Document Package-API anstelle der jetzt veralteten XPS Print-API auf.<br/><br/>Der alte Druckstapel funktioniert in älteren Windows-Versionen weiterhin wie zuvor. | Weder für Benutzer noch für Entwickler sollten Änderungen im Verhalten oder der API-Nutzung sichtbar werden. <br/><br/>Um den alten Stapel in Windows 10 Creators Update zu verwenden, legen Sie den `UseXpsOMPrinting` `REG_DWORD`-Wert des `HKEY_CURRENT_USER\Software\Microsoft.NETFramework\Windows Presentation Foundation\Printing`-Registrierungsschlüssels auf 1 fest. | Edge | 
## <a name="see-also"></a>Siehe auch
[Anwendungskompatibilität in .NET Framework 4.7](Application%20Compatibility%20in%20the%20.NET%20Framework%204.7.md)

