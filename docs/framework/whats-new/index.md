---
title: Neues in .NET Framework | Microsoft-Dokumentation
ms.custom: 
ms.date: 05/02/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
caps.latest.revision: 292
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: ddcefb2b35f8cbf06a3abcc16158eee850f799ff
ms.openlocfilehash: 3b6835c2e2c8ae590c642d5534cd1bae5645db6f
ms.contentlocale: de-de
ms.lasthandoff: 05/03/2017

---
# <a name="whats-new-in-the-net-framework"></a>Neues in .NET Framework
<a name="introduction"></a> Dieser Artikel beschreibt wichtige Funktionen und Änderungen in den folgenden Versionen von .NET Framework:

 [.NET Framework 4.7](#v47) 
 [.NET Framework 4.6.2](#v462) 
 [.NET Framework 4.6.1](#v461) 
 [.NET 2015 und .NET Framework 4.6](#v46) 
 [.NET Framework 4.5.2](#v452) 
 [.NET Framework 4.5.1](#v451) 
 [.NET Framework 4.5](#core)

 Dieser Artikel enthält keine umfassenden Informationen zu jeder neuen Funktion und unterliegt möglichen Änderungen. Allgemeine Informationen zu .NET Framework finden Sie unter [Erste Schritte](../../../docs/framework/get-started/index.md). Informationen zu unterstützten Plattformen finden Sie unter [Systemanforderungen](~/docs/framework/get-started/system-requirements.md). Downloadlinks und Installationsanweisungen finden Sie im [Installationshandbuch](../../../docs/framework/install/guide-for-developers.md).

> [!NOTE]
>  Das .NET Framework-Team veröffentlicht zusätzlich mit NuGet Funktionen außer der Reihe, um die Plattformunterstützung zu erweitern und neue Funktionen einzuführen, z. B. unveränderliche Auflistungen und SIMD-fähige Vektortypen. Weitere Informationen finden Sie unter [Zusätzliche Klassenbibliotheken und APIs](../additional-apis/index.md) und [.NET Framework und Out-of-Band-Releases](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). Lassen Sie eine [vollständige Liste von NuGet-Paketen](https://blogs.msdn.microsoft.com/dotnet/p/nugetpackages/) für .NET Framework anzeigen, oder abonnieren Sie [unseren Feed](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).

<a name="v47"></a> 
## <a name="introducing-the-net-framework-47"></a>Einführung in .NET Framework 4.7
 .NET Framework 4.7 baut auf .NET Framework 4.6, 4.6.1 und 4.6.2 auf und umfasst zahlreiche Fehlerkorrekturen und neue Funktionen in einem gewohnt stabilen Produkt.

### <a name="downloading-and-installing-the-net-framework-47"></a>Herunterladen und Installieren von .NET Framework 4.7
 
Sie können .NET Framework 4.7 von den folgenden Speicherorten herunterladen:

- [.NET Framework 4.7 Webinstaller](http://go.microsoft.com/fwlink/?LinkId=825299)

- [.NET Framework 4.7 Offlineinstaller](http://go.microsoft.com/fwlink/?LinkId=825303)

.NET Framework 4.7 kann unter Windows 10, Windows 8.1, Windows 7 und den entsprechenden Serverplattformen, beginnend mit Windows Server 2008 R2 SP1, installiert werden. Sie können .NET Framework 4.7 wahlweise mit dem Webinstaller oder Offlineinstaller installieren. Die empfohlene Vorgehensweise für die meisten Benutzer ist die Verwendung des Webinstallers.

Sie können .NET Framework 4.7 in Visual Studio 2012 oder höheren Versionen als Ziel verwenden, indem Sie das [.NET Framework 4.7-Entwicklerpaket](http://go.microsoft.com/fwlink/?LinkId=825319) installieren.

### <a name="whats-new-in-the-net-framework-47"></a>Neuerungen in .NET Framework 4.7

.NET Framework 4.7 umfasst neue Features in den folgenden Bereichen:

- [Kernspeicher](#Core47)
- [Netzwerk](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

Eine Liste der neuen APIs, die .NET Framework 4.7 hinzugefügt wurden, finden Sie unter [API-Änderungen für .NET Framework 4.7](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) auf GitHub. Eine Liste der Verbesserungen von Funktionen und Fehlerkorrekturen in .NET Framework 4.7 finden Sie unter [Liste mit Änderungen für .NET Framework 4.7](http://gutithub.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) auf GitHub.  Weitere Informationen finden Sie unter [Announcing the .NET Framework 4.7 (Ankündigung von .NET Framework 4.7)](https://blogs.msdn.microsoft.com/dotnet/2017/04/05/announcing-the-net-framework-4-7/) im .NET-Blog.

<a name="Core47" />
#### <a name="core"></a>Kernspeicher

.NET Framework 4.7 verbessert die Serialisierung durch <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Verbesserte Funktionalität mit Elliptic Curve Cryptography (ECC)***

In .NET Framework 4.7 wurden den Klassen <xref:System.Security.Cryptography.ECDsa> und <xref:System.Security.Cryptography.ECDiffieHellman> `ImportParameters(ECParameters)`-Methoden hinzugefügt, um einem Objekt zu ermöglichen, einen bereits eingerichteten Schlüssel darzustellen. Eine `ExportParameters(Boolean)`-Methode wurde auch zum Exportieren des Schlüssels unter Verwendung expliziter Kurvenparameter hinzugefügt.

.NET Framework 4.7 unterstützt nun auch zusätzliche Kurven (einschließlich der Brainpool-Kurvengruppe) und bietet vordefinierte Definitionen zur Erleichterung der Erstellung mithilfe der Factorymethoden <xref:System.Security.Cryptography.ECDsa.Create%2A> und <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

Auf GitHub finden Sie ein [Beispiel der kryptografischen Verbesserungen in .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e).

**Bessere Unterstützung für Steuerzeichen durch DataContractJsonSerializer**

In .NET Framework 4.7 erfolgt die Serialisierung von Steuerzeichen durch <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> entsprechend dem Standard ECMAScript 6. Dieses Verhalten wird standardmäßig für Anwendungen aktiviert, die auf .NET Framework 4.7 ausgerichtet sind, und ist ein optionales Feature für Anwendungen, die unter .NET Framework 4.7 ausgeführt werden, jedoch auf eine frühere Version von .NET Framework ausgerichtet sind. Weitere Informationen finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />
#### <a name="networking"></a>Netzwerk

.NET Framework-4.7 bietet nun die folgenden netzwerkbezogenen Features:

**Standardmäßig Betriebssystemunterstützung für TLS-Protokolle***

Der TLS-Stapel, der von <xref:System.Net.Security.SslStream?displayProperty=fullName> und vorgelagerten Komponenten im Stapel wie z.B. HTTP, FTP und SMTP verwendet wird, ermöglicht Entwicklern, die vom Betriebssystem unterstützten TLS-Standardprotokolle zu verwenden. Entwickler müssen eine TLS-Version nicht länger vordefinieren.

<a name="ASP-NET47" />
#### <a name="aspnet"></a>ASP.NET

In .NET Framework 4.7 bietet ASP.NET die folgenden neuen Features:

**Erweiterbarkeit des Objektcaches**

Ab .NET Framework 4.7 bietet ASP.NET eine neue Gruppe von APIs, die es Entwicklern ermöglichen, die ASP.NET- Standardimplementierungen für das Zwischenspeichern von Objekten im Arbeitsspeicher und dessen Überwachung zu ersetzen. Entwickler können jetzt die drei folgenden Komponenten ersetzen, wenn die ASP.NET-Implementierung nicht geeignet ist:

- **Objektcachespeicher**. Mithilfe des neuen Abschnitts für die Konfiguration von Cacheanbietern können Entwickler neue Implementierungen eines Objektcaches für eine ASP.NET-Anwendung einbinden, indem die neue **ICacheStoreProvider**-Schnittstelle verwendet wird.
 
- **Speicherüberwachung**. Der Standardspeichermonitor in ASP.NET benachrichtigt Anwendungen, sobald sie sich dem für den Prozess konfigurierten Grenzwert für private Bytes nähern oder der insgesamt verfügbare physische Arbeitsspeicher knapp wird. Bei Annäherung an diese Grenzwerte werden Benachrichtigungen ausgelöst. Bei einigen Anwendungen werden Benachrichtigungen erst ausgelöst, sobald die konfigurierten Grenzwerte schon fast erreicht sind, sodass keine sinnvolle Reaktion möglich ist. Entwickler können jetzt mithilfe der <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=fullName>-Eigenschaft eigene Speichermonitore schreiben.

- **Reaktionen bei Erreichen des Speichergrenzwerts**. Standardmäßig versucht ASP.NET, den Objektcache zu trimmen und regelmäßig <xref:System.GC.Collect%2A?displayProperty=fullName> aufzurufen, wenn der Prozessgrenzwert für private Bereiche fast erreicht ist. Für einige Anwendungen ist die Häufigkeit der Aufrufe von <xref:System.GC.Collect%2A?displayProperty=fullName> oder die Menge des Caches, der getrimmt wird, ineffizient. Entwickler können jetzt das Standardverhalten ersetzen oder ergänzen, indem für den Speichermonitor der Anwendung **IObserver**-Implementierungen abonniert werden.

<a name="wcf47" />
#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

Windows Communication Foundation (WFC) bietet nun die folgenden Features und Änderungen:

**Möglichkeit zum Konfigurieren der Standardsicherheitseinstellungen für Nachrichten für TLS1.1.1 und TLS1.1.2**

Ab .NET Framework 4.7 ermöglicht WCF das Konfigurieren von TSL 1.1 oder TLS 1.2 zusätzlich zu SSL 3.0 und TLS 1.0 als Standardprotokoll für die Sicherheit von Nachrichten. Diese Einstellung ist optional. Um sie zu aktivieren, müssen Sie der Anwendungskonfigurationsdatei den folgenden Eintrag hinzufügen:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" /> 
</runtime>
```

**Verbesserte Zuverlässigkeit von WCF-Anwendungen und WCF-Serialisierung**

WCF umfasst eine Reihe von Codeänderungen zum Vermeiden von Racebedingungen, wodurch Leistung und Zuverlässigkeit von Serialisierungsoptionen verbessert werden. Dazu gehören:

- Bessere Unterstützung für das Kombinieren von asynchronem und synchronem Code in Aufrufen von **SocketConnection.BeginRead** und **SocketConnection.Read**.
- Verbesserte Zuverlässigkeit beim Abbrechen einer Verbindung mit **SharedConnectionListener** und **DuplexChannelBinder**.
- Verbesserte Zuverlässigkeit von Serialisierungsvorgängen beim Aufrufen der Methode <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=fullName>.
- Verbesserte Zuverlässigkeit beim Entfernen eines Waiters durch Aufrufen der **ChannelSynchronizer.RemoveWaiter**-Methode.

<a name="wf47" />
#### <a name="windows-forms"></a>Windows Forms

In .NET Framework 4.7 bietet Windows Forms eine bessere Unterstützung für Monitore mit hohem DPI-Wert.

**Unterstützung hoher DPI-Werte**

Beginnend mit auf .NET Framework 4.7 ausgerichteten Anwendungen unterstützt .NET Framework für Windows Forms-Anwendungen hohe und dynamische DPI-Werte. Durch die Unterstützung hoher DPI-Werte werden das Layout und die Darstellung von Formularen und Steuerelementen auf Monitoren mit hohen DPI-Einstellungen verbessert. Dynamische DPI-Werte ermöglichen das Ändern von Layout und Darstellung von Formularen und Steuerelementen, wenn der Benutzer die DPI-Einstellung oder den Skalierungsfaktor der Anzeige einer ausgeführten Anwendung ändert.

Die Unterstützung hoher DPI-Werte ist ein optionales Feature, das Sie durch Festlegen des Abschnitts [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) in der Anwendungskonfigurationsdatei konfigurieren können. Weitere Informationen zum Hinzufügen der Unterstützung hoher und dynamischer DPI-Werte zu Ihrer Windows Forms-Anwendung finden Sie unter [Unterstützung hoher DPI-Werte in Windows Forms](../winforms/high-dpi-support-in-windows-forms.md).

<a name="WPF47"></a> 
#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

In .NET Framework 4.7 gibt es für WPF die folgenden Verbesserungen:

**Unterstützung für Touch-/Tablettstiftstapel basierend auf Windows-WM_POINTER-Nachrichten**

Sie haben nun die Möglichkeit, einen auf [-Windows-Nachrichten](https://msdn.microsoft.com/library/windows/desktop/hh454903.aspx) basierenden Touch-/Tablettstiftstapel anstelle der Windows Ink Services Plattform (WISP) zu verwenden. Dies ist ein optionales Feature in .NET Framework. Weitere Informationen finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

**Neue Implementierung für Druck-APIs von WPF**

Die Druck-APIs von WPF in der <xref:System.Printing.PrintQueue?displayProperty=fullName>-Klasse rufen die [Print Document Package API](https://msdn.microsoft.com/library/windows/desktop/hh448418(v=vs.85).aspx) von Windows anstelle der veralteten [XPS-Druck-API](https://msdn.microsoft.com/library/windows/desktop/ff686814(v=vs.85).aspx) auf. Die Auswirkung dieser Änderung auf die Anwendungskompatibilität finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md). 

<a name="v462"></a> 
## <a name="whats-new-in-the-net-framework-462"></a>Neuigkeiten in .NET Framework 4.6.2
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] enthält neue Features in den folgenden Bereichen:

- [ASP.NET](#ASPNET462)

- [Zeichenkategorien](#Strings)

- [Kryptografie](#Crypto462)

- [SQLClient](#SQLClient)

- [Windows Communication Foundation](#WCF)

- [Windows Presentation Foundation (WPF)](#WPF462)

- [Windows Workflow Foundation (WF)](#WF462)

- [ClickOnce](#ClickOnce)

- [Konvertieren von Windows Forms und WPF-Apps in UWP-Apps](#UWPConvert)

- [Verbesserungen beim Debugging](#Debug462)

Eine Liste der neuen APIs, die .NET Framework 4.6.2 hinzugefügt wurden, finden unter [API-Änderungen für .NET Framework 4.6.2 auf GitHub](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md). Eine Liste der Verbesserungen von Funktionen und Fehlerkorrekturen in .NET Framework 4.6.2 finden Sie unter [Liste mit Änderungen für .NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=708778) auf GitHub.  Weitere Informationen finden Sie unter der [Ankündigung von .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) im .NET-Blog.

<a name="ASPNET462"></a> 
### <a name="aspnet"></a>ASP.NET
 In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] umfasst ASP.NET die folgenden Verbesserungen:

 **Verbesserte Unterstützung lokalisierter Fehlermeldungen in Validierungssteuerelementen für Datenanmerkungen**
 Mit Validierungssteuerelementen für Datenanmerkungen können Sie eine Überprüfung durchführen, indem Sie mindestens ein Attribut einer Klasseneigenschaft hinzufügen. Das <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName>-Element des Attributs definiert den Text der Fehlermeldung, falls die Validierung fehlschlägt. Beginnend mit [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ist es einfach, mit ASP.NET Fehlermeldungen zu lokalisieren. Fehlermeldungen werden lokalisiert, wenn:

1.  Das <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> wird im Validierungsattribut bereitgestellt.

2.  die Ressourcendatei im Ordner „App_LocalResources“ gespeichert ist.

3.  Der Name der lokalisierten Ressourcendatei ist folgendermaßen aufgebaut: `DataAnnotation.Localization.{`*Name*`}.resx`, wobei *Name *einen Kulturnamen im Format* Sprachcode*`-`*Länder-/Regionscode* oder *Sprachcode* darstellt.

4.  Der Schlüsselname der Ressource ist die Zeichenfolge, die zum <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName>-Attribut zugeordnet ist und sein Wert ist die lokalisierte Fehlermeldung.

 Das folgende Datenanmerkungsattribut definiert z. B. die Fehlermeldung der Standardkultur für eine ungültige Bewertung.

```csharp
public class RatingInfo
{
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]
   [Display(Name = "Your Rating")]
   public int Rating { get; set; }
}
```

```vb
Public Class RatingInfo
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>
   <Display(Name = "Your Rating")>
   Public Property Rating As Integer = 1
End Class
```

 Sie können dann eine Ressourcendatei erstellen, DataAnnotation.Localization.fr.resx, deren Schlüssel die Zeichenfolge der Fehlermeldung und ihr Wert die lokalisierte Fehlermeldung ist. Die Datei muss sich im Ordner `App.LocalResources` befinden. Das folgende Beispiel enthält den Schlüssel und seinen Wert in einer lokalisierten Fehlermeldung (Französisch, fr):

|Name|Wert|
|----------|-----------|
|Die Bewertung muss zwischen 1 und 10 liegen.|La note doit être comprise entre 1 et 10.|

 Diese Datei kann dann

 Darüber hinaus ist die Lokalisierung der Datenanmerkung erweiterbar. Entwickler können ihren eigenen Anbieter für die zu lokalisierenden Zeichenfolgen in einer Ressourcendatei verwenden, indem Sie die <xref:System.Web.Globalization.IStringLocalizerProvider>-Schnittstelle implementieren, um Lokalisierungszeichenfolgen an einem anderen Speicherort zu speichern, jedoch nicht in einer Ressourcendatei.

 **Async-Unterstützung für Sitzungszustands-Schlüsselspeicheranbieter**
 ASP.NET erlaubt nun, dass Methoden, die eine Aufgabe zurückgeben, zusammen mit dem Anbieter für die Speicherung von Daten aus der Variable „Sitzungszustand“ verwendet werden können. Dadurch stehen ASP .NET-Apps die Vorteile zur Verfügung, die async in Sachen Skalierbarkeit bietet. Für die Unterstützung asynchroner Operationen bei Anbietern für die Speicherung von Daten aus der Variable „Sitzungszustand“, enthält ASP.NET eine neue Schnittstelle namens <xref:System.Web.SessionState.ISessionStateModule?displayProperty=fullName>. Diese Schnittstelle erbt von <xref:System.Web.IHttpModule> und erlaubt Entwicklern, ihr eigenes Sitzungszustandsmodul und Anbieter für die Speicherung von async-Sitzungen zu implementieren. Die Schnittstelle wird wie folgt definiert:

```csharp

public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}

```

 Darüber hinaus umfasst die <xref:System.Web.SessionState.SessionStateUtility>-Klasse zwei neue Methoden, <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> und <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, mit denen asynchrone Vorgänge unterstützt werden können.

 **Async-Unterstützung für Ausgabecacheanbieter**
 Ab [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] können Methoden, die Aufgaben zurückgeben, mit Ausgabecacheanbietern verwendet werden, um die Vorteile der Skalierbarkeit von Async bereitzustellen.  Anbieter, die diese Methoden bereitstellen, verringern die Anzahl blockierter Threads auf einem Webserver und verbessern die Skalierbarkeit eines ASP.NET-Diensts.

 Die folgenden APIs wurden hinzugefügt, um asynchrone Ausgabecacheanbieter zu unterstützen:

- Die <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=fullName>-Klasse, die von <xref:System.Web.Caching.OutputCacheProvider?displayProperty=fullName> erbt und es Entwicklern gestattet, einen asynchronen Ausgabecacheanbieter zu implementieren.

- Die <xref:System.Web.Caching.OutputCacheUtility>-Klasse, die Hilfsmethoden zum Konfigurieren des Ausgabecaches bereitstellt.

- 18 neue Methoden in der <xref:System.Web.HttpCachePolicy?displayProperty=fullName>-Klasse. Dazu zählen: <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A> und <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.

- 2 neue Methoden in der <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=fullName>-Klasse: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> und <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.

- 2 neue Methoden in der <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=fullName>-Klasse: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> und <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.

- 2 neue Methoden in der <xref:System.Web.HttpCacheVaryByParams?displayProperty=fullName>-Klasse: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> und <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.

- In der <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=fullName>-Klasse die <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A>-Methode.

- In der <xref:System.Web.Caching.CacheDependency>-Klasse die <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A>-Methode.

<a name="Strings"></a> 
### <a name="character-categories"></a>Zeichenkategorien
 Zeichen im [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] werden basierend auf dem [Unicode-Standard, Version 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) klassifiziert. In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], werden Zeichen basierend auf den Zeichenkategorien von Unicode 6.3 klassifiziert.

 Die Unterstützung von Unicode 8.0 ist beschränkt auf die Klassifizierung von Zeichen durch die <xref:System.Globalization.CharUnicodeInfo>-Klasse und auf Typen und Methoden, die darauf basieren. Dazu zählen die <xref:System.Globalization.StringInfo>-Klasse, die überladene <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>-Methode und die [Zeichenklassen](../../../docs/standard/base-types/character-classes-in-regular-expressions.md), die vom Modul für reguläre Ausdrücke von .NET Framework erkannt werden.  Der Vergleich und die Sortierung von Zeichen und Zeichenfolgen sind von dieser Änderung nicht betroffen und beruhen weiterhin auf dem zugrunde liegenden Betriebssystem oder auf Windows 7-Systemen auf Zeichendaten, die vom .NET Framework bereitgestellt wurden.

 Änderungen in Zeichenkategorien von Unicode 6.0 bis 7.0 Unicode finden Sie unter [Unicode Standard, Version 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) auf der Website des Unicode-Konsortiums. Änderungen von Unicode 7.0 bis 8.0 Unicode finden Sie unter [Unicode Standard, Version 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) auf der Website des Unicode-Konsortiums.

<a name="Crypto462"></a> 
### <a name="cryptography"></a>Kryptografie
 **Unterstützung von X 509-Zertifikaten, die FIPS 186-3 DSA enthalten**
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] unterstützt DSA X509-Zertifikate (Digital Signature Algorithm), deren Schlüssel die FIPS 186-2 1024-Bit-Grenze überschreiten.

 Zusätzlich zur Unterstützung der größeren Schlüsselgrößen von FIPS 186-3, erlaubt [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] die Berechnung von Signaturen mit der SHA-2-Familie der Hashalgorithmen (SHA256, SHA384 und SHA512). Die Unterstützung von FIPS 186-3 wird von der neuen <xref:System.Security.Cryptography.DSACng?displayProperty=fullName>-Klasse bereitgestellt.

 Gemäß der aktuellen Änderungen an der <xref:System.Security.Cryptography.RSA>-Klasse im .NET Framework 4.6 und an der <xref:System.Security.Cryptography.ECDsa>-Klasse im .NET Framework 4.6.1, verfügt die abstrakte Basisklasse <xref:System.Security.Cryptography.DSA> in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] über zusätzliche Methoden, um Aufrufern die Verwendung dieser Funktion ohne die Umwandlung zu erlauben. Sie können die <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=fullName>-Erweiterungsmethode zum Signieren von Daten verwenden, wie das folgende Beispiel veranschaulicht.

```csharp
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPrivateKey())
    {
        return dsa.SignData(data, HashAlgorithmName.SHA384);
    }
}
```

```vb 
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()
    Using DSA As DSA = cert.GetDSAPrivateKey()
        Return DSA.SignData(data, HashAlgorithmName.SHA384)
    End Using
End Function
```

 Sie können auch die <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=fullName>-Erweiterungsmethode zum Überprüfen signierter Daten verwenden, wie das folgende Beispiel veranschaulicht.

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

 **Verbesserte Übersichtlichkeit für Eingaben in die Schlüsselableitungsfunktions-Routinen für den Diffie-Hellman-Schlüsselaustausch**
 In.NET Framework 3.5 wurde die Unterstützung der Elliptic Curve Diffie-Hellman-Schlüsselübereinstimmung mit drei verschiedenen Schlüsselableitungsfunktions-Routinen (KDF) hinzugefügt. Die Eingaben in die Routinen und auch die Routinen selbst wurden mithilfe von Eigenschaften auf dem <xref:System.Security.Cryptography.ECDiffieHellmanCng>-Objekt konfiguriert. Da jedoch nicht jede Routine jede input-Eigenschaft liest,sorgte dies bisher bei Entwicklern für reichlich Verwirrungspotenzial.

 Um darauf in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] zu reagieren, wurden die folgenden drei Methoden zur <xref:System.Security.Cryptography.ECDiffieHellman-Basisklasse hinzugefügt, um diese KDF-Routinen und deren Eingaben eindeutiger darzustellen:

|Die ECDiffieHellman-Methode|Beschreibung|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mithilfe der Formel ab<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> wobei *x* das berechnete Ergebnis des EC Diffie-Hellman-Algorithmus ist.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mithilfe der Formel ab<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> wobei *x* das berechnete Ergebnis des EC Diffie-Hellman-Algorithmus ist.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Leitet Schlüsselmaterial mit dem Ableitungsalgorithmus der TLS-Pseudozufallsfunktion (pseudo-random function; PRF) ab.|

 **Unterstützung der symmetrischen Verschlüsselung persistenter Schlüssel**
 Die Windows-Kryptografiebibliothek (Cryptography API: Next Generation; CNG) verfügt über Unterstützung für die Speicherung persistenter symmetrischer Schlüssel und für die Verwendung von in der Hardware gespeicherter symmetrischer Schlüssel. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ermöglicht Entwicklern, diese Funktion zu verwenden.  Da das Konzept des Schlüsselnamens und des Schlüsselanbieters implementierungsspezifisch ist, erfordert die Nutzung dieser Funktion die Verwendung des Konstruktors der konkreten Implementierungstypen anstatt der bevorzugten Herangehensweise des Unternehmens (z.B. durch aufrufen von `Aes.Create`).

 Die Unterstützung der symmetrischen Verschlüsselung persistenter Schlüssel ist für die AES- (<xref:System.Security.Cryptography.AesCng>) und 3DES-Algorithmen (<xref:System.Security.Cryptography.TripleDESCng>) verfügbar. Beispiel:

```csharp
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)
{
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))
    {
        aes.IV = iv;

        // Using the zero-argument overload is required to make use of the persisted key
        using (ICryptoTransform encryptor = aes.CreateEncryptor())
        {
            if (!encryptor.CanTransformMultipleBlocks)
            {
                throw new InvalidOperationException("This is a sample, this case wasn’t handled...");
            }

            return encryptor.TransformFinalBlock(data, 0, data.Length);
        }
    }
}
```

```vb 
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)
        Aes.IV = iv

        ' Using the zero-argument overload Is required to make use of the persisted key
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()
            If Not encryptor.CanTransformMultipleBlocks Then
                Throw New InvalidOperationException("This is a sample, this case wasn’t handled...")
            End If
            Return encryptor.TransformFinalBlock(data, 0, data.Length)
        End Using
    End Using
End Function
```

 **SignedXml-Unterstützung des Hashing von SHA-2**
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] fügt Unterstützung für die <xref:System.Security.Cryptography.Xml.SignedXml>-Klasse für die Signaturmethoden RSA-SHA256, RSA-SHA384 und RSA-SHA512 PKCS#1 und für die Referenzalgorithmen SHA256, SHA384 sowie SHA512 hinzu.

 Die URI-Konstanten sind alle für <xref:System.Security.Cryptography.Xml.SignedXml> verfügbar gemacht:

|SignedXml-Feld|Konstante|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|

 Alle Programme, die einen benutzerdefinierten <xref:System.Security.Cryptography.SignatureDescription>-Handler in <xref:System.Security.Cryptography.CryptoConfig> registriert haben, um die Unterstützung für diese Algorithmen hinzuzufügen, funktionieren weiterhin wie zuvor, aber da es jetzt Standardwerte für Plattformen gibt, ist die <xref:System.Security.Cryptography.CryptoConfig>-Registrierung nicht mehr erforderlich.

<a name="SQLClient"></a> 
### <a name="sqlclient"></a>SqlClient
 Der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient?displayProperty=fullName>) enthält die folgenden neuen Features in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:

 **Verbindungspooling und Timeouts mit Azure SQL-Datenbanken**
 Wenn das Verbindungspooling aktiviert ist und ein Timeoutfehler oder ein anderer Anmeldefehler auftritt, wird eine Ausnahme zwischengespeichert, und die zwischengespeicherte Ausnahme wird für jeden nachfolgenden Verbindungsversuch für einen Zeitraum von fünf Sekunden bis zu einer Minute ausgelöst.  Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).

 Dieses Verhalten ist bei einer Verbindung zu Azure SQL-Datenbanken unerwünscht, da Verbindungsversuche mit flüchtigen Fehlern fehlschlagen können, die normalerweise schnell wiederhergestellt werden. Das Sperrfristverhalten des Verbindungspools wird entfernt, wenn die Verbindungsversuche zu Azure SQL-Datenbanken fehlschlagen, damit erneute Verbindungsversuche leichter erfolgen können.

 Mit dem Hinzufügen des neuen `PoolBlockingPeriod`-Schlüsselworts können Sie die Sperrfrist auswählen, die für Ihre App am besten geeignet ist. Mögliche Werte:

 `Auto`
 Die Sperrfrist des Verbindungspools für eine Anwendung, die eine Verbindung mit einer Azure SQL-Datenbank herstellt, ist deaktiviert, und die Sperrfrist des Verbindungspools für eine Anwendung, die eine Verbindung mit einem anderen SQL-Server herstellt, ist aktiviert. Dies ist der Standardwert. Wenn der Serverendpunktname eine der folgenden Endungen besitzt, werden sie als Azure SQL-Datenbanken bezeichnet:

- .database.windows.net

- .database.chinacloudapi.cn

- .database.usgovcloudapi.net

- .database.cloudapi.de

 `AlwaysBlock` Die Sperrfrist des Verbindungspools ist immer aktiviert.

 `NeverBlock` Die Sperrfrist des Verbindungspools ist immer deaktiviert.

 **Verbesserungen für Always Encrypted** SQLClient führt zwei Verbesserungen für Always Encrypted ein:

- Verschlüsselungsmetadaten für Abfrageparameter werden nun zwischengespeichert, um die Leistung von parametrisierten Abfragen von verschlüsselten Datenbankspalten zu verbessert. Mit der auf `true` (Standardwert) festgelegten <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=fullName>-Eigenschaft ruft der Client, wenn dieselbe Abfrage mehrmals aufgerufen wird, Parametermetadaten von Server nur einmal ab.

- Schlüsseleinträge für die Spaltenverschlüsselung im Schlüsselcache werden jetzt nach einem konfigurierbaren Zeitintervall entfernt, das mithilfe der <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=fullName>-Eigenschaft festgelegt wird.

<a name="WCF"></a> 
### <a name="windows-communication-foundation"></a>Windows Communication Foundation
 In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wurde die Windows Communication Foundation in den folgenden Bereichen erweitert:

 **Unterstützung der WCF-Transportsicherheit für Zertifikate, die mithilfe der CNG gespeichert wurden**
 WCF-Transportsicherheit unterstützt Zertifikate, die mithilfe der Windows-Kryptographiebibliothek (CNG) gespeichert wurden. Diese Unterstützung ist in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] auf die Verwendung von Zertifikaten mit einem öffentlichen Schlüssel beschränkt, der über einen Exponent mit einer Länge von nicht mehr als 32 Bit verfügt. Wenn sich eine Anwendung auf den [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] bezieht, so ist diese Funktion standardmäßig aktiviert.

 Für Anwendungen, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früher abzielen, aber auf [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ausgeführt werden, kann diese Funktion aktiviert werden, indem die folgende Zeile zum Abschnitt „[\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)“ der Datei „app.config“ oder „web.config“ hinzugefügt wird.

```xml
<AppContextSwitchOverrides
    value="Switch.System.ServiceModel.DisableCngCertificates=false"
/>
```

Dies kann auch programmgesteuert mit dem Code durchgeführt werden, so wie in folgendem Beispiel gezeigt:

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";
AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

 **Bessere Unterstützung mehrerer Anpassungsregeln für die Sommerzeit durch die DataContractJsonSerializer-Klasse**
 Kunden können eine Anwendungskonfigurationseinstellung verwenden, um zu bestimmen, ob die Klasse <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> mehrere Anpassungsregeln für eine Zeitzone unterstützt. Dies ist ein Opt-in-Feature. Fügen Sie die folgende Einstellung der Datei app.config hinzu, um sie zu aktivieren:

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

Wenn dieses Feature aktiviert ist, verwendet ein <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>-Objekt den <xref:System.TimeZoneInfo>-Typ anstelle des <xref:System.TimeZone>-Typs zum Deserialisieren von Datums- und Zeitdaten. <xref:System.TimeZoneInfo> unterstützt mehrere Anpassungsregeln, die es ermöglichen, mit veralteten Zeitzonendaten. <xref:System.TimeZone> unterstützt dies nicht.

Weitere Informationen zur <xref:System.TimeZoneInfo>-Struktur und zu Zeitzonenanpassungen finden Sie unter [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).

**Beibehaltung einer UTC-Zeit bei der Serialisierung und Deserialisierung mit der XmlSerializer-Klasse** Wenn die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Serialisieren eines <xref:System.DateTime>-UTC-Werts verwendet wird, erstellt sie normalerweise eine serialisierte Zeitzeichenfolge, die das Datum und die Uhrzeit beibehält, jedoch davon ausgeht, dass die Zeit die Ortszeit ist.  Wenn Sie beispielsweise ein UTC-Datum und eine UTC-Uhrzeit instanziieren, indem Sie den folgenden Code aufrufen:

```csharp
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);
```

```vb
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)
```

ist das Ergebnis für ein System, das acht Stunden hinter der Zeitzone UTC liegt, die serialisierte Zeitzeichenfolge „03:00:00.0000000-08:00“.  Serialisierte Werte sind zudem immer als lokale Datums- und Uhrzeitwerte deserialisiert.

 Sie können eine Anwendungskonfigurationseinstellung verwenden, um zu bestimmen, ob die <xref:System.Xml.Serialization.XmlSerializer>-Klasse die UTC-Zeitzoneninformation beibehält, wenn sie die <xref:System.DateTime>-Werte serialisiert und deserialisiert:

```xml 
<runtime>
     <AppContextSwitchOverrides 
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />
</runtime>
```

Wenn dieses Feature aktiviert ist, verwendet ein <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>-Objekt den <xref:System.TimeZoneInfo>-Typ anstelle des <xref:System.TimeZone>-Typs zum Deserialisieren von Datums- und Zeitdaten. <xref:System.TimeZoneInfo> unterstützt mehrere Anpassungsregeln, die es ermöglichen, mit veralteten Zeitzonendaten. <xref:System.TimeZone> unterstützt dies nicht.

Weitere Informationen zur <xref:System.TimeZoneInfo>-Struktur und zu Zeitzonenanpassungen finden Sie unter [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).

 **Höchste Übereinstimmung von NetNamedPipeBinding **
 WCF bietet eine neue App-Einstellung, die für Clientanwendungen festgelegt werden kann, um sicherzustellen, dass diese immer eine Verbindung zu dem Dienst herstellen, der an dem URI lauscht, der die höchste Übereinstimmung zu dem aufweist, den die Anwendungen anfordern. Wenn diese App-Einstellung auf `false` (Standard) festgelegt ist, ist es für Clients möglich, <xref:System.ServiceModel.NetNamedPipeBinding> zu verwenden, um zu versuchen, eine Verbindung zu einem Dienst herzustellen, der an einen URI lauscht, der eine Teilzeichenfolge des angeforderten URI darstellt.

 Angenommen, ein Client versucht, eine Verbindung zu einem Dienst herzustellen, der an `net.pipe://localhost/Service1` lauscht, aber ein anderer Dienst auf dem Computer, der mit Administratorrechten ausgeführt wird, lauscht an `net.pipe://localhost`. Der Client würde versuchen, mit dieser App-Einstellung, die auf `false` festgelegt ist, eine Verbindung zu dem falschen Dienst herzustellen. Nach dem Festlegen der App-Einstellung auf `true`, wird der Client stets eine Verbindung zu den passendsten Dienst herstellen.

> [!NOTE]
>  Clients, die <xref:System.ServiceModel.NetNamedPipeBinding> verwenden, suchen Dienste, die auf der Basisadresse des Diensts basieren (soweit vorhanden) anstatt die vollständige Endpunktadresse. Damit diese Einstellung immer funktioniert muss der Dienst eine eindeutige Basisadresse verwenden.

 Fügen Sie die folgende App-Einstellung der App.config- oder Web.config-Datei der Anwendung Ihres Clients hinzu, um die Änderung zu aktivieren:

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

 **SSL 3.0 ist kein Standardprotokoll**
 Bei der Verwendung von NetTcp im Transportsicherheitsmodus und der Einstellung „Zertifikat“ wird SSL 3.0 nicht länger als eines der Standardprotokolle für das Aushandeln einer sicheren Verbindung verwendet. In den meisten Fällen sollte es keine Auswirkungen auf vorhandene Apps geben, da TLS 1.0 in der Protokollliste für NetTcp enthalten ist. Alle vorhandenen Clients sollten in der Lage sein, eine Verbindung mit mindestens TLS 1.0 auszuhandeln.      Wenn Ssl3 erforderlich ist, verwenden Sie eine der folgenden Konfigurationsmechanismen, um es der Liste der ausgehandelten Protokolle hinzuzufügen.

- Die <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName>-Eigenschaft

- Die <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName>-Eigenschaft

- Der Abschnitt [\<transport>](../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) des Abschnitts [\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)

- Der Abschnitt [\<sslStreamSecurity>](../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) des Abschnitts [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

<a name="WPF462"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wurde die Windows Presentation Foundation in den folgenden Bereichen erweitert:

 **Sortieren von Gruppen**
 Eine Anwendung, die ein <xref:System.Windows.Data.CollectionView>-Objekt zum gruppieren von Daten verwendet, kann nun explizit deklarieren, wie die Gruppen sortiert werden. Das explizite Sortieren behebt das Problem der nicht-intuitiven Sortierung beim dynamischen Hinzufügen oder Entfernen von Gruppen und beim Ändern des Wert der beim Gruppieren beteiligten Elementeigenschaften durch eine App. Diese Vorgehensweise kann auch die Leistung des Gruppenerstellungsprozesses verbessern, indem Vergleiche der Gruppierungseigenschaften nicht bei der Sortierung der vollständigen Sammlung, sondern bei der Sortierung der Gruppen erfolgen/vorgenommen werden.

 Zur Unterstützung der Gruppensortierung beschreiben die neuen Eigenschaften <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=fullName> und <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=fullName> wie die Auflistung von Gruppen sortiert wird, die vom <xref:System.ComponentModel.GroupDescription>-Objekt erzeugt wurden. Dies ist vergleichbar mit der Art wie gleichnamigen <xref:System.Windows.Data.ListCollectionView>-Eigenschaften die Sortierung der Datenelemente beschreiben.

 Zwei neue statische Eigenschaften der <xref:System.Windows.Data.PropertyGroupDescription>-Klasse, <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> und <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, können für die am häufigsten vorkommenden Fälle verwendet werden.

 Zum Beispiel gruppiert der folgende XAML-Code Daten nach Alter, sortiert die Gruppen in aufsteigender Reihenfolge und gruppierten die Elemente in den einzelnen Gruppen anhand des Nachnamens.

```xaml
<GroupDescriptions>
     <PropertyGroupDescription 
         PropertyName=”Age” 
         CustomSort= 
              ”{x:Static PropertyGroupDescription.CompareNamesAscending}”/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName=”LastName”/>
</SortDescriptions>
```

 **Unterstützung der Bildschirmtastatur**
 Die Unterstützung der Bildschirmtastatur ermöglicht die fokussierte Verfolgung in WPF-Anwendungen, indem automatisch die neue Bildschirmtastatur in Windows 10 aufgerufen und geschlossen wird, wenn die Fingereingabe von einem Steuerelement empfangen wird, das Texteingabe nutzen kann.

 In früheren Versionen des .NET-Frameworks konnte für WPF-Anwendungen die Fokusverfolgung nur aktiviert werden, wenn in WPF die Unterstützung für Stifte und Touchgesten deaktiviert wurde.  Die WPF-Anwendungen müssen daher zwischen der vollständiger WPF-Gestenunterstützung und der Windows-Mausheraufstufung wählen.

 **DPI pro Monitor**
 Um die neueste Vervielfältigung von hohen DPI- und hybrider DPI-Umgebungen für WPF-Apps zu unterstützen, sorgt WPF dafür, dass monitorspezifische DPI-Werte in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] erkannt werden. Weitere Informationen dazu, wie Sie in Ihrer WPF-Anwendung dafür sorgen, dass Sie mit monitorspezifischen DPI-Werten kompatibel ist, finden Sie unter [Samples and Developer Guide](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) (Beispiele und Entwicklerhandbuch) auf GitHub.

 In früheren Versionen von .NET Framework sind WPF-Apps kompatibel mit systemspezifischen DPI-Werten. Die Benutzeroberfläche der Anwendung wird anders gesagt ggf. mit dem Betriebssystem skaliert, abhängig von der DPI des Monitors, auf dem die App gerendert wird. ,

 Apps, die unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ausgeführt werden, können Sie monitorspezifische DPI-Änderungen in WPF-Apps deaktivieren, indem Sie eine Konfigurationsanweisung zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen, so wie in folgendem Beispiel gezeigt:

```xml
<runtime>
   <AppContextSwitchOverrides value=”Switch.System.Windows.DoNotScaleForDpiChanges=false”/>
</runtime>
```

<a name="WF462"></a> 
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)
 In [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wurde die Windows Workflow Foundation im folgenden Bereich erweitert:

 **Unterstützung für C#-Ausdrücke und IntelliSense im neu gehosteten WF-Designer**
 Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] unterstützt WF C#-Ausdrücke sowohl im Visual Studio-Designer als auch in Codeworkflows. Der neu gehostete Workflow-Designer ist eine wichtige Funktion von WF, die zulässt, dass sich der Workflow-Designer in einer Anwendung außerhalb von Visual Studio befindet (z.B. in WPF).  Windows Workflow Foundation bietet die Möglichkeit der Unterstützung von C#-Ausdrücken und IntelliSense im neu gehosteten Workflow-Designer. Weitere Informationen finden Sie im [Windows Workflow Foundation-Blog](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).

 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`
 In Versionen von .NET Framework vor [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] wird IntelliSense in WF-Designer unterbrochen, wenn ein Kunde ein Workflowprojekt von Visual Studio neu erstellt. Obwohl die Erstellung des Projekts erfolgreich war, können die Workflowtypen nicht im Designer gefunden werden und IntelliSense gibt Warnungen für die fehlenden Workflowtypen im Fenster **Fehlerliste** aus. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] behandelt dieses Problem und macht IntelliSense verfügbar.

 **Workflow V1-Anwendungen mit aktivierter Workflowüberwachung werden im FIPS-Modus ausgeführt**
 Computer mit aktiviertem FIPS-Kompatibilitätsmodus können jetzt erfolgreich eine Anwendung, die dem Stil der Workflowversion 1 entspricht, mit aktivierter Workflowüberwachung ausführen. Sie müssen die folgenden Änderungen in Ihrer app.config-Datei vornehmen, um dieses Szenario zu aktivieren:

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

 Wenn dieses Szenario nicht aktiviert ist, führt das Ausführen der Anwendung weiterhin dazu, dass eine Ausnahme mit folgender Meldung ausgelöst wird: „Diese Implementation ist nicht Teil der Windows Platform FIPS-überprüften kryptografischen Algorithmen.“

 **Verbesserungen des Workflows bei der Verwendung von dynamischen Updates mit dem Workflow-Designer von Visual Studio**
 Der Workflow-Designer, der Flussdiagramm-Aktivitätsdesigner und andere Workflow-Aktivitätsdesigner laden nun erfolgreich Workflows, die nach dem Aufruf der Methode <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> gespeichert wurden, und zeigen diese an. In Versionen von .NET Framework vor [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], kann das Laden einer XAML-File in Visual Studio für einen Workflow, der nach dem Aufruf von <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> gespeichert wurde, zu folgenden Problemen führen:

- Der Workflow-Designer kann die XAML-Datei nicht ordnungsgemäß laden (wenn sich <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=fullName> am Ende der Zeile befindet).

- Der Flussdiagramm-Aktivitätsdesigner oder andere Workflow-Aktivitätsdesigner können möglicherweise alle Objekte an ihrem Standardspeicherort anzeigen, im Gegensatz zu angefügten Eigenschaftswerten.

<a name="ClickOnce"></a> 
### <a name="clickonce"></a>ClickOnce
 ClickOnce wurde zur Unterstützung von TLS 1.1 und TLS 1.2 neben dem 1.0-Protokoll aktualisiert, das schon unterstützt wird. ClickOnce erkennt automatisch, welches Protokoll erforderlich ist. Es sind keine zusätzlichen Schritte innerhalb der ClickOnce-Anwendung erforderlich, um die TLS 1.1 und 1.2-Unterstützung zu aktivieren.

<a name="UWPConvert"></a> 
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Konvertieren von Windows Forms und WPF-Apps in UWP-Apps
 Windows bietet nun Möglichkeiten, vorhandene Windows Desktop-Apps, einschließlich WPF- und Windows Forms-Apps, auf der Universal Windows Platform (UWP) bereitzustellen. Diese Technologie agiert als Brücke, indem sie Ihnen ermöglicht, Ihre vorhandene Codebasis nach und nach zu UWP zu migrieren und so Ihre App auf allen Windows 10-Geräten bereitzustellen.

 Konvertierte Desktop-Apps erlangen eine App-Identität ähnlich der App-Identität von UWP-Apps, wodurch UWP-APIs zugänglich gemacht werden, um Funktionen wie Live-Kacheln und Benachrichtigungen zu aktivieren. Die App verhält sich weiterhin wie zuvor und wird als voll vertrauenswürdige App ausgeführt. Sobald die App konvertiert ist, kann ein App-Container-Prozess zum vorhandenen voll vertrauenswürdigen Prozess hinzugefügt werden, um eine adaptive Benutzeroberfläche hinzuzufügen. Wenn alle Funktionen in den App-Container-Prozess verschoben werden, kann der vollständig vertrauenswürdige Prozess entfernt werden, und die neue UWP-App kann auf allen Windows 10-Geräten zur Verfügung gestellt werden.

<a name="Debug462"></a> 
### <a name="debugging-improvements"></a>Verbesserungen beim Debugging
 Die *nicht verwaltete Debug-API* wurde im [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] verbessert, um zusätzlichen Analysen durchzuführen, wenn eine <xref:System.NullReferenceException>-Klasse ausgelöst wird, sodass es möglich ist, zu bestimmen, welche Variablen in einer einzelnen Zeile des Quellcodes `null` ist.   Um dieses Szenario zu unterstützen, wurden die folgenden APIs der nicht verwalteten Debug-API hinzugefügt.

- Die Schnittstellen [ICorDebugCode4](../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md), und [ICorDebugVariableHomeEnum](../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md), die den Ursprungsort verwalteter Variablen verfügbar machen. Dadurch können Debugger Codeflussanalysen durchführen, wenn eine <xref:System.NullReferenceException>-Klasse auftritt und auf dieser Grundlage die verwaltete Variable zu bestimmen, die dem nativen Speicherort entspricht, der `null` war.

- Die Methode [ICorDebugType2::GetTypeID](../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) bietet eine Zuordnung für die Schnittstelle „ICorDebugType“ zur Struktur [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), wodurch der Debugger eine [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)-Struktur ohne eine Instanz der Schnittstelle „ICorDebugType“ abrufen kann. Vorhandenen APIs auf der [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)-Struktur kann dann verwendet werden, um das Klassenlayout des Typs zu bestimmen.

<a name="v461"></a> 
## <a name="whats-new-in-the-net-framework-461"></a>Neuigkeiten in .NET Framework 4.6.1
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] enthält neue Features in den folgenden Bereichen:

- [Kryptografie](#Crypto)

- [ADO.NET](#ADO.NET461)

- [Windows Presentation Foundation (WPF)](#WPF461)

- [Windows Workflow Foundation](#WWF461)

- [Profilerstellung](#Profile461)

- [NGen](#NGEN461)

 Weitere Informationen zu [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] finden Sie unter den folgenden Themen:

- [Liste der Änderungen in .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=622964)

- [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

- [Unterschiede der .NET Framework-API](http://go.microsoft.com/fwlink/?LinkId=622989) (auf GitHub)

<a name="Crypto"></a> 
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Kryptografie: Unterstützung für X509-Zertifikate mit ECDSA
 RSACng-Unterstützung für X509-Zertifikate in .NET Framework 4.6. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] fügt Unterstützung für ECDSA (Elliptic Curve Digital Signature Algorithm) X509-Zertifikate hinzu.

 ECDSA bietet eine bessere Leistung und einen sichereren Kryptografiealgorithmus als RSA. Somit ist die Lösung eine hervorragende Wahl, wenn es um TLS (Transport Layer Security)-Leistung und Skalierbarkeit geht. Die .NET Framework-Implementierung schließt Aufrufe in die vorhandene Windows-Funktionalität ein.

 Im folgenden Codebeispiel wird gezeigt, wie einfach es ist, eine Signatur für einen Bytedatenstrom mit der neuen in [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] enthaltenen ECDSA-Unterstützung für X509-Zertifikate zu generieren.

 [!code-csharp[whatsnew.461.crypto#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
 [!code-vb[whatsnew.461.crypto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

 Dies steht in deutlichem Gegensatz zu dem Code, der zum Generieren einer Signatur in .NET Framework 4.6 erforderlich war.

 [!code-csharp[whatsnew.461.crypto#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
 [!code-vb[whatsnew.461.crypto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461"></a> 
### <a name="adonet"></a>ADO.NET
 ADO.NET wurde um die folgenden Features erweitert:

 Always Encrypted-Unterstützung für hardwaregeschützte Schlüssel ADO.NET unterstützt jetzt die native Speicherung von Always Encrypted-Spaltenhauptschlüsseln in Hardwaresicherheitsmodulen (Hardware Security Modules, HSMs). Mit dieser Unterstützung profitieren Kunden von asymmetrischen, in HSMs gespeicherten Schlüsseln, ohne benutzerdefinierte Spaltenhauptschlüssel-Speicheranbieter zu schreiben und in Anwendungen registrieren zu müssen.

 Kunden müssen die vom HSM-Anbieter bereitgestellten CSP-Anbieter oder CNG-Schlüsselspeicheranbieter auf den App-Servern oder Clientcomputern installieren, um über die in einem HSM gespeicherten Spaltenhauptschlüssel auf die mit "Always Encrypted" geschützten Daten zuzugreifen.

 Verbesserung des Verbindungsverhaltens <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> für AlwaysOn-SQLClient ermöglicht jetzt automatisch schnellere Verbindungen mit einer AlwaysOn-Verfügbarkeitsgruppe (Availability Group, AG). Er erkennt auf transparente Weise, ob die Anwendung eine Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe in einem anderen Subnetz herstellt, ermittelt schnell den aktiven Server und stellt eine Verbindung mit dem Server her. Vor dieser Version musste eine Anwendung `“MultisubnetFailover=true”` in die Verbindungszeichenfolge einschließen, um anzugeben, dass eine Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe hergestellt wurde. Wenn das Verbindungsschlüsselwort nicht auf `true` festgelegt wird, kann bei der Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe ein Anwendungstimeout auftreten. Mit dieser Version muss eine Anwendung <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> *nicht* mehr auf `true` festlegen. Weitere Informationen zur SqlClient-Unterstützung für AlwaysOn-Verfügbarkeitsgruppen finden Sie unter [SqlClient-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung](../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).

<a name="WPF461"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 Windows Presentation Foundation umfasst eine Reihe von Verbesserungen und Änderungen.

 Leistungssteigerung Die Verzögerung beim Auslösen von Berührungsereignissen wurde in [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] behoben. Wenn eine Eingabe in ein <xref:System.Windows.Controls.RichTextBox>-Steuerelement erfolgt, wird außerdem der Renderthread während der schnellen Eingabe nicht mehr vollständig beansprucht.

 Verbesserte Rechtschreibprüfung Die Rechtschreibprüfung in WPF wurde unter Windows 8.1 und höheren Versionen aktualisiert, um die Betriebssystemunterstützung für die Rechtschreibprüfung zusätzlicher Sprachen zu nutzen.  Bezüglich der Funktionalität in Windows-Versionen vor Windows 8.1 gibt es keine Änderung.

 Wie in früheren .NET Framework-Versionen wird die Sprache eines <xref:System.Windows.Controls.TextBox>-Steuerelements oder <xref:System.Windows.Controls.RichTextBox>-Blocks ermittelt, indem in der folgenden Reihenfolge nach Informationen gesucht wird:

- `xml:lang`, falls vorhanden.

- Aktuelle Eingabesprache

- Aktuelle Threadkultur

 Weitere Informationen zur Sprachunterstützung in WPF finden Sie im [WPF-Blogbeitrag zu .NET Framework 4.6.1-Features](http://go.microsoft.com/fwlink/?LinkID=691819).

 Zusätzliche Unterstützung für benutzerdefinierte Benutzerwörterbücher In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] erkennt WPF Benutzerwörterbücher, die global registriert sind. Diese Funktion ist zusätzlich zur Registrierung der Wörterbücher pro Steuerelement verfügbar.

 In früheren WPF-Versionen wurden Listen ausgeschlossener Wörter und AutoKorrektur-Listen von benutzerdefinierten Wörterbüchern nicht erkannt. Diese werden unter Windows 8.1 und Windows 10 mittels Dateien unterstützt, die im Verzeichnis `%AppData%\Microsoft\Spelling\<language tag>` abgelegt werden können.  Für diese Dateien gelten die folgenden Regeln:

- Die Dateien sollten über die Erweiterungen ".dic" (hinzugefügte Wörter), ".exc" (ausgeschlossene Wörter) oder ".acl" (AutoKorrektur-Wörter) verfügen.

- Außerdem sollten sie das UTF-16LE-Nur-Text-Format aufweisen, das mit der Bytereihenfolgenmarke (Byte Order Mark, BOM) beginnt.

- Jede Zeile sollte aus einem Wort (aus der Liste hinzugefügter und ausgeschlossener Wörter) oder einem AutoKorrektur-Paar bestehen, bei dem die Wörter durch einen senkrechten Strich („&#124;“) (in der AutoKorrektur-Wortliste) getrennt sind.

- Diese Dateien sind schreibgeschützt und werden vom System nicht geändert.

> [!NOTE]
>  Diese neuen Dateiformate werden von der WPF-Rechtschreibprüfungs-API nicht direkt unterstützt, sodass die benutzerdefinierten Wörterbücher, die in Anwendungen für WPF bereitgestellt werden, weiterhin LEX-Dateien verwenden sollten.

 Beispiele Auf MSDN finden sich eine Reihe von [WPF-Beispielen](https://msdn.microsoft.com/library/ms771633.aspx). Mehr als 200 der bekanntesten Beispiele werden (basierend auf ihrer Verwendung) in ein [Open Source-GitHub-Repository](https://github.com/Microsoft/WPF-Samples) verschoben. Helfen Sie uns bei der Verbesserung unserer Beispiele, indem Sie uns einen Pull Request senden oder ein [GitHub-Problem](https://github.com/Microsoft/WPF-Samples/issues) eröffnen.

 DirectX-Erweiterungen WPF enthält ein [NuGet-Paket](http://go.microsoft.com/fwlink/?LinkID=691342) mit neuen Implementierungen von <xref:System.Windows.Interop.D3DImage>. Diese erleichtern die Interoperabilität mit DX10- und DX11-Inhalten. Der Code für dieses Paket steht als Open Source-Code auf [GitHub](https://github.com/Microsoft/WPFDXInterop) zur Verfügung.

<a name="WWF461"></a> 
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: Transaktionen
 Die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName>-Methode kann jetzt einen anderen verteilten Transaktions-Manager als MSDTC verwenden, um die Transaktion höher zu stufen. Dazu geben Sie einen Bezeichner zur Höherstufung der GUID-Transaktion für die neue <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName>-Überladung an. Wenn dieser Vorgang erfolgreich ist, unterliegt die Transaktionsfunktionalität gewissen Einschränkungen. Sobald ein Nicht-MSDTC-Transaktionspromoter eingetragen wird, lösen die folgenden Methoden eine <xref:System.Transactions.TransactionPromotionException> aus, da diese Methoden die Höherstufung auf MSDTC erfordern:

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=fullName>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=fullName>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=fullName>

 Sobald ein Nicht-MSDTC-Transaktionspromoter eingetragen wird, muss er mit dauerhaften Eintragungen verwendet werden. Dabei werden die von ihm definierten Protokolle verwendet. Die <xref:System.Guid> des Transaktionspromoters kann mithilfe der <xref:System.Transactions.Transaction.PromoterType%2A>-Eigenschaft abgerufen werden. Bei der Höherstufung der Transaktion stellt der Transaktionspromoter ein <xref:System.Byte>-Array bereit, das das höher gestufte Token darstellt. Eine Anwendung kann das höher gestufte Token für eine nicht von MSDTC höher gestufte Transaktion mit der <xref:System.Transactions.Transaction.GetPromotedToken%2A>-Methode abrufen.

 Benutzer der neuen <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName>-Überladung müssen einer bestimmten Aufrufsequenz folgen, damit die Höherstufung erfolgreich abgeschlossen werden kann. Diese Regeln werden in der Dokumentation der Methode beschrieben.

<a name="Profile461"></a> 
### <a name="profiling"></a>Profilerstellung
 Die nicht verwaltete Profilerstellungs-API wurde wie folgt erweitert:

 Bessere Unterstützung für den Zugriff auf die PDB-Dateien in der [ICorProfilerInfo7](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)-Schnittstelle In ASP.Net 5 werden Assemblys zunehmend im Arbeitsspeicher von Roslyn kompiliert. Für Entwickler von Profilertools bedeutet dies, dass PDB-Dateien, die früher auf Datenträgern serialisiert wurden, u. U. nicht mehr vorkommen. Profilertools verwenden PDB-Dateien häufig, um Codezeilen wieder den Quellzeilen zuzuordnen, beispielsweise für die Codeabdeckung oder zeilenweise Leistungsanalysen. Die [ICorProfilerInfo7](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)-Schnittstelle enthält jetzt zwei neue Methoden, [ICorProfilerInfo7::GetInMemorySymbolsLength](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) und [ICorProfilerInfo7::ReadInMemorySymbols](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), um diesen Profilertools Zugriff auf die PDB-Daten im Arbeitsspeicher zu gewähren. Mithilfe der neuen APIs kann ein Profiler Inhalte einer im Arbeitsspeicher enthaltenen PDB-Datei als Bytearray abrufen und dieses anschließend verarbeiten oder auf den Datenträger serialisieren.

 Bessere Instrumentation mit den ICorProfiler-Schnittstellenprofilern, die die ReJit-Funktionalität der `ICorProfiler`-API für die dynamische Instrumentation verwenden, kann jetzt einige Metadaten ändern. Früher konnte IL durch diese Tools jederzeit instrumentiert werden, während Metadaten nur zur Ladezeit des Moduls geändert werden konnten. Da IL auf Metadaten verweist, sind die möglichen Instrumentationsarten eingeschränkt. Wir haben einige dieser Beschränkungen durch Hinzufügen der [ICorProfilerInfo7::ApplyMetaData](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)-Methode aufgehoben. Dadurch werden einige Metadatenbearbeitungen nach dem Laden des Moduls ermöglicht, insbesondere das Hinzufügen neuer `AssemblyRef`-, `TypeRef`-, `TypeSpec`-, `MemberRef`-, `MemberSpec`- und `UserString`-Datensätze. Diese Änderung erweitert die Möglichkeiten der dynamischen Instrumentation.

<a name="NGEN461"></a> 
### <a name="native-image-generator-ngen-pdbs"></a>NGEN (Native Image Generator)-PDBs
 Die computerübergreifende Ereignisablaufverfolgung ermöglicht Kunden die Profilerstellung für ein Programm auf Computer A und die Anzeige der Profilerstellungsdaten per Quellzeilenzuordnung auf Computer B. Unter früheren .NET Framework-Versionen musste der Benutzer alle Module und systemeigenen Images vom Profilcomputer auf den Analysecomputer kopieren, der die IL PDB-Datei für die Zuordnung zwischen Quellzeilen und systemeigenen Images enthielt. Während dies bei kleineren Dateien wie Handy-Apps durchaus gut funktionieren kann, können Desktopsystemdateien ziemlich anwachsen und beträchtliche Zeit für das Kopieren erfordern.

 Bei NGEN PDB-Dateien kann NGen eine PDB-Datei erstellen, die die Zuordnung zwischen IL und systemeigenen Images enthält, ohne dass eine Abhängigkeit von der IL PDB-Datei besteht. In diesem Szenario für die computerübergreifende Ereignisablaufverfolgung muss lediglich die von Computer A generierte PDB-Datei für systemeigene Images auf Computer B kopiert werden, und die [Debug Interface Access-APIs](https://msdn.microsoft.com/library/ee8x173s.aspx) müssen verwendet werden, um die „Quellzeilen-zu-IL“-Zuordnung der IL PDB-Datei und die „IL-zu-systemeigene Images“-Zuordnung der PDB-Datei für systemeigene Images zu lesen. Durch die Kombination beider Zuordnungen entsteht eine Zuordnung zwischen Quellzeilen und systemeigenem Image. Da die PDB-Datei für systemeigene Images viel kleiner als alle Module und systemeigenen Images ist, wird das Kopieren von Computer A auf Computer B deutlich beschleunigt.

<a name="v46"></a> 
## <a name="whats-new-in-net-2015"></a>Neuigkeiten in .NET 2015
 In .NET 2015 werden [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und .NET Core eingeführt. Einige neue Funktionen gelten für beide, während andere Funktionen für [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] bzw. [!INCLUDE[net_core](../../../includes/net-core-md.md)] spezifisch sind.

- **ASP.NET 5**

     .NET 2015 enthält ASP.NET 5, eine schlanke .NET-Plattform zum Erstellen moderner, cloudbasierter Apps. Die Plattform ist modular aufgebaut, sodass Sie nur die Funktionen aufnehmen können, die Sie in Ihrer Anwendung benötigen. Sie kann auf IIS oder eigenständig in einem benutzerdefinierten Prozess gehostet werden, und Sie können Apps mit verschiedenen Versionen von .NET Framework auf demselben Server ausführen. Sie umfasst ein neues Umgebungskonfigurationssystem, das für die Cloudbereitstellung entwickelt wurde.

     MVC, Web-API und Webseiten sind in einem einzigen Framework namens MVC 6 vereint. Sie erstellen ASP.NET 5-Apps mithilfe der neuen Tools in Visual Studio 2015. Ihre vorhandenen Anwendungen funktionieren im neuen .NET Framework. Um jedoch eine App zu erstellen, die MVC 6 oder SignalR 3 verwendet, müssen Sie das Projektsystem in Visual Studio 2015 verwenden.

     Weitere Informationen finden Sie unter [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).

- **Updates für ASP.NET**

    - **Aufgabenbasierte API für die asynchrone Antwortleerung**

         ASP.NET verfügt nun mit <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=fullName> über eine einfache aufgabenbasierte API für die asynchrone Antwortleerung. Hiermit wird mithilfe der `async/await`-Unterstützung für Ihre Sprache die asynchrone Leerung von Antworten ermöglicht.

    - `Model binding supports task-returning methods`

         In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], ASP.NET wurde das Modellbindungsfeature hinzugefügt, das einen erweiterbaren, codeorientierten Ansatz für CRUD-basierte Datenvorgänge in Web Forms-Seiten und Benutzersteuerelementen ermöglicht. Das Modellbindungssystem unterstützt nun wiederkehrende <xref:System.Threading.Tasks.Task>-Modellbindungsmethoden. Dadurch erhalten Web Forms-Entwickler die Vorteile hinsichtlich der Asynchronität und die Einfachheit des Datenbindungssystems beim Verwenden neuerer Versionen von ORMs, einschließlich des Entity Frameworks.

         Die asynchrone Modellbindung wird durch die `aspnet:EnableAsyncModelBinding`-Konfigurationseinstellung gesteuert.

        ```
        <appSettings>
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
        </appSettings>
        ```

         Bei auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielenden Apps wird der Standardwert auf `true` festgelegt. Bei Apps unter [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], die auf eine frühere Version von .NET Framework abzielen, ist `false` der Standard. Dies kann aktiviert werden, indem die Konfigurationseinstellung auf `true` festgelegt wird.

    - **HTTP/2-Unterstützung (Windows 10)**

         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) ist eine neue Version des HTTP-Protokolls, die eine wesentlich bessere Nutzung von Verbindungen ermöglicht (weniger Roundtrips zwischen Client und Server) und so die Latenz beim Laden von Webseiten für Benutzer verringert.  Webseiten profitieren am meisten von HTTP/2 (im Gegensatz zu Services), da das Protokoll Anforderungen mehrerer Artefakte in einem Aufruf zusammenfasst und so optimiert. Die HTTP/2-Unterstützung wurde zu ASP.NET in .NET Framework 4.6 hinzugefügt. Da Netzwerkfunktionen auf mehreren Ebenen vorhanden sind, waren neue Funktionen in Windows, IIS und ASP.NET erforderlich, um HTTP/2 nutzen zu können. Sie müssen Windows 10 ausführen, um HTTP/2 mit ASP.NET nutzen zu können.

         HTTP/2 wird auch unterstützt und ist standardmäßig für Windows 10-UWP-Apps aktiviert, die die <xref:System.Net.Http.HttpClient?displayProperty=fullName>-API verwenden.

         Es wurde eine neue Methode mit zwei Überladungen, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> und <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, zur <xref:System.Web.HttpResponse>-Klasse hinzugefügt, um eine Möglichkeit zu bieten, um das [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE)-Feature in ASP.NET-Anwendungen zu nutzen.

        > [!NOTE]
        >  Während ASP.NET 5 Unterstützung für HTTP/2 enthält, wurde noch keine Unterstützung für das PUSH PROMISE-Feature hinzugefügt.

         Browser und Webserver (IIS unter Windows) erledigen die gesamte Arbeit. Sie müssen keine umfangreichen Aufgaben für Ihre Benutzer ausführen.

         Die meisten [gängigen Browser unterstützen HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), sodass Ihre Benutzer wahrscheinlich vom HTTP/2-Protokoll profitieren können, sofern Ihr Server dies unterstützt.

    - **Unterstützung für das Tokenbindungsprotokoll**

         Microsoft und Google haben gemeinsam einen neuen Ansatz für die Authentifizierung erarbeitet, das so genannte [Tokenbindungsprotokoll](https://github.com/TokenBinding/Internet-Drafts). Die Prämisse: Authentifizierungstoken (im Browsercache) können von Internetkriminellen gestohlen und verwendet werden, um auf ansonsten sichere Ressourcen (z. B. Bankkonten) zuzugreifen, ohne Ihr Kennwort oder andere geschützte Informationen zu kennen. Das neue Protokoll zielt darauf ab, dieses Problem zu minimieren.

         Das Tokenbindungsprotokoll wird in Windows 10 als Browserfunktion implementiert. ASP.NET-Anwendungen werden in das Protokoll einbezogen, damit die Legitimität von Authentifizierungstoken überprüft werden kann. Die Client- und Serverimplementierungen stellen den durch das Protokoll angegebenen umfassenden Schutz bereit.

    - **Zufällige Zeichenfolgen-Hashalgorithmen**

         Mit .NET Framework 4.5 wurde ein [zufälliger Zeichenfolgen-Hashalgorithmus](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md) eingeführt. Dieser wurde jedoch durch ASP.NET nicht unterstützt, da einige der ASP.NET von einem stabilen Hash abhängig sind. In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] werden nun zufällige Zeichenfolgen-Hashalgorithmen unterstützt. Verwenden Sie zum Aktivieren dieses Features die `aspnet:UseRandomizedStringHashAlgorithm`-Konfigurationseinstellung.

        ```
        <appSettings>
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
        </appSettings>
        ```

- **ADO.NET**

     ADO .NET unterstützt jetzt das in SQL Server 2016 Community Technology Preview 2 (CTP2) verfügbare Feature zum grundsätzlichen Verschlüsseln. Mit der grundsätzlichen Verschlüsselung kann SQL Server Operationen zu verschlüsselten Daten durchführen und das Beste ist, der Verschlüsselungsschlüssel ist bei der Anwendung in der vertrauenswürdigen Umgebung des Kunden abgelegt, nicht auf dem Server. Die grundsätzliche Verschlüsselung sichert Kundendaten so, dass DBAs keinen Zugriff auf Textdaten haben. Die Verschlüsselung und Entschlüsselung von Daten erfolgt transparent auf Treiberebene, dadurch werden die an vorhandenen Anwendungen erforderlichen Änderungen auf ein Mindestmaß reduziert. Weitere Informationen finden Sie unter [Always Encrypted (Datenbankmodul)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) und [Always Encrypted (Cliententwicklung)](/sql/relational-databases/security/encryption/always-encrypted-client-development).

- **64-Bit-JIT-Compiler für verwalteten Code**

     .NET Framework 4.6 umfasst eine neue Version des 64-Bit-JIT-Compilers (ursprünglicher Codename „RyuJIT“). Der neue 64-Bit-Compiler bietet erhebliche Leistungsverbesserungen im Vergleich zum älteren 64-Bit-JIT-Compiler. Der neue 64-Bit-Compiler wird für 64-Bit-Prozesse aktiviert, die zusätzlich zu .NET Framework 4.6 ausgeführt werden. Ihre App wird in einem 64-Bit-Prozess ausgeführt, wenn sie als 64 Bit oder AnyCPU kompiliert ist und auf einem 64-Bit-Betriebssystem ausgeführt wird. Obwohl der Übergang zum neuen Compiler so transparent wie möglich verlief, sind Änderungen im Verhalten möglich. Wir möchten Sie bitten, uns direkt über Probleme zu informieren, die beim Verwenden des neuen JIT-Compilers auftreten. Kontaktieren Sie uns über [Microsoft Connect](http://connect.microsoft.com/), wenn Sie ein Problem feststellen, das möglicherweise mit dem neuen 64-Bit-JIT-Compiler zusammenhängt.

     Der neue 64-Bit-Compiler umfasst zudem Hardware-SIMD-Beschleunigungsfeatures, wenn er mit SIMD-fähigen Typen im <xref:System.Numerics>-Namespace gekoppelt wird, was zu Leistungsverbesserungen führen kann.

- **Verbesserungen am Assemblyladeprogramm**

     Das Assemblyladeprogramm verwendet nun den Arbeitsspeicher effizienter, indem IL-Assemblys entladen werden, nachdem ein entsprechendes NGEN-Image geladen wurde. Durch diese Änderung wird der virtuelle Arbeitsspeicher verringert. Dies ist besonders bei großen 32-Bit-Apps (wie Visual Studio) hilfreich. Zudem wird dadurch physischer Arbeitsspeicher eingespart.

- **Änderungen an Basisklassenbibliotheken**

     Viele neue APIs wurden im Umfeld von [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] hinzugefügt, um wichtige Szenarios zu ermöglichen. Dazu zählen die folgenden Änderungen und Ergänzungen:

    - **IReadOnlyCollection\<T>-Implementierungen**

         Von weiteren Auflistungen wird <xref:System.Collections.Generic.IReadOnlyCollection%601> implementiert, z. B. <xref:System.Collections.Generic.Queue%601> und <xref:System.Collections.Generic.Stack%601>.

    - **CultureInfo.CurrentCulture und CultureInfo.CurrentUICulture**

         Die Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> sind nicht schreibgeschützt und können jetzt gelesen und geschrieben werden. Wenn Sie diesen Eigenschaften ein neues <xref:System.Globalization.CultureInfo>-Objekt zuweisen, ändern sich ebenfalls die aktuelle Threadkultur, die durch die Eigenschaft `Thread.CurrentThread.CurrentCulture` definiert ist, sowie die aktuelle UI-Threadkultur, die durch die `Thread.CurrentThread.CurrentUICulture`-Eigenschaften definiert ist.

    - **Verbesserungen bei der Garbage Collection (GC)**

         Die <xref:System.GC>-Klasse enthält jetzt <xref:System.GC.TryStartNoGCRegion%2A>- und <xref:System.GC.EndNoGCRegion%2A>-Methoden, die es Ihnen ermöglichen, die Garbage Collection während der Ausführung eines kritischen Pfads nicht zuzulassen.

         Eine neue Überladung der <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=fullName>-Methode erlaubt Ihnen die Kontrolle, ob für den kleinen und großen Objektheap eine Komprimierung und ein Sweep ausgeführt werden, oder ob nur ein Sweep erfolgt.

    - **SIMD-fähige Typen**

         Der <xref:System.Numerics>-Namespace enthält jetzt eine Reihe von SIMD-fähigen Typen wie <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> und <xref:System.Numerics.Vector4>.

         Da der neue 64-Bit-JIT-Compiler zudem Hardware-SIMD-Beschleunigungsfeatures enthält, liegen insbesondere erhebliche Leistungsverbesserungen beim Verwenden von SIMD-fähigen Typen mit dem neuen 64-Bit-JIT-Compiler vor.

    - **Kryptografieupdates**

         Die <xref:System.Security.Cryptography?displayProperty=fullName>-API wird aktualisiert, um die [Kryptografie-APIs von Windows CNG](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx) zu unterstützen. Frühere Versionen von .NET Framework basierten vollständig auf einer [früheren Version der Kryptografie-APIs von Windows](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) als Grundlage für die <xref:System.Security.Cryptography?displayProperty=fullName>-Implementierung. Benutzer forderten die Unterstützung der CNG-API, da diese [moderne Kryptografiealgorithmen](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support) unterstützt, die für bestimmte Kategorien von Apps wichtig sind.

         .NET Framework 4.6 umfasst die folgenden neuen Erweiterungen, um die Kryptografie-API von Windows CNG zu unterstützen:

        - Ein Satz von Erweiterungsmethoden für X509-Zertifikate, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` und `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, die nach Möglichkeit anstelle einer CAPI-basierten Implementierung eine CNG-basierte Implementierung zurückgeben. (Für einige Smartcards usw. ist weiterhin CAPI erforderlich, und die APIs verarbeiten den Fallback).

        - Die <xref:System.Security.Cryptography.RSACng?displayProperty=fullName>-Klasse, die eine CNG-Implementierung des RSA-Algorithmus bietet.

        - Erweiterungen an der RSA-API, damit für allgemeine Aktionen keine Umwandlung mehr erforderlich ist. Beispielsweise war für das Verschlüsseln von Daten mithilfe eines <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Objekts Code wie der folgende in vorherigen Versionen von .NET Framework erforderlich.

             [!code-csharp[WhatsNew.Casting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
           [!code-vb[WhatsNew.Casting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

             Code, der die neuen Kryptografie-APIs in .NET Framework 4.6 verwendet, kann wie folgt umgeschrieben werden, um die Umwandlung zu vermeiden.

             [!code-csharp[WhatsNew.Casting#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
           [!code-vb[WhatsNew.Casting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

    - **Unterstützung für das Konvertieren von Datumsangaben und Uhrzeiten zur oder aus der Unix-Zeit**

         Die folgenden neuen Methoden wurden zur <xref:System.DateTimeOffset>-Struktur hinzugefügt, um das Konvertieren von Datums- und Uhrzeitangaben zur oder aus der Unix-Zeit zu unterstützen:

        - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=fullName>

        - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=fullName>

        - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=fullName>

        - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=fullName>

    - **Kompatibilitätsoptionen**

         Die neue <xref:System.AppContext>-Klasse fügt ein neues Kompatibilitätsfeature hinzu, das es Bibliotheksautoren ermöglicht, ihren Benutzern einen einheitlichen Abwahlmechanismus für neue Funktionalitäten bereitzustellen. Sie richtet einen lose gekoppelten Vertrag zwischen den Komponenten ein, um eine Anforderung zur Abwahl zu übermitteln. Diese Möglichkeit ist in der Regel wichtig, wenn vorhandene Funktionalitäten verändert werden. Im Gegensatz dazu existiert bereits eine implizite Auswahloption für neue Funktionalitäten.

         Mit <xref:System.AppContext> definieren Bibliotheken Kompatibilitätsoptionen und machen diese verfügbar, während im Code, der von diesen Bibliotheken abhängig ist, diese Optionen festgelegt werden können, um das Verhalten der Bibliothek zu beeinflussen. Standardmäßig stellen Bibliotheken die neue Funktionalität bereit. Nur wenn die Option festgelegt ist, stellen sie die vorherige Funktionalität bereit.

         Eine Anwendung (oder eine Bibliothek) kann den Wert einer Option deklarieren (hierbei handelt es sich immer um einen <xref:System.Boolean>-Wert), die von einer abhängige Bibliothek definiert wird. Die Option ist immer implizit `false`. Durch Festlegen der Option auf `true` wird diese aktiviert. Durch explizites Festlegen der Option auf `false` wird das neue Verhalten aktiviert.

        ```csharp
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
        ```

         Die Bibliothek muss überprüfen, ob ein Consumer den Wert der Option deklariert hat, und dann entsprechend reagieren.

        ```csharp
        if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow)) 
        {
           // This is the case where the switch value was not set by the application. 
           // The library can choose to get the value of shouldThrow by other means. 
           // If no overrides nor default values are specified, the value should be 'false'. 
           // A false value implies the latest behavior.
        }

           // The library can use the value of shouldThrow to throw exceptions or not.
           if (shouldThrow) 
           {
              // old code
           }
           else {
              // new code
           }
        }

        ```

         Es empfiehlt sich, ein konsistentes Format für Optionen zu verwenden, da es sich hierbei um eine formellen Vertrag handelt, der von einer Bibliothek verfügbar gemacht wird. Das folgende Beispiel zeigt zwei offensichtliche Formate.

        - *Switch*.*namespace*.*switchname*

        - *Switch*.*library*.*switchname*

    - **Änderungen am aufgabenbasierten asynchronen Entwurfsmuster (TAP)**

         Für Apps, die auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ausgerichtet sind, erben die Objekte <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> die Kultur und die Benutzeroberflächenkultur des aufrufenden Threads. Das Verhalten von Apps, die mit früheren Versionen von .NET Framework arbeiten oder auf keine bestimmte Version von .NET Framework ausgelegt sind, ist davon nicht betroffen. Weitere Informationen finden Sie im Abschnitt „Kultur und aufgabenbasierte asynchrone Vorgänge“ im Thema zur <xref:System.Globalization.CultureInfo>-Klasse.

         Die <xref:System.Threading.AsyncLocal%601?displayProperty=fullName>-Klasse ermöglicht Ihnen das Darstellen von Umgebungsdaten, die für eine angegebene asynchrone Ablaufsteuerung wie eine `async`-Methode lokal sind. Sie kann zum threadübergreifenden Beibehalten von Daten verwendet werden. Sie können zudem eine Rückrufmethode definieren, die benachrichtigt wird, sobald sich die Umgebungsdaten ändern, und zwar entweder aufgrund der expliziten Änderung der <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=fullName>-Eigenschaft oder weil der Thread einen Kontextübergang ermittelt hat.

         Drei ergänzende Methoden, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=fullName> und <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=fullName>, wurden zu den aufgabenbasierten asynchronen Mustern (TAP) hinzugefügt, um abgeschlossene Aufgaben in einem bestimmten Zustand zurückzugeben.

         Die <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse unterstützt jetzt die asynchrone Kommunikation mit seinem neuen <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. -Methode.

    - **EventSource unterstützt jetzt das Schreiben in das Ereignisprotokoll**

         Sie können nun die <xref:System.Diagnostics.Tracing.EventSource>-Klasse verwenden, um Verwaltungs- oder betriebliche Nachrichten in das Ereignisprotokoll zu schreiben, und zwar zusätzlich zu vorhandenen auf dem Computer erstellten ETW-Sitzungen. Früher mussten Sie das „Microsoft.Diagnostics.Tracing.EventSource“-NuGet-Paket für diese Funktionalität verwenden. Diese Funktionalität ist nun in .NET Framework 4.6 integriert.

         Sowohl das NuGet-Paket als auch .NET Framework 4.6 wurden mit den folgenden Features aktualisiert:

        - **Dynamische Ereignisse**

             Ermöglichen das „spontane“ Definieren von Ereignissen, und zwar ohne das Erstellen von Ereignismethoden.

        - **Umfangreiche Nutzlasten**

             Ermöglicht, dass speziell attributierte Klassen und Arrays sowie primitive Typen als eine Nutzlast übergeben werden.

        - **Aktivitätsnachverfolgung**

             Löst Start- und Stoppereignisse aus, um Ereignisse zwischen ihnen mit einer ID zu kennzeichnen, die alle aktuell aktiven Aktivitäten darstellt.

         Zur Unterstützung dieser Features wurde die überladene <xref:System.Diagnostics.Tracing.EventSource.Write%2A>-Methode zur <xref:System.Diagnostics.Tracing.EventSource>-Klasse hinzugefügt.

- **Windows Presentation Foundation (WPF)**

    - **HDPI-Verbesserungen**

         Die HDPI-Unterstützung in WPF ist nun besser in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Es wurden Änderungen an der Layoutglättung vorgenommen, um die Instanzen von Clipping in Steuerelementen mit Begrenzungen zu reduzieren. Dieses Feature ist standardmäßig nur dann aktiviert, wenn das <xref:System.Runtime.Versioning.TargetFrameworkAttribute> auf .NET 4.6 festgelegt ist.  Anwendungen, die auf frühere Versionen des Frameworks abzielen, aber auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ausgeführt werden, können das neue Verhalten übernehmen, indem die folgende Zeile zum Abschnitt „[\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)“ der Datei „app.config“ hinzugefügt wird:

        ```
        <AppContextSwitchOverrides
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
        />
        ```

         Sich auf mehrere Monitore erstreckende WPF-Fenster mit unterschiedlichen DPI-Einstellungen (Multi-DPI-Einrichtung) wurden nun vollständig gerendert, und zwar ohne verdunkelte Bereiche. Sie können dieses Verhalten deaktivieren, indem Sie die folgende Zeile zum `<appSettings>`-Abschnitt der Datei „app.config“ hinzufügen, um dieses neue Verhalten zu deaktivieren:

        ```
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>
        ```

         Unterstützung für das automatische Laden des richtigen Cursors, und zwar abhängig davon, ob die DPI-Einstellung zu <xref:System.Windows.Input.Cursor?displayProperty=fullName> hinzugefügt wurde.

    - **Toucheingabe ist besser**

         Über [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) meldet der Kunde, dass das unvorhersehbare Verhalten der Toucheingabe in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] behoben wurde. Der Schwellenwert für das Doppeltippen für Windows Store- und WPF-Anwendungen entspricht nun dem in Windows 8.1 und höher.

    - **Unterstützung für das transparente untergeordnete Fenster**

         WPF in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] unterstützte transparente untergeordnete Fenster in Windows 8.1 und höher. Dadurch können Sie untergeordnete Fenster, die weder viereckig noch transparent sind, in Ihren Fenstern auf oberster Ebene erstellen. Sie können dieses Feature durch Festlegen der <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=fullName>-Eigenschaft auf `true` aktivieren.

- **Windows Communication Foundation (WCF)**

    - **SSL-Unterstützung**

         WCF unterstützt nun SSL Version TLS 1.1 und TLS 1.2 neben SSL 3.0 und TLS 1.0 beim Verwenden von NetTcp mit Transportsicherheit und Clientauthentifizierung. Es ist nun möglich, auszuwählen, welches Protokoll verwendet werden soll, oder ältere und zugleich unsicherere Protokolle zu deaktivieren. Dies kann entweder durch Festlegen der <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A>-Eigenschaft oder durch Hinzufügen von Folgendem zu einer Konfigurationsdatei erreicht werden.

        ```
        <netTcpBinding>
           <binding>
              <security mode= "None|Transport|Message|TransportWithMessageCredential" >
                 <transport clientCredentialType="None|Windows|Certificate"
                            protectionLevel="None|Sign|EncryptAndSign"
                            sslProtocols="Ssl3|Tls1|Tls11|Tls12">
                    </transport>
              </security>
           </binding>
        </netTcpBinding>
        ```

    - **Senden von Nachrichten mithilfe von unterschiedlichen HTTP-Verbindungen**

         WCF ermöglicht Benutzern nun, sicherzustellen, dass bestimmte Nachrichten unter Verwendung von zugrunde liegenden HTTP-Verbindungen gesendet wurden. Hierfür gibt es zwei Möglichkeiten:

        - **Verwenden eines Verbindungsgruppen-Namenspräfix**

             Benutzer können eine Zeichenfolge angeben, die WCF als ein Präfix für den Verbindungsgruppennamen verwendet. Unter Verwendung von unterschiedlichen zugrunde liegenden HTTP-Verbindungen werden zwei Nachrichten mit unterschiedlichen Präfixen gesendet. Sie legen das Präfix durch Hinzufügen eines Schlüssel-Wert-Paars zur <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=fullName>-Eigenschaft der Nachricht fest. Der Schlüssel ist „HttpTransportConnectionGroupNamePrefix“ und der Wert ist das gewünschte Präfix.

        - **Verwenden von unterschiedlichen Kanalfaktoren**

             Benutzer können zudem ein Feature aktivieren, das sicherstellt, dass die mithilfe von anhand unterschiedlicher Kanalfaktoren erstellten Kanälen gesendeten Nachrichten unterschiedliche zugrunde liegende HTTP-Verbindungen verwenden. Zum Aktivieren dieses Features müssen die Benutzer die folgende `appSetting` auf `true` festlegen:

            ```
            <appSettings>
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
            </appSettings>
            ```

- **Windows Workflow Foundation (WWF)**

     Sie können nun die Anzahl der Sekunden angeben, die ein Workflowdienst an einer gestörten Vorgangsanforderung festhält, wenn ein ausstehendes Nicht-Protokoll-Lesezeichen vorliegt, bevor für die Anforderung ein Timeout ausgelöst wird. Ein Nicht-Protokoll-Lesezeichen ist ein Lesezeichen, das nicht mit ausstehenden Receive-Aktivitäten verknüpft ist. Bei einigen Aktivitäten werden Nicht-Protokoll-Lesezeichen in ihrer Implementierung erstellt. Es ist daher ggf. nicht offensichtlich, ob ein Nicht-Protokoll-Lesezeichen vorhanden ist. Dazu zählen der Status und die Auswahl. Wenn Sie über einen Workflowdienst verfügen, der mit einem Statuscomputer implementiert wurde oder eine Auswahlaktivität enthält, verfügen Sie sehr wahrscheinlich über Nicht-Protokoll-Lesezeichen. Sie geben das Intervall an, indem Sie eine Zeile wie die folgende zum `appSettings`-Abschnitt Ihrer „app.config“-Datei hinzufügen:

    ```
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
    ```

     Der Standardwert beträgt 60 Sekunden. Wenn `value` auf „0“ festgelegt ist, werden gestörte Anforderungen sofort mit einem Fehlertext abgelehnt, der wie folgt aussieht:

    ```
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees. 
    ```

     Hierbei handelt es sich um dieselbe Meldung, die Sie empfangen, wenn Sie eine Meldung in Bezug auf einen gestörten Vorgang empfangen und keine Nicht-Protokoll-Lesezeichen vorliegen.

     Wenn der Wert des `FilterResumeTimeoutInSeconds`-Elements nicht null entspricht, liegen keine Nicht-Protokoll-Lesezeichen vor, und das Timeoutintervall läuft ab, wobei beim Vorgang Fehler auftreten und eine Timeoutmeldung angezeigt wird.

- **Transaktionen**

     Sie können die ID für die verteilte Transaktion nun für die Transaktion einbeziehen, die eine Ausnahme verursacht hat, die von der auszulösenden <xref:System.Transactions.TransactionException> abgeleitet wurde. Hierzu müssen Sie den folgenden Schlüssel zum `appSettings`-Abschnitt Ihrer „app.config“-Datei hinzufügen.

    ```
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/> 
    ```

     Der Standardwert ist `false`.

- **Netzwerk**

    - **Socket-Wiederverwendung**

         Windows 10 umfasst einen neuen hochskalierbaren Netzwerkalgorithmus, der eine bessere Verwendung von Computerressourcen ermöglicht, indem lokale Ports für ausgehende TCP-Verbindungen verwendet werden. .NET Framework 4.6 unterstützt den neuen Algorithmus, wodurch .NET-Apps von diesem neuen Verhalten profitieren können. In früheren Windows-Versionen gab es einen Grenzwert für gleichzeitige, künstliche Verbindungen (für gewöhnlich 16.384, die Standardgröße des dynamischen Portbereichs), wodurch die Skalierbarkeit eines Diensts begrenzt werden konnte, indem unter Lastbedingungen eine Portauslastung verursacht werden konnte.

         In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] wurden zwei neue APIs hinzugefügt, um die Portwiederverwendung zu aktivieren, wodurch die 64K-Begrenzung für gleichzeitige Verbindungen effektiv entfernt wurde:

        - Der <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName>-Enumerationswert.

        - Die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName>-Eigenschaft.

         Standardmäßig ist die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName>-Eigenschaft `false`, sofern nicht der `HWRPortReuseOnSocketBind`-Wert des `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319`-Registrierungsschlüssels auf „0x1“ festgelegt ist. Legen Sie zum Aktivieren der lokalen Portwiederverwendung für HTTP-Verbindungen die <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName>-Eigenschaft auf `true` fest. Dadurch verwenden alle ausgehenden TCP-Socketverbindungen von <xref:System.Net.Http.HttpClient> und <xref:System.Net.HttpWebRequest> die neue Windows 10-Socketoption [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), die die lokale Portwiederverwendung ermöglicht.

         Entwickler, die Nur-Socketanwendungen schreiben, können die <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName>-Option beim Aufrufen einer Methode wie <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=fullName> angeben, sodass die ausgehenden Sockets die lokale Ports während der Bindung erneut verwenden.

    - **Unterstützung für internationale Domänennamen und PunyCode**

         Der Klasse <xref:System.Uri> wurde die neue Eigenschaft <xref:System.Uri.IdnHost%2A> hinzugefügt, um internationale Domänennamen und PunyCode besser zu unterstützen.

- **Größenänderungen in Windows Forms-Steuerelementen**

     Dieses Feature wurde in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] erweitert, um die Typen <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> und <xref:System.Windows.Forms.ToolStripSplitButton> und das durch die <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A>-Eigenschaft angegebene Rechteck einzubeziehen, das beim Zeichnen eines <xref:System.Drawing.Design.UITypeEditor> verwendet wird.

     Dies ist ein Opt-in-Feature. Setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element in der Anwendungskonfigurationsdatei (app.config) auf `true`, um dieses Feature zu aktivieren:

    ```
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- **Unterstützung für Codepagecodierungen**

     [!INCLUDE[net_core](../../../includes/net-core-md.md)] unterstützt primär Unicode-Codierungen und bietet standardmäßig eingeschränkte Unterstützung für Codepagecodierungen. Sie können Unterstützung für Codeseitencodierungen, die im .NET Framework zur Verfügung stellen, in .[!INCLUDE[net_core](../../../includes/net-core-md.md)] jedoch nicht unterstützt werden, hinzufügen, indem Sie die Codeseitencodierungen mithilfe der <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=fullName>-Methode registrieren. Weitere Informationen finden Sie unter <xref:System.Text.CodePagesEncodingProvider?displayProperty=fullName>.

- **.NET Native**

     Windows-Apps für Windows 10, die auf [!INCLUDE[net_core](../../../includes/net-core-md.md)] ausgerichtet und in C# oder Visual Basic geschrieben sind, können eine neue Technologie nutzen, die Apps in systemeigenen Code kompiliert statt in IL. Sie erzeugen Apps, die sich durch kürzere Start- und Ausführungszeiten auszeichnen. Weitere Informationen finden Sie unter [Kompilieren von Anwendungen mit .NET Native](../../../docs/framework/net-native/index.md). Eine Übersicht über .NET Native, in der untersucht wird, wie es sich sowohl von der JIT-Kompilierung als auch von NGEN unterscheidet und was dies für Ihren Code bedeutet, finden Sie unter [.NET Native und Kompilierung](../../../docs/framework/net-native/net-native-and-compilation.md).

     Ihre Apps werden beim Kompilieren mit Visual Studio 2015 standardmäßig in systemeigenen Code kompiliert. Weitere Informationen finden Sie unter [Erste Schritte mit .NET Native](../../../docs/framework/net-native/getting-started-with-net-native.md).

     Um das Debuggen von .NET Native-Apps zu unterstützen, wurden der API für nicht verwaltetes Debugging eine Reihe neuer Schnittstellen und Enumerationen hinzugefügt. Weitere Informationen finden Sie im Thema [Debuggen (Referenz zur nicht verwalteten API)](../../../docs/framework/unmanaged-api/debugging/index.md).

- **Open-Source-Pakete von .NET Framework**

     [!INCLUDE[net_core](../../../includes/net-core-md.md)]-Pakete wie das „immutable collections“-Paket, [SIMD APIs](http://go.microsoft.com/fwlink/?LinkID=518639) und Netzwerk-APIs wie diejenigen aus dem <xref:System.Net.Http>-Namespace stehen jetzt als Open Source-Pakete auf [GitHub](https://github.com/) zur Verfügung. Informationen über den Codezugriff finden Sie unter [NetFx auf GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). Weitere Informationen und wie Sie zu diesen Paketen beitragen können, finden Sie unter [.NET Core und Open-Source](../../../docs/framework/get-started/net-core-and-open-source.md), [.NET-Homepage auf GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).

 [Zurück zum Anfang](#introduction)

<a name="v452"></a> 
## <a name="whats-new-in-the-net-framework-452"></a>Neuigkeiten in .NET Framework 4.5.2

- **Neue APIs für ASP.NET-Apps** Mithilfe der neuen Methoden <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=fullName> und <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=fullName> können Sie Antwortheader untersuchen und ändern. Zudem wird Statuscode als Antwort in die Client-App geschrieben. Erwägen Sie die Verwendung dieser Methoden anstelle der Ereignisse <xref:System.Web.HttpApplication.PreSendRequestHeaders> und <xref:System.Web.HttpApplication.PreSendRequestContent>. Diese Methoden sind effizienter und zuverlässiger.

     Mithilfe der <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=fullName>-Methode können Sie kleine Hintergrund-Arbeitsaufgaben planen. ASP.NET überwacht diese Aufgaben und verhindert, dass IIS den Arbeitsprozess abrupt beendet, bevor alle Hintergrund-Arbeitsaufgaben abgeschlossen wurden. Diese Methode kann nicht außerhalb von verwalteten ASP.NET-App-Domänen aufgerufen werden.

     Die neuen Eigenschaften <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=fullName> und <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=fullName> geben boolesche Werte zurück, die angeben, ob die Antwortheader geschrieben wurden. Mit diesen Eigenschaften können Sie sicherstellen, dass API-Aufrufe wie z. B. <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=fullName> (die Ausnahmen auslösen, wenn die Header geschrieben wurden) erfolgreich ausgeführt werden.

- **Größenänderungen in Windows Forms-Steuerelementen** Dieses Feature wurde erweitert. Sie können nun die systemeigene DPI-Einstellung verwenden, um die Größe von Komponenten der folgenden zusätzlichen Steuerelemente anzupassen (z. B. der Dropdownpfeil in Combofeldern):

     <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ToolStripComboBox> <xref:System.Windows.Forms.ToolStripMenuItem> <xref:System.Windows.Forms.Cursor> <xref:System.Windows.Forms.DataGridView <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

     Dies ist ein Opt-in-Feature. Setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element in der Anwendungskonfigurationsdatei (app.config) auf `true`, um dieses Feature zu aktivieren:

    ```
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- **Neues Workflow-Feature** Ein Ressourcen-Manager, der die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>-Methode verwendet (und daher die <xref:System.Transactions.IPromotableSinglePhaseNotification>-Schnittstelle implementiert), kann die neue <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName>-Methode verwenden, um Folgendes anzufordern:

    - Stufen Sie die Transaktion zu einer Microsoft Distributed Transaction Coordinator (MSDTC)-Transaktion herauf.

    - Ersetzen Sie <xref:System.Transactions.IPromotableSinglePhaseNotification> durch eine <xref:System.Transactions.ISinglePhaseNotification>, die eine dauerhafte Eintragung darstellt, die einphasige Commits unterstützt.

     Dies kann innerhalb derselben App-Domäne erfolgen, und erfordert keinen zusätzlichen nicht verwalteten Code für die Interaktion mit MSDTC für die Höherstufung. Die neue Methode kann nur aufgerufen werden, wenn ein ausstehender Aufruf von <xref:System.Transactions?displayProperty=fullName> für die <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote`-Methode vorliegt, der von der heraufstufbaren Eintragung implementiert wird.

- **Profilerstellungsverbesserungen** Die folgenden neuen, nicht verwalteten Profilerstellungs-APIs bieten eine robustere Profilerstellung:

     [COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur](../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) 
     [COR_PRF_HIGH_MONITOR-Enumeration](../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 
     [GetAssemblyReferences-Methode](../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) 
     [GetEventMask2-Methode](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) 
     [SetEventMask2-Methode](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 
     [AddAssemblyReference-Methode](../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

     Frühere `ICorProfiler`-Implementierungen unterstützten Lazy Loading für abhängige Assemblys. Die neue Profilerstellungs-API benötigt abhängige Assemblys, die vom Profiler zum sofortigen Laden eingefügt werden, anstatt nach der vollständigen Initialisierung der App geladen zu werden. Diese Änderung betrifft keine Benutzer der existierenden `ICorProfiler`-APIs.

- **Verbesserungen beim Debugging** Die folgenden neuen, nicht verwalteten Debugging-APIs bieten bessere Profilerintegration. Beim Debuggen von Abbildern haben Sie nun Zugriff auf die vom Profiler eingefügten Metadaten sowie auf lokale Variablen und den von ReJIT-Anfragen des Compilers eingefügten Code.

     [SetWriteableMetadataUpdateMode-Methode](../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) 
     [EnumerateLocalVariablesEx-Methode](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) 
     [GetLocalVariableEx-Methode](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) 
     [GetCodeEx-Methode](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) 
     [GetActiveReJitRequestILCode-Methode](../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md) 
     [GetInstrumentedILMap-Methode](../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- **Änderungen an der Ereignisablaufverfolgung** .NET Framework 4.5.2 unterstützt prozessexterne Ereignisablaufverfolgung für Windows (ETW)-basierte Aktivitätsverfolgung für eine größere Oberfläche. Auf diese Weise können Advanced Power Management (APM)-Hersteller einfache Tools zur Messung der Kosten einzelner threadübergreifender Anfragen und Aktivitäten anbieten.  Diese Ereignisse werden nur ausgelöst, wenn sie von einem ETW-Controller aktiviert wurden. Die Änderungen betreffen daher keinen zuvor geschriebenen ETW-Code oder Code, der mit deaktivierter ETW ausgeführt wird.

- **Höherstufen einer Transaktion mit entsprechender Konvertierung zu einer dauerhaften Eintragung**

     <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> ist eine neue API, die zu .NET Framework 4.5.2 und 4.6 hinzugefügt wurde:

    ```csharp
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                              IPromotableSinglePhaseNotification promotableNotification,
                                              ISinglePhaseNotification enlistmentNotification,
                                              EnlistmentOptions enlistmentOptions)
    ```

     Die Methode kann von einer Eintragung verwendet werden, die zuvor von <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> als Antwort auf die <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName>-Methode erstellt wurde. Sie fragt `System.Transactions` ab, um die Transaktion zu einer MSDTC-Transaktion heraufzustufen und um die heraufstufbare Eintragung zu einer dauerhaften Eintragung zu „konvertieren“. Nach dem erfolgreichen Abschluss dieser Methode wird nicht mehr durch `System.Transactions` auf die <xref:System.Transactions.IPromotableSinglePhaseNotification>-Schnittstelle verwiesen und alle zukünftigen Benachrichtigungen gelangen zur bereitgestellten <xref:System.Transactions.ISinglePhaseNotification>-Schnittstelle. Die entsprechende Eintrag muss als eine dauerhafte Eintragung fungieren und die Transaktionsprotokollierung und -wiederherstellung unterstützen. Weitere Informationen finden Sie unter <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>. Darüber hinaus muss die Eintragung <xref:System.Transactions.ISinglePhaseNotification> unterstützen.  Diese Methode kann *nur* während der Verarbeitung eines <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName>-Aufrufs aufgerufen werden. Wenn dies nicht der Fall ist, wird eine <xref:System.Transactions.TransactionException>-Ausnahme ausgelöst.

 [Zurück zum Anfang](#introduction)

<a name="v451"></a> 
## <a name="whats-new-in-the-net-framework-451"></a>Neuigkeiten in .NET Framework 4.5.1
 **Updates für April 2014**:

- [Visual Studio 2013 Update 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) enthält Updates für die Vorlagen der portablen Klassenbibliothek, um die folgenden Szenarien zu unterstützen:

    - Sie können die Windows-Runtime APIs in portablen Bibliotheken einsetzen, die Windows 8.1, Windows Phone 8.1 und Windows Phone Silverlight 8.1 als Ziel verwenden.

    - Sie können XAML (Windows.UI.XAML-Typen) in portablen Bibliotheken einsetzen, wenn Sie Windows 8.1 oder Windows Phone 8.1 als Ziel verwenden. Die folgenden XAML-Vorlagen werden unterstützt: Leere Seite, Ressourcenverzeichnis, Steuerelement mit Vorlagen und Benutzersteuerelement.

    - Sie können eine portable Komponente für Windows-Runtime (.winmd-Datei) für den Einsatz in Store-Apps erstellen, die Windows 8.1 und Windows Phone 8.1 als Ziel verwenden.

    - Sie können eine Windows Store- oder Windows Phone Store-Klassenbibliothek wie eine portable Klassenbibliothek neu zuweisen.

     Weitere Informationen zu diesen Änderungen finden Sie unter [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

- Der .NET Framework-Inhaltssatz enthält nun Dokumentation für [!INCLUDE[net_native](../../../includes/net-native-md.md)], eine Vorkompilierungstechnologie für die Erstellung und Bereitstellung von Windows-Apps. [!INCLUDE[net_native](../../../includes/net-native-md.md)] kompiliert Ihre Apps direkt in systemeigenen Code anstelle einer Intermediate Language (IL) und erzielt dadurch eine bessere Leistung. Details hierzu finden Sie unter [Kompilieren von Anwendungen mit .NET Native](../../../docs/framework/net-native/index.md).

- Die [.NET Framework-Verweisquelle](http://referencesource.microsoft.com/) bietet ein neues Browsererlebnis und erweiterte Funktionen. Sie können den Quellcode von .NET Framework online durchsuchen, die [Referenz herunterladen](http://referencesource.microsoft.com/download.html), um diese offline anzuzeigen, und den Quellcode (inklusive Patches und Updates) beim Debuggen schrittweise durchlaufen. Weitere Informationen finden Sie im Blogeintrag [A new look for .NET Reference Source](https://blogs.msdn.microsoft.com/dotnet/2014/02/24/a-new-look-for-net-reference-source/).

 .NET Framework 4.5.1 enthält die folgenden neuen Kernfunktionen und -optimierungen:

- Automatische Bindungsumleitung für Assemblys. Ab [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] können beim Kompilieren einer App, deren Ziel [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] ist, Bindungsumleitungen zur App-Konfigurationsdatei hinzugefügt werden, wenn die App oder ihre Komponenten sich auf mehrere Versionen derselben Assembly beziehen. Sie können diese Funktion auch für Projekte aktivieren, die frühere Versionen von .NET Framework als Ziel haben. Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).

- Fähigkeit, Diagnoseninformationen zu erfassen, um Entwicklern zu helfen, die Leistung von Server- und Cloud-Anwendungen zu verbessern. Weitere Informationen finden Sie unter den Methoden <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> und <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> in der <xref:System.Diagnostics.Tracing.EventSource>-Klasse.

- Fähigkeit, während einer Garbage Collection den großen Objektheap (Large Object Heap, LOH) explizit zu komprimieren. Weitere Informationen finden Sie unter der <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName>-Eigenschaft.

- Zusätzliche Leistungsverbesserungen wie ASP.NET-App-Unterbrechung, Multikern-JIT-Verbesserungen und schnellere App-Starts nach einem .NET Framework-Update. Ausführliche Informationen finden Sie in der [.NET Framework 4.5.1-Ankündigung](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/) und im Blogbeitrag [ASP.NET App Suspend](https://blogs.msdn.microsoft.com/dotnet/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting/).

 Verbesserungen für Windows Forms-Anwendungen:

- Größenänderungen in Windows Forms-Steuerelementen. Sie können die systemeigene DPI-Einstellung verwenden, um die Größe von Komponenten von Steuerelementen anzupassen (z. B. die Symbole in einem Eigenschaftenraster), indem Sie diese Funktion über einen Eintrag in der Anwendungskonfigurationsdatei (app.config) für Ihre App aktivieren. Dieses Feature wird zurzeit für die folgenden Windows Forms-Steuerelemente unterstützt:

     <xref:System.Windows.Forms.PropertyGrid> <xref:System.Windows.Forms.TreeView> Einige Aspekte von <xref:System.Windows.Forms.DataGridView> (weitere unterstützte Steuerelemente finden Sie unter [Neue Features in 4.5.2](#v452))

     Fügen Sie ein neues \<appSettings>-Element zur Konfigurationsdatei (app.config) hinzu und setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element auf `true`, um dieses Feature zu aktivieren:

    ```
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

 Zu Verbesserungen beim Debuggen Ihrer .NET Framework-Apps in [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] zählen:

- Rückgabewerte im Visual Studio-Debugger. Wenn Sie eine verwaltete App in [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] debuggen, werden Rückgabetypen und -werte für Methoden im Fenster "Auto" angezeigt. Diese Informationen sind für Desktop-, Windows Store- und Windows Phone-Apps verfügbar. Weitere Informationen finden Sie unter [Überprüfen von Rückgabewerten der Methodenaufrufe](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) in der MSDN Library.

- "Bearbeiten und Fortfahren" für 64-Bit-Apps. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] unterstützt die Funktion "Bearbeiten und Fortfahren" für verwaltete 64-Bit-Apps für Desktops, Windows Store und Windows Phone. Die vorhandenen Einschränkungen bleiben für 32-Bit- und 64-Bit-Apps wirksam (siehe den letzten Abschnitt des Artikels [Unterstützte Codeänderungen (C#)](/visualstudio/debugger/supported-code-changes-csharp)).

- Async-bewusstes Debuggen. Um das Debuggen asynchroner Apps in [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] zu vereinfachen, wird der Infrastrukturcode, der von Compilern zur Unterstützung asynchronen Programmierens bereitgestellt wird, in der Aufrufliste ausgeblendet. Ebenfalls erfolgt dort eine Verkettung mit logisch übergeordneten Rahmen, sodass der logischen Programmausführung übersichtlicher gefolgt werden kann. Ein Aufgabenfenster ersetzt das Fenster "Parallele Aufgaben" und zeigt Aufgaben an, die sich auf einen bestimmten Haltepunkt beziehen. Außerdem werden alle anderen Aufgaben angezeigt, die momentan aktiv oder in der App geplant sind. Informationen zu diesem Feature finden Sie im Abschnitt „Async-bewusstes Debuggen“ in der [.NET Framework 4.5.1-Ankündigung](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/).

- Bessere Ausnahmeunterstützung für Windows-Runtime-Komponenten. In [!INCLUDE[win81](../../../includes/win81-md.md)] behalten Ausnahmen, die sich aus Windows Store-Apps ergeben, Informationen zum Fehler, der die Ausnahme ausgelöst hat, sogar über Sprachgrenzen bei. Informationen zu diesem Feature finden Sie im Abschnitt „Windows Store-App-Entwicklung“ in der [.NET Framework 4.5.1-Ankündigung](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/). 

 Ab [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] können Sie zusätzlich das [Managed Profile Guided Optimization Tool (Mpgo.exe)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) verwenden, um sowohl [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps als auch Desktop-Apps zu optimieren.

 Informationen zu neuen Funktionen in ASP.NET 4.5.1 finden Sie unter [ASP.NET 4.5.1 und Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) auf der ASP.NET-Website.

 [Zurück zum Anfang](#introduction)

<a name="core"></a> 
## <a name="whats-new-in-the-net-framework-45"></a>Neuigkeiten in .NET Framework 4.5

### <a name="core-new-features-and-improvements"></a>Wichtige neue Features und Verbesserungen

- Weniger Systemneustarts durch Erkennen und Schließen von .NET Framework 4-Anwendungen bei der Bereitstellung. Siehe [Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen](../../../docs/framework/deployment/reducing-system-restarts.md).

- Unterstützung von mehr als 2 Gigabyte (GB) großen Arrays auf 64-Bit-Plattformen. Sie können die Funktion in der Anwendungskonfiguration aktivieren. Siehe das [\<gcAllowVeryLargeObjects>-Element](../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), das auch andere Einschränkungen zur Objekt- und Arraygröße auflistet.

- Bessere Leistung durch Garbage Collection im Hintergrund für Server. Wenn Sie die Garbage Collection auf dem Server in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] verwenden, wird die Garbage Collection im Hintergrund automatisch aktiviert. Siehe im Abschnitt „Garbage Collection auf dem Server im Hintergrund“ des Themas [Grundlagen der Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md).

- Just-In-Time (JIT)-Kompilierung im Hintergrund zur Verbesserung der Anwendungsleistung, die optional auf Mehrkernprozessoren verfügbar ist. Siehe <xref:System.Runtime.ProfileOptimization>.

- Festlegen der Zeit, die das Modul für reguläre Ausdrücke zum Auflösen eines regulären Ausdrucks bis zum Timeout benötigen darf. Weitere Informationen finden Sie unter der <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=fullName>-Eigenschaft.

- Definieren der Standardkultur für eine Anwendungsdomäne. Weitere Informationen finden Sie unter der <xref:System.Globalization.CultureInfo>-Klasse.

- Konsolenunterstützung für Unicode-Codierung (UTF-16). Weitere Informationen finden Sie unter der <xref:System.Console>-Klasse.

- Unterstützung für die Versionierung kulturabhängiger Zeichenfolgenreihenfolgen und -vergleichsdaten. Weitere Informationen finden Sie unter der <xref:System.Globalization.SortVersion>-Klasse.

- Bessere Leistung beim Abrufen von Ressourcen. Siehe [Verpacken und Bereitstellen von Ressourcen](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).

- Verbesserte ZIP-Komprimierung zur Reduzierung der Größe einer komprimierten Datei. Weitere Informationen finden Sie unter dem <xref:System.IO.Compression?displayProperty=fullName>-Namespace.

- Anpassen von Reflektionskontext zum Überschreiben des Standardreflektionsverhaltens mit der <xref:System.Reflection.Context.CustomReflectionContext>-Klasse.

- Unterstützung der Version 2008 des IDNA-Standards (Internationalized Domain Names in Applications) beim Verwenden der <xref:System.Globalization.IdnMapping?displayProperty=fullName>-Klasse in [!INCLUDE[win8](../../../includes/win8-md.md)].

- Delegieren des Zeichenfolgenvergleichs an das Betriebssystem, wobei Unicode 6.0 implementiert wird, wenn .NET Framework in [!INCLUDE[win8](../../../includes/win8-md.md)] verwendet wird. Bei Ausführung auf anderen Plattformen verwendet .NET Framework eigene Zeichenfolgenvergleichsdaten, wobei Unicode 5.x. implementiert wird. Weitere Informationen finden Sie unter der <xref:System.String>-Klasse und im Abschnitt „Hinweise“ der <xref:System.Globalization.SortVersion>-Klasse.

- Berechnen der Hashcodes für Zeichenfolgen pro Anwendungsdomäne. Siehe [\<UseRandomizedStringHashAlgorithm>-Element](../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).

- Unterstützung der Typreflektion zwischen <xref:System.Type>- und <xref:System.Reflection.TypeInfo>-Klassen. Siehe [Reflektion in .NET Framework für Windows Store-Apps](../../../docs/framework/reflection-and-codedom/reflection-for-windows-store-apps.md).

### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)
 In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] bietet das Managed Extensibility Framework (MEF) folgende neue Funktionen:

- Unterstützung von generischen Typen.

- Konventionsbasiertes Programmiermodell zum Erstellen von Teilen auf Grundlage von Namenskonventionen anstelle von Attributen.

- Mehrere Bereiche.

- Eine Teilmenge von MEF, die Sie verwenden können, wenn Sie Apps im [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] erstellen. Diese Teilmenge steht als [herunterladbares Paket](http://go.microsoft.com/fwlink/?LinkId=256238) in der NuGet Gallery zur Verfügung. Öffnen Sie zum Installieren des Pakets das Projekt in Visual Studio, wählen Sie im Menü **Projekt** die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Composition`-Paket.

 Weitere Informationen finden Sie unter [Übersicht über das Managed Extensibility Framework](../../../docs/framework/mef/index.md).

### <a name="asynchronous-file-operations"></a>Asynchrone Dateivorgänge
 In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wurden neue asynchrone Funktionen zu den Programmiersprachen C# und Visual Basic hinzugefügt. Diese Funktionen ergänzen ein aufgabenbasiertes Modell zum Ausführen von asynchronen Vorgängen. Verwenden Sie dieses neue Modell mithilfe der asynchronen Methoden in den E/A-Klassen. Siehe [Asynchrone Datei-E/A](../../../docs/standard/io/asynchronous-file-i-o.md).

<a name="tools"></a> 
### <a name="tools"></a>Tools
 In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] können Sie mit dem Resource File Generator-Tool (Resgen.exe) aus einer RESOURCES-Datei, die in einer .NET Framework-Assembly eingebettet ist, eine RESW-Datei für [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps erstellen. Weitere Informationen finden Sie unter [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).

 Mit Managed Profile Guided Optimization (Mpgo.exe) können Sie die Anwendungsstartzeit, die Arbeitsspeicherauslastung (Workingsetgröße) und den Durchsatz verbessern, indem Sie die Assemblys systemeigener Abbilder optimieren. Das Befehlszeilentool generiert Profildaten für Anwendungsassemblys systemeigener Abbilder. Siehe [Mpgo.exe (verwaltetes, profilgesteuertes Optimierungstool)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md). Ab [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] können Sie Mpgo.exe verwenden, um [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps und Desktop-Apps zu optimieren.

<a name="parallel"></a> 
### <a name="parallel-computing"></a>Parallele Computervorgänge
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] stellt mehrere neue Funktionen und Verbesserungen für parallele Berechnung bereit. Dazu gehören leistungsfähigere, erweiterte Steuerungsmöglichkeiten, verbesserte Unterstützung für asynchrone Programmierung, eine neue Datenflussbibliothek und verbesserte Unterstützung für paralleles Debuggen und Leistungsanalyse. Siehe den Eintrag zu den [Neuerungen hinsichtlich der Parallelität in .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) im Blog zur parallelen Programmierung mit .NET.

<a name="web"></a> 
### <a name="web"></a>Web
 In ASP.NET 4.5 und 4.5.1 wurden die Modellbindung für Webformulare, WebSocket-Unterstützung, asynchrone Handler, Leistungserweiterungen und viele weitere Funktionen hinzugefügt. Weitere Informationen finden Sie in den folgenden Ressourcen:

- [ASP.NET 4.5 und Visual Studio 2012](http://msdn.microsoft.com/library/ac9bb7f6-f094-4af7-bad0-acf49a5dbc55) in der MSDN Library.

- [ASP.NET 4.5.1 und Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) auf der ASP.NET-Website.

<a name="networking"></a> 
### <a name="networking"></a>Netzwerk
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] stellt eine neue Programmierschnittstelle für HTTP-Anwendungen bereit. Weitere Informationen finden Sie unter den neuen Namespaces <xref:System.Net.Http?displayProperty=fullName> und <xref:System.Net.Http.Headers?displayProperty=fullName>.

 Unterstützt wird jetzt auch eine neue Programmierschnittstelle, um eine WebSocket-Verbindung mithilfe der vorhandenen <xref:System.Net.HttpListener>-Klasse und verknüpften Klassen anzunehmen und mit dieser zu interagieren. Weitere Informationen finden Sie unter dem neuen <xref:System.Net.WebSockets>-Namespace und der <xref:System.Net.HttpListener>-Klasse.

 Darüber hinaus enthält [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] folgende Netzwerkfunktionsverbesserungen:

- RFC-kompatible URI-Unterstützung. Weitere Informationen finden Sie in der <xref:System.Uri>-Klasse und verknüpften Klassen.

- Unterstützung für IDN (Internationalized Domain Name)-Analysen. Weitere Informationen finden Sie in der <xref:System.Uri>-Klasse und verknüpften Klassen.

- Unterstützung für E-Mail-Adressen-Internationalisierung (EAI). Weitere Informationen finden Sie unter dem <xref:System.Net.Mail>-Namespace.

- Verbesserte IPv6-Unterstützung. Weitere Informationen finden Sie unter dem <xref:System.Net.NetworkInformation>-Namespace.

- Dual-Modus-Socket-Unterstützung. Weitere Informationen finden Sie unter den Klassen <xref:System.Net.Sockets.Socket> und <xref:System.Net.Sockets.TcpListener>.

<a name="client"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 In der Version [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] wurde Windows Presentation Foundation (WPF) in vielen Bereichen überarbeitet und verbessert. Dazu gehören:

- Das neue <xref:System.Windows.Controls.Ribbon.Ribbon>-Steuerelement, mit dem Sie eine Menüband-Benutzeroberfläche implementieren können, die eine Symbolleiste für den Schnellzugriff, ein Anwendungsmenü und Registerkarten hostet.

- Die neue <xref:System.ComponentModel.INotifyDataErrorInfo>-Schnittstelle, die die synchrone und asynchrone Datenüberprüfung unterstützt.

- Neue Features für die Klassen <xref:System.Windows.Controls.VirtualizingPanel> und <xref:System.Windows.Threading.Dispatcher>.

- Verbesserte Leistung beim Anzeigen großer Datengruppierungen sowie durch den Zugriff auf Auflistungen in Nicht-UI-Threads.

- Datenbindung an statische Eigenschaften, Datenbindung an benutzerdefinierte Typen, die die <xref:System.Reflection.ICustomTypeProvider>-Schnittstelle implementieren, und Abrufen von Datenbindungsinformationen von einem Bindungsausdruck.

- Neupositionierung von Daten bei Wertänderung (Live-Strukturierung).

- Überprüfen einer möglicherweise getrennten Verbindung des Datenkontexts für einen Elementcontainer.

- Festlegen der Zeit, die zwischen Eigenschaftenänderungen und Datenquellenupdates verstreichen soll.

- Verbesserte Unterstützung für das Implementieren schwacher Ereignismuster. Zudem können Ereignisse jetzt Markuperweiterungen akzeptieren.

<a name="windows_communication_foundation"></a> 
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)
 Um das Schreiben und Verwalten von Windows Communication Foundation (WCF)-Anwendungen zu erleichtern, wurden in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] folgende Funktionen hinzugefügt:

- Vereinfachung von generierten Konfigurationsdateien.

- Unterstützung für Contract-First-Entwicklung.

- Leichteres Konfigurieren des ASP.NET-Kompatibilitätsmodus.

- Änderungen in den standardmäßigen Transporteigenschaftswerten, um die Wahrscheinlichkeit zu reduzieren, dass Sie sie festlegen müssen.

- Updates der <xref:System.Xml.XmlDictionaryReaderQuotas>-Klasse, um die Wahrscheinlichkeit zu reduzieren, dass Sie Kontingente für XML-Wörterbuch-Reader manuell konfigurieren müssen.

- Validierung von WCF-Konfigurationsdateien von Visual Studio als Teil des Buildprozesses, sodass Sie Konfigurationsfehler erkennen können, bevor Sie die Anwendung ausführen.

- Neue Unterstützung für asynchrones Streaming.

- Neue HTTPS-Protokollzuordnung zur leichteren Bereitstellung eines Endpunkts über HTTPS mit IIS (Internetinformationsdienste).

- Generieren von Metadaten in einem einzelnen WSDL-Dokument durch Anfügen von `?singleWSDL` an die Dienst-URL.

- Websockets-Unterstützung für echte bidirektionale Kommunikation über die Ports 80 und 443 mit TCP-transportähnlichen Leistungsmerkmalen.

- Unterstützung für das Konfigurieren von Diensten im Code.

- XML-Editor-QuickInfos.

- Unterstützung der <xref:System.ServiceModel.ChannelFactory>-Zwischenspeicherung.

- Unterstützung für die Komprimierung binärer Encoder.

- Unterstützung für einen UDP-Transport, mit dem Entwickler "Fire and Forget" (Auslösen und Vergessen)-Messaging-Dienste schreiben können. Ein Client sendet eine Nachricht an einen Dienst und erwartet von diesem keine Antwort.

- Unterstützung mehrerer Authentifizierungsmodi auf einem einzelnen WCF-Endpunkt beim Verwenden von HTTP-Transport und -Transportsicherheit.

- Unterstützung für WCF-Dienste, die internationale Domänennamen (IDNs) verwenden.

 Weitere Informationen finden Sie unter [Neues in Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).

<a name="windows_workflow_foundation"></a> 
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)
 In der Version [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] gibt es jetzt viele neue Funktionen in Windows Workflow Foundation (WF), darunter:

- Zustandsautomatworkflows, die zunächst als Teil von .NET Framework 4.0.1 ([.NET Framework 4 Platform-Update 1](http://go.microsoft.com/fwlink/?LinkID=215092)) eingeführt wurden. Dieses Update umfasste mehrere neue Klassen und Aktivitäten, sodass Entwickler Zustandsautomatworkflows erstellen konnten. Diese Klassen und Aktivitäten wurden für [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] aktualisiert und umfassen nun Folgendes:

    - Festlegen von Haltepunkten für Zustände.

    - Kopieren und Einfügen von Übergängen im Workflow Designer.

    - Designerunterstützung für das Erstellen von freigegebenen Triggerübergängen.

    - Aktivitäten zum Erstellen von Zustandsautomatworkflows, einschließlich: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> und <xref:System.Activities.Statements.Transition>.

- Verbesserte Workflow Designer-Funktionen, z. B.:

    - Verbesserte Workflowsuchfunktionen in Visual Studio, einschließlich **Schnellsuche** und **In Dateien suchen**.

    - Automatisches Erstellen einer Sequenzaktivität, wenn eine zweite untergeordnete Aktivität zu einer Containeraktivität hinzugefügt wird, und Einschließen beider Aktivitäten in die Sequenzaktivität.

    - Schwenk-Unterstützung zur Änderung des sichtbaren Teils eines Workflows ohne die Verwendung von Bildlaufleisten.

    - Die neue Ansicht **Dokumentgliederung**, die die Gliederungsansicht der Workflowkomponenten in einer Baumstruktur anzeigt und die Auswahl einer Komponente in der Ansicht **Dokumentgliederung** ermöglicht.

    - Hinzufügen von Anmerkungen zu Aktivitäten.

    - Definieren und Verarbeiten von Aktivitätsdelegaten mit dem Workflow Designer.

    - Automatisches Verbinden und Einfügen für Aktivitäten und Übergänge in Zustandsautomaten- und Flussdiagrammworkflows.

- Speichern der Ansichtszustandsinformationen für einen Workflow in einem einzelnen Element in der XAML-Datei, sodass Sie die Ansichtszustandsinformationen leicht finden und bearbeiten können.

- Eine NoPersistScope-Containeraktivität, damit untergeordnete Aktivitäten nicht beibehalten werden.

- Unterstützung von C#-Ausdrücken:

    - Visual Basic-Workflowprojekte verwenden Visual Basic-Ausdrücke, und C#-Workflowprojekte verwenden C#-Ausdrücke.

    - C#-Workflowprojekte, die in Visual Studio 2010 erstellt wurden und Visual Basic-Ausdrücke verwenden, sind mit C#-Workflowprojekten, die C#-Ausdrücke verwenden, kompatibel.

- Versionsverwaltungserweiterungen:

    - Die neue <xref:System.Activities.WorkflowIdentity>-Klasse, die eine Zuordnung zwischen einer beibehaltenen Workflowinstanz und ihrer Workflowdefinition bietet.

    - Parallele Ausführung mehrerer Workflowversionen auf demselben Host, einschließlich <xref:System.ServiceModel.Activities.WorkflowServiceHost>.

    - Die Änderbarkeit der Definition einer beibehaltenen Workflowinstanz im Rahmen eines dynamischen Updates.

- Contract-First-Workflowdienstentwicklung, die das automatische Generieren von Aktivitäten zur Übereinstimmung mit einem vorhandenen Dienstvertrag unterstützt.

 Weitere Informationen finden Sie unter [Neues in Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).

<a name="tailored"></a> 
### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]
 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps werden für bestimmte Formularfaktoren entworfen und nutzen die Leistungsfähigkeit des Windows-Betriebssystems. Eine Teilmenge von [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] oder 4.5.1 kann mithilfe von C# oder Visual Basic zum Erstellen von [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Apps in Windows verwendet werden. Diese Teilmenge wird [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] genannt und in einer [Übersicht](http://go.microsoft.com/fwlink/?LinkId=228491) im Windows Developer Center erläutert.

<a name="portable"></a> 
### <a name="portable-class-libraries"></a>Portable Klassenbibliotheken
 Mit dem Projekt "Portable Klassenbibliothek" in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] (und Folgeversionen) können Sie verwaltete Assemblys, die auf mehreren .NET Framework-Plattformen ausgeführt werden können, schreiben und erstellen. Mit einem "Portable Klassenbibliothek"-Projekt wählen Sie die Zielplattformen (wie Windows Phone und [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]). Die verfügbaren Typen und Member im Projekt werden automatisch auf die allgemeinen Typen und Member dieser Plattformen beschränkt. Weitere Informationen finden Sie in der Dokumentation zur [Portablen Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

## <a name="see-also"></a>Siehe auch
 [.NET Framework und Out-of-Band-Releases](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Neues in Visual Studio 2017](/visualstudio/ide/whats-new-in-visual-studio)   
 [ASP.NET](/aspnet)   
 [Neues in Visual C++](/cpp/what-s-new-for-visual-cpp-in-visual-studio) 
