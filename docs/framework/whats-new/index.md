---
title: Neuigkeiten in .NET Framework | Microsoft-Dokumentation
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework-4.6
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
translationtype: Human Translation
ms.sourcegitcommit: 9460c8b6ca8db927af4064e3567eca34c1bf5c91
ms.openlocfilehash: 56bf5905fc9e4c676e2cf681c9135fddf88e5c89
ms.lasthandoff: 04/08/2017

---
# <a name="what39s-new-in-the-net-framework"></a>Neuigkeiten in .NET Framework
<a name="introduction"></a> Dieser Artikel beschreibt wichtige Funktionen und Änderungen in den folgenden Versionen von .NET Framework:  
  
 [.NET Framework 4.7](#v47)   
 [.NET Framework 4.6.2](#v462)   
 [.NET Framework 4.6.1](#v461)   
 [.NET 2015 und .NET Framework 4.6](#v46)   
 [.NET Framework 4.5.2](#v452)   
 [.NET Framework 4.5.1](#v451)   
 [.NET Framework 4.5](#core)  
  
 Dieser Artikel enthält keine umfassenden Informationen zu jeder neuen Funktion und unterliegt möglichen Änderungen. Allgemeine Informationen zu .NET Framework finden Sie unter [Erste Schritte](http://msdn.microsoft.com/library/c693fd34-88fe-4d90-b332-19eeadf3b7e7). Informationen zu unterstützten Plattformen finden Sie unter [Systemanforderungen](~/docs/framework/get-started/system-requirements.md). Downloadlinks und Installationsanweisungen finden Sie im [Installationshandbuch](../../../docs/framework/install/guide-for-developers.md).  
  
> [!NOTE]
>  Das .NET Framework-Team veröffentlicht zusätzlich mit NuGet Funktionen außer der Reihe, um die Plattformunterstützung zu erweitern und neue Funktionen einzuführen, z. B. unveränderliche Auflistungen und SIMD-fähige Vektortypen. Weitere Informationen finden Sie unter [Zusätzliche Klassenbibliotheken und APIs](http://msdn.microsoft.com/library/cf2d9006-b631-4e5d-81cd-20aab78c60f1) und [.NET Framework und Out-of-Band-Releases](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). Lassen Sie eine [vollständige Liste von NuGet-Paketen](http://blogs.msdn.com/b/dotnet/p/nugetpackages.aspx) für .NET Framework anzeigen, oder abonnieren Sie [unseren Feed](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).  
  
<a name="v47"></a>   
## <a name="introducing-the-net-framework-47"></a>Einführung in .NET Framework 4.7  
 .NET Framework 4.7 baut auf .NET Framework 4.6, 4.6.1 und 4.6.2 auf und umfasst zahlreiche Fehlerkorrekturen und neue Funktionen in einem gewohnt stabilen Produkt.  

> [!NOTE]
> .NET Framework 4.7 ist auf allen Windows 10 Creators Update-Systemen vorinstalliert. Es ist nicht für das Herunterladen und Installieren unter anderen Windows-Betriebssystemen verfügbar.  

## <a name="whats-new-in-the-net-framework-47"></a>Neuerungen in .NET Framework 4.7

.NET Framework 4.7 umfasst neue Features in den folgenden Bereichen:

- [Kernspeicher](#Core47)
- [Netzwerk](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

<a name="Core47" />
### <a name="core"></a>Kernspeicher ###

.NET Framework 4.7 verbessert die Serialisierung durch <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Verbesserte Funktionalität mit Elliptic Curve Cryptography (ECC)***

In .NET Framework 4.7 wurden den Klassen <xref:System.Security.Cryptography.ECDsa> und <xref:System.Security.Cryptography.ECDiffieHellman> `ImportParameters(ECParameters)`-Methoden hinzugefügt, um einem Objekt zu ermöglichen, einen bereits eingerichteten Schlüssel darzustellen. Eine `ExportParameters(Boolean)`-Methode wurde auch zum Exportieren des Schlüssels unter Verwendung expliziter Kurvenparameter hinzugefügt.

.NET Framework 4.7 unterstützt nun auch zusätzliche Kurven (einschließlich der Brainpool-Kurvengruppe) und bietet vordefinierte Definitionen zur Erleichterung der Erstellung mithilfe der Factorymethoden <xref:System.Security.Cryptography.ECDsa.Create%2A> und <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

Auf GitHub finden Sie ein [Beispiel der kryptografischen Verbesserungen in .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e).

**Bessere Unterstützung für Steuerzeichen durch DataContractJsonSerializer**

In .NET Framework 4.7 erfolgt die Serialisierung von Steuerzeichen durch <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> entsprechend dem Standard ECMAScript 6. Dieses Verhalten wird standardmäßig für Anwendungen aktiviert, die auf .NET Framework 4.7 ausgerichtet sind, und ist ein optionales Feature für Anwendungen, die unter .NET Framework 4.7 ausgeführt werden, jedoch auf eine frühere Version von .NET Framework ausgerichtet sind. Weitere Informationen finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />
### <a name="networking"></a>Netzwerk ###

.NET Framework-4.7 bietet nun die folgenden netzwerkbezogenen Features:

**Standardmäßig Betriebssystemunterstützung für TLS-Protokolle***

Der TLS-Stapel, der von <xref:System.Net.Security.SslStream?displayProperty=fullName> und vorgelagerten Komponenten im Stapel wie z.B. HTTP, FTP und SMTP verwendet wird, ermöglicht Entwicklern, die vom Betriebssystem unterstützten TLS-Standardprotokolle zu verwenden. Entwickler müssen eine TLS-Version nicht länger vordefinieren.

<a name="ASP-NET47" />
### <a name="aspnet"></a>ASP.NET ###

In .NET Framework 4.7 bietet ASP.NET die folgenden neuen Features:

**Erweiterbarkeit des Objektcaches**

Ab .NET Framework 4.7 bietet ASP.NET eine neue Gruppe von APIs, die es Entwicklern ermöglichen, die ASP.NET- Standardimplementierungen für das Zwischenspeichern von Objekten im Arbeitsspeicher und dessen Überwachung zu ersetzen. Entwickler können jetzt die drei folgenden Komponenten ersetzen, wenn die ASP.NET-Implementierung nicht geeignet ist:

- **Objektcachespeicher**. Mithilfe des neuen Abschnitts für die Konfiguration von Cacheanbietern können Entwickler neue Implementierungen eines Objektcaches für eine ASP.NET-Anwendung einbinden, indem die neue **ICacheStoreProvider**-Schnittstelle verwendet wird.
 
- **Speicherüberwachung**. Der Standardspeichermonitor in ASP.NET benachrichtigt Anwendungen, sobald sie sich dem für den Prozess konfigurierten Grenzwert für private Bytes nähern oder der insgesamt verfügbare physische Arbeitsspeicher knapp wird. Bei Annäherung an diese Grenzwerte werden Benachrichtigungen ausgelöst. Bei einigen Anwendungen werden Benachrichtigungen erst ausgelöst, sobald die konfigurierten Grenzwerte schon fast erreicht sind, sodass keine sinnvolle Reaktion möglich ist. Entwickler können jetzt mithilfe der <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=fullName>-Eigenschaft eigene Speichermonitore schreiben.

- **Reaktionen bei Erreichen des Speichergrenzwerts**. Standardmäßig versucht ASP.NET, den Objektcache zu trimmen und regelmäßig <xref:System.GC.Collect%2A?displayProperty=fullName> aufzurufen, wenn der Prozessgrenzwert für private Bereiche fast erreicht ist. Für einige Anwendungen ist die Häufigkeit der Aufrufe von <xref:System.GC.Collect%2A?displayProperty=fullName> oder die Menge des Caches, der getrimmt wird, ineffizient. Entwickler können jetzt das Standardverhalten ersetzen oder ergänzen, indem für den Speichermonitor der Anwendung **IObserver**-Implementierungen abonniert werden.

<a name="wcf47" />
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF) ###

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
- Verbesserte Zuverlässigkeit von Serialisierungsvorgängen beim Aufrufen der [FormatterServices.GetSerializableMembers](assetId:///System.Runtime.Serialization.FormatterServices.GetSerializableMembers(System.Type??qualifyHint=True&autoUpgrade=False)-Methode.
- Verbesserte Zuverlässigkeit beim Entfernen eines Waiters durch Aufrufen der **ChannelSynchronizer.RemoveWaiter**-Methode.  

<a name="wf47" />
### <a name="windows-forms"></a>Windows Forms ###

In .NET Framework 4.7 bietet Windows Forms eine bessere Unterstützung für Monitore mit hohem DPI-Wert.

**Unterstützung hoher DPI-Werte**

Beginnend mit auf .NET Framework 4.7 ausgerichteten Anwendungen unterstützt .NET Framework für Windows Forms-Anwendungen hohe und dynamische DPI-Werte. Durch die Unterstützung hoher DPI-Werte werden das Layout und die Darstellung von Formularen und Steuerelementen auf Monitoren mit hohen DPI-Einstellungen verbessert. Dynamische DPI-Werte ermöglichen das Ändern von Layout und Darstellung von Formularen und Steuerelementen, wenn der Benutzer die DPI-Einstellung oder den Skalierungsfaktor der Anzeige einer ausgeführten Anwendung ändert.

Die Unterstützung hoher DPI-Werte ist ein optionales Feature, das Sie durch Festlegen des Abschnitts [\<System.Windows.Forms.ConfigurationSection>](Windows%20Forms%20Configuration%20Section.md) in der Anwendungskonfigurationsdatei konfigurieren können. Weitere Informationen zum Hinzufügen der Unterstützung hoher und dynamischer DPI-Werte zu Ihrer Windows Forms-Anwendung finden Sie unter [Unterstützung hoher DPI-Werte in Windows Forms](High%20DPI%20Support%20In%20Windows%20Forms.md).  

<a name="WPF47"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

In .NET Framework 4.7 gibt es für WPF die folgenden Verbesserungen:

**Unterstützung für Touch-/Tablettstiftstapel basierend auf Windows-WM_POINTER-Nachrichten**

Sie haben nun die Möglichkeit, einen auf [-Windows-Nachrichten](https://msdn.microsoft.com/library/windows/desktop/hh454903(v=vs.85).aspx) basierenden Touch-/Tablettstiftstapel anstelle der Windows Ink Services Plattform (WISP) zu verwenden. Dies ist ein optionales Feature in .NET Framework. Weitere Informationen finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](Retargeting%20Changes%20in%20the%20.NET%20Framework%204.7.md).

**Neue Implementierung für Druck-APIs von WPF**

Die Druck-APIs von WPF in der [System.Printing.PrintQueue](assetId:///T:System.Printing.PrintQueue?qualifyHint=True&autoUpgrade=True)-Klasse rufen die Windows-API [PrintDocumentPackage](https://msdn.microsoft.com/library/windows/desktop/hh448418(v=vs.85).aspx) anstelle der veralteten [XPS-Druck-API](https://msdn.microsoft.com/library/windows/desktop/ff686814(v=vs.85).aspx) auf. Die Auswirkung dieser Änderung auf die Anwendungskompatibilität finden Sie unter [Änderungen der Neuzuweisungen in .NET Framework 4.7](Retargeting%20Changes%20in%20the%20.NET%20Framework%204.7.md). 

<a name="v462"></a>   
## <a name="whats-new-in-the-net-framework-462"></a>Neuigkeiten in .NET Framework 4.6.2  
.NET Framework 4.6.2 umfasst neue Features in den folgenden Bereichen:  
  
-   [ASP.NET](#ASPNET462)  
  
-   [Zeichenkategorien](#Strings)  
  
-   [Kryptografie](#Crypto462)  
  
-   [SQLClient](#SQLClient)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF462)  
  
-   [Windows Workflow Foundation (WF)](#WF462)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Konvertieren von Windows Forms und WPF-Apps in UWP-Apps](#UWPConvert)  
  
-   [Verbesserungen beim Debugging](#Debug462)  
  
 Eine Liste der neuen APIs, die .NET Framework 4.6.2 hinzugefügt wurden, finden unter [API-Änderungen für .NET Framework 4.6.2 auf GitHub](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md). Eine Liste der Verbesserungen von Features und Fehlerkorrekturen in .NET Framework 4.6.2 finden Sie unter [API-Änderungen für .NET Framework 4.6.2 auf GitHub](http://go.microsoft.com/fwlink/?LinkId=708778).  Weitere Informationen finden Sie unter der [Ankündigung von .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) im .NET-Blog.  
  
<a name="ASPNET462"></a>   
### <a name="aspnet"></a>ASP.NET  
 In .NET Framework 4.6.2 bietet ASP.NET die folgenden Verbesserungen:  
  
 **Verbesserte Unterstützung lokalisierter Fehlermeldungen in Validierungssteuerelementen für Datenanmerkungen**  
 Mit Validierungssteuerelementen für Datenanmerkungen können Sie eine Überprüfung durchführen, indem Sie mindestens ein Attribut einer Klasseneigenschaft hinzufügen. Das Element [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True) des Attributs definiert den Text der Fehlermeldung, falls die Überprüfung fehlschlägt. Ab .NET Framework 4.6.2 ist es einfach, mit ASP.NET Fehlermeldungen zu lokalisieren. Fehlermeldungen werden lokalisiert, wenn:  
  
1.  Das [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True)-Attribut wird im Überprüfungsattribut bereitgestellt.  
  
2.  Die Ressourcendatei im Ordner „App_LocalResources“ gespeichert ist.  
  
3.  Der Name der lokalisierten Ressourcendatei ist folgendermaßen aufgebaut: `DataAnnotation.Localization.{`*Name*`}.resx`, wobei *Name *einen Kulturnamen im Format* Sprachcode*`-`*Länder-/Regionscode* oder *Sprachcode* darstellt.  
  
4.  Der Schlüsselname der Ressource ist die Zeichenfolge, die dem Attribut [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True) zugewiesen ist, und deren Wert ist die lokalisierte Fehlermeldung.  
  
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
   \<Required(ErrorMessage = "The rating must be between 1 and 10.")>  
   \<Display(Name = "Your Rating")>  
   Public Property Rating As Integer = 1  
End Class  
  
```  
  
 Sie können dann eine Ressourcendatei erstellen, DataAnnotation.Localization.fr.resx, deren Schlüssel die Zeichenfolge der Fehlermeldung und ihr Wert die lokalisierte Fehlermeldung ist. Die Datei muss sich im Ordner `App.LocalResources` befinden. Das folgende Beispiel enthält den Schlüssel und seinen Wert in einer lokalisierten Fehlermeldung (Französisch, fr):  
  
|Name|Wert|  
|----------|-----------|  
|Die Bewertung muss zwischen 1 und 10 liegen.|La note doit être comprise entre 1 et 10.|  
  
 Diese Datei kann dann  
  
 Darüber hinaus ist die Lokalisierung der Datenanmerkung erweiterbar. Entwickler können ihren eigenen Anbieter für die zu lokalisierenden Zeichenfolgen in einer Ressourcendatei verwenden, indem sie die [IStringLocalizerProvider](assetId:///T:System.Web.Globalization.IStringLocalizerProvider?qualifyHint=False&autoUpgrade=True)-Schnittstelle implementieren, um Lokalisierungszeichenfolgen an einem anderen Speicherort zu speichern, jedoch nicht in einer Ressourcendatei.  
  
 **Async-Unterstützung für Sitzungszustands-Schlüsselspeicheranbieter**  
 ASP.NET erlaubt nun, dass Methoden, die eine Aufgabe zurückgeben, zusammen mit dem Anbieter für die Speicherung von Daten aus der Variable „Sitzungszustand“ verwendet werden können. Dadurch stehen ASP .NET-Apps die Vorteile zur Verfügung, die async in Sachen Skalierbarkeit bietet. Für die Unterstützung asynchroner Vorgänge mit Sitzungszustandsspeicher-Anbietern enthält ASP.NET eine neue Schnittstelle namens [System.Web.SessionState.ISessionStateModule](assetId:///T:System.Web.SessionState.ISessionStateModule?qualifyHint=True&autoUpgrade=True). Diese Schnittstelle erbt von [IHttpModule](assetId:///T:System.Web.IHttpModule?qualifyHint=False&autoUpgrade=True) und erlaubt Entwicklern, ihr eigenes Sitzungszustandsmodul und asynchrone Sitzungsspeicheranbieter zu implementieren. Die Schnittstelle wird wie folgt definiert:  
  
```csharp  
  
public interface ISessionStateModule : IHttpModule {  
    void ReleaseSessionState(HttpContext context);  
    Task ReleaseSessionStateAsync(HttpContext context);  
}  
  
```  
  
 Darüber hinaus enthält die [SessionStateUtility](assetId:///T:System.Web.SessionState.SessionStateUtility?qualifyHint=False&autoUpgrade=True)-Klasse die beiden neuen Methoden [IsSessionStateReadOnly](assetId:///M:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly(System.Web.HttpContext)?qualifyHint=False&autoUpgrade=True) und [IsSessionStateRequired](assetId:///M:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired(System.Web.HttpContext)?qualifyHint=False&autoUpgrade=True), die verwendet werden können, um asynchrone Vorgänge zu unterstützen.  
  
 **Async-Unterstützung für Ausgabecacheanbieter**  
 Ab .NET Framework 4.6.2 können Methoden, die Tasks zurückgeben, mit Ausgabecacheanbietern verwendet werden, um die Vorteile der Skalierbarkeit der Asynchronität zu bieten.  Anbieter, die diese Methoden bereitstellen, verringern die Anzahl blockierter Threads auf einem Webserver und verbessern die Skalierbarkeit eines ASP.NET-Diensts.  
  
 Die folgenden APIs wurden hinzugefügt, um asynchrone Ausgabecacheanbieter zu unterstützen:  
  
-   Die [System.Web.Caching.OutputCacheProviderAsync](assetId:///T:System.Web.Caching.OutputCacheProviderAsync?qualifyHint=True&autoUpgrade=True)-Klasse, die von [System.Web.Caching.OutputCacheProvider](assetId:///T:System.Web.Caching.OutputCacheProvider?qualifyHint=True&autoUpgrade=True) erbt und es Entwicklern gestattet, einen asynchronen Ausgabecacheanbieter zu implementieren.  
  
-   Die [OutputCacheUtility](assetId:///T:System.Web.Caching.OutputCacheUtility?qualifyHint=False&autoUpgrade=True)-Klasse, die Hilfsmethoden zum Konfigurieren des Ausgabecaches bereitstellt.  
  
-   18 neue Methoden in der [System.Web.HttpCachePolicy](assetId:///T:System.Web.HttpCachePolicy?qualifyHint=True&autoUpgrade=True)-Klasse. Dazu gehören [GetCacheability](assetId:///M:System.Web.HttpCachePolicy.GetCacheability?qualifyHint=False&autoUpgrade=True), [GetCacheExtensions](assetId:///M:System.Web.HttpCachePolicy.GetCacheExtensions?qualifyHint=False&autoUpgrade=True), [GetETag](assetId:///M:System.Web.HttpCachePolicy.GetETag?qualifyHint=False&autoUpgrade=True), [GetETagFromFileDependencies](assetId:///M:System.Web.HttpCachePolicy.GetETagFromFileDependencies?qualifyHint=False&autoUpgrade=True), [GetMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetMaxAge?qualifyHint=False&autoUpgrade=True), [GetMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetMaxAge?qualifyHint=False&autoUpgrade=True), [GetNoStore](assetId:///M:System.Web.HttpCachePolicy.GetNoStore?qualifyHint=False&autoUpgrade=True), [GetNoTransforms](assetId:///M:System.Web.HttpCachePolicy.GetNoTransforms?qualifyHint=False&autoUpgrade=True), [GetOmitVaryStar](assetId:///M:System.Web.HttpCachePolicy.GetOmitVaryStar?qualifyHint=False&autoUpgrade=True), [GetProxyMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetProxyMaxAge?qualifyHint=False&autoUpgrade=True), [GetRevalidation](assetId:///M:System.Web.HttpCachePolicy.GetRevalidation?qualifyHint=False&autoUpgrade=True), [GetUtcLastModified](assetId:///M:System.Web.HttpCachePolicy.GetUtcLastModified?qualifyHint=False&autoUpgrade=True), [GetVaryByCustom](assetId:///M:System.Web.HttpCachePolicy.GetVaryByCustom?qualifyHint=False&autoUpgrade=True), [HasSlidingExpiration](assetId:///M:System.Web.HttpCachePolicy.HasSlidingExpiration?qualifyHint=False&autoUpgrade=True) und [IsValidUntilExpires](assetId:///M:System.Web.HttpCachePolicy.IsValidUntilExpires?qualifyHint=False&autoUpgrade=True).  
  
-   2 neue Methoden in der [System.Web.HttpCacheVaryByContentEncodings](assetId:///T:System.Web.HttpCacheVaryByContentEncodings?qualifyHint=True&autoUpgrade=True)-Klasse: [GetContentEncodings](assetId:///M:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings?qualifyHint=False&autoUpgrade=True) und [SetContentEncodings](assetId:///M:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   2 neue Methoden in der [System.Web.HttpCacheVaryByHeaders](assetId:///T:System.Web.HttpCacheVaryByHeaders?qualifyHint=True&autoUpgrade=True)-Klasse: [GetHeaders](assetId:///M:System.Web.HttpCacheVaryByHeaders.GetHeaders?qualifyHint=False&autoUpgrade=True) und [SetHeaders](assetId:///M:System.Web.HttpCacheVaryByHeaders.SetHeaders(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   2 neue Methoden in der [System.Web.HttpCacheVaryByParams](assetId:///T:System.Web.HttpCacheVaryByParams?qualifyHint=True&autoUpgrade=True)-Klasse: [GetParams](assetId:///M:System.Web.HttpCacheVaryByParams.GetParams?qualifyHint=False&autoUpgrade=True) und [SetParams](assetId:///M:System.Web.HttpCacheVaryByParams.SetParams(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   In der [System.Web.Caching.AggregateCacheDependency](assetId:///T:System.Web.Caching.AggregateCacheDependency?qualifyHint=True&autoUpgrade=True)-Klasse die [GetFileDependencies](assetId:///M:System.Web.Caching.AggregateCacheDependency.GetFileDependencies?qualifyHint=False&autoUpgrade=True)-Methode.  
  
-   In [CacheDependency](assetId:///T:System.Web.Caching.CacheDependency?qualifyHint=False&autoUpgrade=True) die [GetFileDependencies](assetId:///M:System.Web.Caching.CacheDependency.GetFileDependencies?qualifyHint=False&autoUpgrade=True)-Methode.  
  
<a name="Strings"></a>   
### <a name="character-categories"></a>Zeichenkategorien  
 Zeichen in .NET Framework 4.6.2 werden basierend auf dem [Unicode-Standard, Version 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) klassifiziert. In .NET Framework 4.6 und .NET Framework 4.6.1 werden Zeichen basierend auf den Zeichenkategorien von Unicode 6.3 klassifiziert.  
  
 Die Unterstützung von Unicode 8.0 ist beschränkt auf die Klassifizierung von Zeichen durch die [CharUnicodeInfo](assetId:///T:System.Globalization.CharUnicodeInfo?qualifyHint=False&autoUpgrade=True)-Klasse und auf Typen und Methoden, die darauf basieren. Dazu gehören die [StringInfo](assetId:///T:System.Globalization.StringInfo?qualifyHint=False&autoUpgrade=True)-Klasse, die überladene [Char.GetUnicodeCategory](assetId:///M:System.Char.GetUnicodeCategory(System.Char)?qualifyHint=True&autoUpgrade=True)-Methode und die [Zeichenklassen](../Topic/Character%20Classes%20in%20Regular%20Expressions.md), die vom .NET Framework-Modul für reguläre Ausdrücke erkannt werden.  Der Vergleich und die Sortierung von Zeichen und Zeichenfolgen sind von dieser Änderung nicht betroffen und beruhen weiterhin auf dem zugrunde liegenden Betriebssystem oder auf Windows 7-Systemen auf Zeichendaten, die vom .NET Framework bereitgestellt wurden.  
  
 Änderungen in Zeichenkategorien von Unicode 6.0 bis 7.0 Unicode finden Sie unter [Unicode Standard, Version 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) auf der Website des Unicode-Konsortiums. Änderungen von Unicode 7.0 bis 8.0 Unicode finden Sie unter [Unicode Standard, Version 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) auf der Website des Unicode-Konsortiums.  
  
<a name="Crypto462"></a>   
### <a name="cryptography"></a>Kryptografie  
 **Unterstützung von X 509-Zertifikaten, die FIPS 186-3 DSA enthalten**  
 .NET Framework 4.6.2 unterstützt DSA X509-Zertifikate (Digital Signature Algorithm), deren Schlüssel den FIPS 186-2-Grenzwert von 1024 Bits überschreiten.  
  
 Zusätzlich zur Unterstützung der höheren Schlüsselgrößen von FIPS 186-3 erlaubt .NET Framework 4.6.2 die Berechnung von Signaturen mit der SHA-2-Familie von Hashalgorithmen (SHA256, SHA384 und SHA512). Die Unterstützung von FIPS 186-3 wird von der neuen [System.Security.Cryptography.DSACng](assetId:///T:System.Security.Cryptography.DSACng?qualifyHint=True&autoUpgrade=True)-Klasse bereitgestellt.  
  
 Gemäß der aktuellen Änderungen an der [RSA](assetId:///T:System.Security.Cryptography.RSA?qualifyHint=False&autoUpgrade=True)-Klasse im .NET Framework 4.6 und an der [ECDsa](assetId:///T:System.Security.Cryptography.ECDsa?qualifyHint=False&autoUpgrade=True)-Klasse im .NET Framework 4.6.1, verfügt die abstrakte Basisklasse [DSA](assetId:///T:System.Security.Cryptography.DSA?qualifyHint=False&autoUpgrade=True) in .NET Framework 4.6.2 über zusätzliche Methoden, um Aufrufern die Verwendung dieser Funktion ohne Umwandlung zu erlauben. Sie können die Erweiterungsmethode [DSACertificateExtensions.GetDSAPrivateKey](assetId:///M:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?qualifyHint=True&autoUpgrade=True) verwenden, um Daten zu signieren (siehe das folgende Beispiel).  
  
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
  
 Sie können auch die Erweiterungsmethode [DSACertificateExtensions.GetDSAPublicKey](assetId:///M:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?qualifyHint=True&autoUpgrade=True) aufrufen, um signierte Daten zu überprüfen (siehe das folgende Beispiel).  
  
```csharp  
  
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)  
{  
    using (DSA dsa = cert.GetDSAPublicKey())  
    {  
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);  
    }  
}  
  
```  
  
```  
  
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean  
    Using dsa As DSA = cert.GetDSAPublicKey()  
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)  
    End Using  
End Function  
  
```  
  
 **Verbesserte Übersichtlichkeit für Eingaben in die Schlüsselableitungsfunktions-Routinen für den Diffie-Hellman-Schlüsselaustausch**  
 In.NET Framework 3.5 wurde die Unterstützung der Elliptic Curve Diffie-Hellman-Schlüsselübereinstimmung mit drei verschiedenen Schlüsselableitungsfunktions-Routinen (KDF) hinzugefügt. Die Eingaben in die Routinen und auch die Routinen selbst wurden mithilfe von Eigenschaften für das [ECDiffieHellmanCng](assetId:///T:System.Security.Cryptography.ECDiffieHellmanCng?qualifyHint=False&autoUpgrade=True)-Objekt konfiguriert. Da jedoch nicht jede Routine jede Eingabeeigenschaft liest, sorgte dies bisher bei Entwicklern für reichlich Verwirrungspotenzial.  
  
 Um darauf in .NET Framework 4.6.2 zu reagieren, wurden die folgenden drei Methoden zur [ECDiffieHellman](assetId:///T:System.Security.Cryptography.ECDiffieHellman?qualifyHint=False&autoUpgrade=True)-Basisklasse hinzugefügt, um diese KDF-Routinen und deren Eingaben eindeutiger darzustellen:  
  
|Die ECDiffieHellman-Methode|Beschreibung|  
|----------------------------|-----------------|  
|[DeriveKeyFromHash(ECDiffieHellmanPublicKey, HashAlgorithmName, Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Security.Cryptography.HashAlgorithmName,System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Leitet Schlüsselmaterial mithilfe der Formel ab<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> wobei *x* das berechnete Ergebnis des EC Diffie-Hellman-Algorithmus ist.|  
|[DeriveKeyFromHmac(ECDiffieHellmanPublicKey, HashAlgorithmName, Byte\[\], Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Security.Cryptography.HashAlgorithmName,System.Byte[],System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Leitet Schlüsselmaterial mithilfe der Formel ab<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> wobei *x* das berechnete Ergebnis des EC Diffie-Hellman-Algorithmus ist.|  
|[DeriveKeyTls(ECDiffieHellmanPublicKey, Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Leitet Schlüsselmaterial mit dem Ableitungsalgorithmus der TLS-Pseudozufallsfunktion (pseudo-random function; PRF) ab.|  
  
 **Unterstützung der symmetrischen Verschlüsselung persistenter Schlüssel**  
 Die Windows-Kryptografiebibliothek (CNG) hat Unterstützung für die Speicherung persistenter symmetrischer Schlüssel und für die Verwendung von in der Hardware gespeicherter symmetrischer Schlüssel bereitgestellt. .NET Framework 4.6.2 ermöglicht Entwicklern, diese Funktion zu verwenden.  Da das Konzept des Schlüsselnamens und des Schlüsselanbieters implementierungsspezifisch ist, erfordert die Nutzung dieser Funktion die Verwendung des Konstruktors der konkreten Implementierungstypen anstatt der bevorzugten Herangehensweise des Unternehmens (z.B. durch aufrufen von `Aes.Create`).  
  
 Die Unterstützung der symmetrischen Verschlüsselung persistenter Schlüssel ist für die Algorithmen AES ([AesCng](assetId:///T:System.Security.Cryptography.AesCng?qualifyHint=False&autoUpgrade=True)) und 3DES ([TripleDESCng](assetId:///T:System.Security.Cryptography.TripleDESCng?qualifyHint=False&autoUpgrade=True)) verfügbar. Zum Beispiel:  
  
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
 .NET Framework 4.6.2 fügt Unterstützung für die [SignedXml](assetId:///T:System.Security.Cryptography.Xml.SignedXml?qualifyHint=False&autoUpgrade=True)-Klasse für die Signaturmethoden RSA-SHA256, RSA-SHA384 und RSA-SHA512 PKCS#1 und für die Referenzdigestalgorithmen SHA256, SHA384 sowie SHA512 hinzu.  
  
 Die URI-Konstanten werden alle für [SignedXml](xref:System.Security.Cryptography.Xml.SignedXml?qualifyHint=False&autoUpgrade=True) verfügbar gemacht:  
  
|SignedXml-Feld|Konstante|  
|---------------------|--------------|  
|[XmlDsigSHA256Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmlenc#sha256"|  
|[XmlDsigRSASHA256Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|  
|[XmlDsigSHA384Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#sha384"|  
|[XmlDsigRSASHA384Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|  
|[XmlDsigSHA512Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmlenc#sha512"|  
|[XmlDsigRSASHA512Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|  
  
 Alle Programme, die einen benutzerdefinierten [SignatureDescription](assetId:///T:System.Security.Cryptography.SignatureDescription?qualifyHint=False&autoUpgrade=True)-Handler in [CryptoConfig](assetId:///T:System.Security.Cryptography.CryptoConfig?qualifyHint=False&autoUpgrade=True) registriert haben, um Unterstützung für diese Algorithmen hinzuzufügen, funktionieren weiterhin wie gewohnt. Da nun jedoch Plattformstandards existieren, ist die [CryptoConfig](assetId:///T:System.Security.Cryptography.CryptoConfig?qualifyHint=False&autoUpgrade=True)-Registrierung nicht mehr notwendig.  
  
<a name="SQLClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 Der .NET Framework-Datenanbieter für SQL Server ([System.Data.SqlClient](assetId:///N:System.Data.SqlClient?qualifyHint=True&autoUpgrade=True)) enthält in .NET Framework 4.6.2 die folgenden neuen Features:  
  
 **Verbindungspooling und Timeouts mit Azure SQL-Datenbanken**  
 Wenn das Verbindungspooling aktiviert ist und ein Timeoutfehler oder ein anderer Anmeldefehler auftritt, wird eine Ausnahme zwischengespeichert sowie die zwischengespeicherte Ausnahme wird für jeden nachfolgenden Verbindungsversuch für die nächsten 5 Sekunden bis zu einer Minute.  Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../Topic/SQL%20Server%20Connection%20Pooling%20\(ADO.NET\).md).  
  
 Dieses Verhalten ist bei einer Verbindung zu Azure SQL-Datenbanken unerwünscht, da Verbindungsversuche mit flüchtigen Fehlern fehlschlagen können, die normalerweise schnell wiederhergestellt werden. Das Sperrfristverhalten des Verbindungspools wird entfernt, wenn die Verbindungsversuche zu Azure SQL-Datenbanken fehlschlagen, damit erneute Verbindungsversuche leichter erfolgen können.  
  
 Mit dem Hinzufügen des neuen `PoolBlockingPeriod`-Schlüsselworts können Sie die Sperrfrist auswählen, die für Ihre App am besten geeignet ist. Mögliche Werte:  
  
 `Auto`  
 Die Sperrfrist des Verbindungspools für eine Anwendung, die eine Verbindung mit einer Azure SQL-Datenbank herstellt, ist deaktiviert, und die Sperrfrist des Verbindungspools für eine Anwendung, die eine Verbindung mit einem anderen SQL-Server herstellt, ist aktiviert. Dies ist der Standardwert. Wenn der Serverendpunktname eine der folgenden Endungen besitzt, werden sie als Azure SQL-Datenbanken bezeichnet:  
  
-   .database.windows.net  
  
-   .database.chinacloudapi.cn  
  
-   .database.usgovcloudapi.net  
  
-   .database.cloudapi.de  
  
 `AlwaysBlock`  
 Die Sperrfrist des Verbindungspools ist immer aktiviert.  
  
 `NeverBlock`  
 Die Sperrfrist des Verbindungspools ist immer deaktiviert.  
  
 **Verbesserungen für Always Encrypted**  
 SQLClient führt zwei Verbesserungen für Always Encrypted ein:  
  
-   Verschlüsselungsmetadaten für Abfrageparameter werden nun zwischengespeichert, um die Leistung von parametrisierten Abfragen von verschlüsselten Datenbankspalten zu verbessert. Mit der auf `true` (Standardwert) festgelegten [SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled](assetId:///P:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled?qualifyHint=True&autoUpgrade=True)-Eigenschaft ruft der Client, wenn dieselbe Abfrage mehrmals aufgerufen wird, Parametermetadaten von Server nur einmal ab.  
  
-   Spaltenverschlüsselungsschlüssel-Einträge im Schlüsselcache werden nun nach einem konfigurierbaren Zeitintervall entfernt, das mithilfe der [SqlConnection.ColumnEncryptionKeyCacheTtl](assetId:///P:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl?qualifyHint=True&autoUpgrade=True)-Eigenschaft festgelegt wird.  
  
<a name="WCF"></a>   
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 In .NET Framework 4.6.2 wurde Windows Communication Foundation in den folgenden Bereichen erweitert:  
  
 **Unterstützung der WCF-Transportsicherheit für Zertifikate, die mithilfe der CNG gespeichert wurden**  
 Die WCF-Transportsicherheit unterstützt Zertifikate, die mithilfe der Windows-Kryptografiebibliothek (CNG) gespeichert wurden. Diese Unterstützung ist in .NET Framework 4.6.2 auf die Verwendung von Zertifikaten mit einem öffentlichen Schlüssel beschränkt, der über einen Exponent mit einer Länge von nicht mehr als 32 Bit verfügt. Wenn eine Anwendung auf .NET Framework 4.6.2 ausgerichtet ist, ist dieses Feature standardmäßig aktiviert.  
  
 Für Anwendungen, die auf .NET Framework 4.6.1 und früher ausgerichtet sind, aber in .NET Framework 4.6.2 oder höher ausgeführt werden, kann dieses Feature aktiviert werden, indem die folgende Zeile dem Abschnitt [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) der Datei „app.config“ oder „web.config“ hinzugefügt wird.  
  
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
 Kunden können eine Anwendungskonfigurationseinstellung verwenden, um zu bestimmen, ob die [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True)-Klasse mehrere Anpassungsregeln für eine Zeitzone unterstützt. Dies ist ein Opt-in-Feature. Fügen Sie die folgende Einstellung der Datei app.config hinzu, um sie zu aktivieren:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />  
</runtime>  
  
```  
  
 Wenn dieses Feature aktiviert ist, verwendet ein [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True)-Objekt den [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True)-Typ anstelle des [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True)-Typs zum Deserialisieren von Datums- und Zeitdaten. [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) unterstützt mehrere Anpassungsregeln, die es ermöglichen, mit veralteten Zeitzonendaten zu arbeiten. [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True) unterstützt dies nicht.  
  
 Weitere Informationen zur [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True)-Struktur und zu Zeitzonenanpassungen finden Sie unter [Übersicht über Zeitzonen](../Topic/Time%20Zone%20Overview.md).  
  
 **Beibehaltung einer UTC-Zeit bei der Serialisierung und Deserialisierung mit der XmlSerializer-Klasse**  
 Wenn die [XmlSerializer](assetId:///T:System.Xml.Serialization.XmlSerializer?qualifyHint=False&autoUpgrade=True)-Klasse zum Serialisieren eines UTC-Werts des Typs [DateTime](assetId:///T:System.DateTime?qualifyHint=False&autoUpgrade=True) verwendet wird, erstellt sie normalerweise eine serialisierte Zeitzeichenfolge, die das Datum und die Uhrzeit beibehält, jedoch davon ausgeht, dass die Zeit die Ortszeit ist.  Wenn Sie beispielsweise ein UTC-Datum und eine UTC-Uhrzeit instanziieren, indem Sie den folgenden Code aufrufen:  
  
```csharp  
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);  
```  
  
```vb  
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)  
```  
  
 ist das Ergebnis für ein System, das acht Stunden hinter der Zeitzone UTC ist, die serialisierten Zeit-Zeichenfolge „03:00:00.0000000-08:00“ .  Serialisierte Werte sind zudem immer als lokale Datums- und Uhrzeitwerte deserialisiert.  
  
 Sie können eine Anwendungskonfigurationseinstellung verwenden, um zu bestimmen, ob die [XmlSerializer](assetId:///T:System.Xml.Serialization.XmlSerializer?qualifyHint=False&autoUpgrade=True)-Klasse die UTC-Zeitzoneninformation beibehält, wenn sie die [DateTime](assetId:///T:System.DateTime?qualifyHint=False&autoUpgrade=True)-Werte serialisiert und deserialisiert:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides   
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />  
</runtime>  
  
```  
  
 Wenn dieses Feature aktiviert ist, verwendet ein [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True)-Objekt den [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True)-Typ anstelle des [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True)-Typs zum Deserialisieren von Datums- und Zeitdaten. [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) unterstützt mehrere Anpassungsregeln, die es ermöglichen, mit veralteten Zeitzonendaten zu arbeiten. [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True) unterstützt dies nicht.  
  
 Weitere Informationen zur [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True)-Struktur und zu Zeitzonenanpassungen finden Sie unter [Übersicht über Zeitzonen](../Topic/Time%20Zone%20Overview.md).  
  
 **NetNamedPipeBinding höchste Übereinstimmung**  
 WCF bietet eine neue App-Einstellung, die für Clientanwendungen festgelegt werden kann, um sicherzustellen, dass diese immer eine Verbindung zu dem Dienst herstellen, der an dem URI lauscht, der die höchste Übereinstimmung zu dem aufweist, den die Anwendungen anfordern. Wenn diese App-Einstellung auf `false` (Standard) festgelegt ist, ist es für Clients möglich, [NetNamedPipeBinding](assetId:///T:System.ServiceModel.NetNamedPipeBinding?qualifyHint=False&autoUpgrade=True) zu verwenden, um zu versuchen, eine Verbindung zu einem Dienst herzustellen, der an einem URI lauscht, der eine Teilzeichenfolge des angeforderten URI darstellt.  
  
 Angenommen, ein Client versucht, eine Verbindung zu einem Dienst herzustellen, der an `net.pipe://localhost/Service1` lauscht, aber ein anderer Dienst auf dem Computer, der mit Administratorrechten ausgeführt wird, lauscht an `net.pipe://localhost`. Der Client würde versuchen, mit dieser App-Einstellung, die auf `false` festgelegt ist, eine Verbindung zu dem falschen Dienst herzustellen. Nach dem Festlegen der App-Einstellung auf `true`, wird der Client stets eine Verbindung zu den passendsten Dienst herstellen.  
  
> [!NOTE]
>  Clients, die [NetNamedPipeBinding](assetId:///T:System.ServiceModel.NetNamedPipeBinding?qualifyHint=False&autoUpgrade=True) verwenden, suchen Dienste, die auf der Basisadresse des Diensts basieren (soweit vorhanden) anstatt die vollständige Endpunktadresse. Damit diese Einstellung immer funktioniert muss der Dienst eine eindeutige Basisadresse verwenden.  
  
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
  
-   Die [SslStreamSecurityBindingElement.SslProtocols](assetId:///P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?qualifyHint=True&autoUpgrade=True)-Eigenschaft  
  
-   Die [TcpTransportSecurity.SslProtocols](assetId:///P:System.ServiceModel.TcpTransportSecurity.SslProtocols?qualifyHint=True&autoUpgrade=True)-Eigenschaft  
  
-   Der Abschnitt [\<transport>](../Topic/%3Ctransport%3E%20of%20%3CnetTcpBinding%3E.md) des Abschnitts [\<netTcpBinding>](../Topic/%3CnetTcpBinding%3E.md)  
  
-   Der Abschnitt [\<sslStreamSecurity>](../Topic/%3CsslStreamSecurity%3E.md) des Abschnitts [\<customBinding>](../Topic/%3CcustomBinding%3E.md)  
  
<a name="WPF462"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 In .NET Framework 4.6.2 wurde Windows Presentation Foundation in den folgenden Bereichen erweitert:  
  
 **Sortieren von Gruppen**  
 Eine Anwendung, die ein [CollectionView](assetId:///T:System.Windows.Data.CollectionView?qualifyHint=False&autoUpgrade=True)-Objekt zum Gruppieren von Daten verwendet, kann nun explizit deklarieren, wie die Gruppen sortiert werden sollen. Das explizite Sortieren behebt das Problem der nicht-intuitiven Sortierung beim dynamischen Hinzufügen oder Entfernen von Gruppen und beim Ändern des Wert der beim Gruppieren beteiligten Elementeigenschaften durch eine App. Diese Vorgehensweise kann auch die Leistung des Gruppenerstellungsprozesses verbessern, indem Vergleiche der Gruppierungseigenschaften nicht bei der Sortierung der vollständigen Sammlung, sondern bei der Sortierung der Gruppen erfolgen/vorgenommen werden.  
  
 Zur Unterstützung der Gruppensortierung beschreiben die neuen Eigenschaften [GroupDescription.SortDescriptions](assetId:///P:System.ComponentModel.GroupDescription.SortDescriptions?qualifyHint=True&autoUpgrade=True) und [GroupDescription.CustomSort](assetId:///P:System.ComponentModel.GroupDescription.CustomSort?qualifyHint=True&autoUpgrade=True), wie die Sammlung von Gruppen sortiert werden soll, die vom [GroupDescription](assetId:///T:System.ComponentModel.GroupDescription?qualifyHint=False&autoUpgrade=True)-Objekt erstellt wurde. Dies ist vergleichbar mit der Art, in der gleichnamige [ListCollectionView](assetId:///T:System.Windows.Data.ListCollectionView?qualifyHint=False&autoUpgrade=True)-Eigenschaften die Sortierung der Datenelemente beschreiben.  
  
 Die beiden neuen statischen Eigenschaften der [PropertyGroupDescription](assetId:///T:System.Windows.Data.PropertyGroupDescription?qualifyHint=False&autoUpgrade=True)-Klasse, [CompareNameAscending](assetId:///P:System.Windows.Data.PropertyGroupDescription.CompareNameAscending?qualifyHint=False&autoUpgrade=True) und [CompareNameDescending](assetId:///P:System.Windows.Data.PropertyGroupDescription.CompareNameDescending?qualifyHint=False&autoUpgrade=True), können für die am häufigsten vorkommenden Fälle verwendet werden.  
  
 Zum Beispiel gruppiert der folgende XAML-Code Daten nach Alter, sortiert die Gruppen in aufsteigender Reihenfolge und gruppierten die Elemente in den einzelnen Gruppen anhand des Nachnamens.  
  
```xaml  
  
<GroupDescriptions>  
     \<PropertyGroupDescription   
         PropertyName=”Age”   
         CustomSort=   
              ”{x:Static PropertyGroupDescription.CompareNamesAscending}”/>  
     </PropertyGroupDescription>  
</GroupDescriptions>  
  
<SortDescriptions>  
     \<SortDescription PropertyName=”LastName”/>  
</SortDescriptions>  
  
```  
  
 **Bildschirmtastatur-Unterstützung**  
 Die Bildschirmtastatur-Unterstützung ermöglicht die fokussierte Verfolgung in WPF-Anwendungen, indem automatisch die neue Bildschirmtastatur in Windows 10 aufgerufen und geschlossen wird, wenn die Fingereingabe von einem Steuerelement empfangen wird, das Texteingabe nutzen kann.  
  
 In früheren Versionen des .NET-Frameworks konnte für WPF-Anwendungen die Fokusverfolgung nur aktiviert werden, wenn in WPF die Unterstützung für Stifte und Touchgesten deaktiviert wurde.  Die WPF-Anwendungen müssen daher zwischen der vollständiger WPF-Gestenunterstützung und der Windows-Mausheraufstufung wählen.  
  
 **DPI pro Monitor**  
 Um die zunehmende Verbreitung hoher und hybrider DPI-Umgebungen für WPF-Apps zu unterstützen, sorgt WPF dafür, dass monitorspezifische DPI-Werte in .NET Framework 4.6.2 erkannt werden. Weitere Informationen dazu, wie Sie in Ihrer WPF-Anwendung dafür sorgen, dass Sie mit monitorspezifischen DPI-Werten kompatibel ist, finden Sie unter [Samples and Developer Guide](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) (Beispiele und Entwicklerhandbuch) auf GitHub.  
  
 In früheren Versionen von .NET Framework sind WPF-Apps kompatibel mit systemspezifischen DPI-Werten. Die Benutzeroberfläche der Anwendung wird anders gesagt ggf. mit dem Betriebssystem skaliert, abhängig von der DPI des Monitors, auf dem die App gerendert wird. ,  
  
 Für Apps, die unter .NET Framework 4.6.2 ausgeführt werden, können Sie monitorspezifische DPI-Änderungen in WPF-Apps deaktivieren, indem Sie eine Konfigurationsanweisung zum Abschnitt [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) Ihrer Anwendungskonfigurationsdatei hinzufügen (siehe das folgende Beispiel):  
  
```xml  
  
<runtime>  
   \<AppContextSwitchOverrides value=”Switch.System.Windows.DoNotScaleForDpiChanges=false”/>  
</runtime>  
  
```  
  
<a name="WF462"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 In .NET Framework 4.6.2 wurde Windows Workflow Foundation im folgenden Bereich erweitert:  
  
 **Unterstützung für C#-Ausdrücke und IntelliSense im neu gehosteten WF-Designer**  
 Ab .NET Framework 4.5 unterstützt Workflow Foundation C#-Ausdrücke sowohl im Visual Studio-Designer als auch in Codeworkflows. Der neu gehostete Workflow-Designer ist eine wichtige Funktion von WF, die zulässt, dass sich der Workflow-Designer in einer Anwendung außerhalb von Visual Studio befindet (z.B. in WPF).  Windows Workflow Foundation bietet die Möglichkeit der Unterstützung von C#-Ausdrücken und IntelliSense im neu gehosteten Workflow-Designer. Weitere Informationen finden Sie im [Windows Workflow Foundation-Blog](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).  
  
 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`  
 In Versionen von .NET Framework vor .NET Framework 4.6.2 wird IntelliSense in WF-Designer unterbrochen, wenn ein Kunde ein Workflowprojekt von Visual Studio neu erstellt. Obwohl die Erstellung des Projekts erfolgreich war, können die Workflowtypen nicht im Designer gefunden werden und IntelliSense gibt Warnungen für die fehlenden Workflowtypen im Fenster **Fehlerliste** aus. .NET Framework 4.6.2 behebt dieses Problem und macht IntelliSense verfügbar.  
  
 **Workflow V1-Anwendungen mit aktivierter Workflowüberwachung werden im FIPS-Modus ausgeführt**  
 Computer mit aktiviertem FIPS-Kompatibilitätsmodus können jetzt erfolgreich eine Anwendung, die dem Stil der Workflowversion 1 entspricht, mit aktivierter Workflowüberwachung ausführen. Sie müssen die folgenden Änderungen in Ihrer app.config-Datei vornehmen, um dieses Szenario zu aktivieren:  
  
```xml  
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />  
```  
  
 Wenn dieses Szenario nicht aktiviert ist, führt das Ausführen der Anwendung weiterhin dazu, dass eine Ausnahme mit folgender Meldung ausgelöst wird: „Diese Implementation ist nicht Teil der Windows Platform FIPS-überprüften kryptografischen Algorithmen.“  
  
 **Verbesserungen des Workflows bei der Verwendung von dynamischen Updates mit dem Workflow-Designer von Visual Studio**  
 Der Workflow-Designer, der Flussdiagramm-Aktivitätsdesigner und andere Workflow-Aktivitätsdesigner laden nun erfolgreich Workflows, die nach dem Aufruf der [DynamicUpdateServices.PrepareForUpdate](assetId:///M:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate(System.Activities.Activity)?qualifyHint=True&autoUpgrade=True)-Methode gespeichert wurden, und zeigen diese an. In Versionen von .NET Framework vor .NET Framework 4.6.2 kann das Laden einer XAML-File in Visual Studio für einen Workflow, der nach dem Aufruf von [DynamicUpdateServices.PrepareForUpdate](assetId:///M:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate(System.Activities.Activity)?qualifyHint=True&autoUpgrade=True) gespeichert wurde, zu folgenden Problemen führen:  
  
-   Der Workflow-Designer kann die XAML-Datei nicht ordnungsgemäß laden (wenn sich [ViewStateData.Id](assetId:///P:System.Activities.Presentation.ViewState.ViewStateData.Id?qualifyHint=True&autoUpgrade=True) am Ende der Zeile befindet).  
  
-   Der Flussdiagramm-Aktivitätsdesigner oder andere Workflow-Aktivitätsdesigner können möglicherweise alle Objekte an ihrem Standardspeicherort anzeigen, im Gegensatz zu angefügten Eigenschaftswerten.  
  
<a name="ClickOnce"></a>   
### <a name="clickonce"></a>ClickOnce  
 ClickOnce wurde zur Unterstützung von TLS 1.1 und TLS 1.2 neben dem 1.0-Protokoll aktualisiert, das schon unterstützt wird. ClickOnce erkennt automatisch, welches Protokoll erforderlich ist. Es sind keine zusätzlichen Schritte innerhalb der ClickOnce-Anwendung erforderlich, um die TLS 1.1 und 1.2-Unterstützung zu aktivieren.  
  
<a name="UWPConvert"></a>   
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Konvertieren von Windows Forms und WPF-Apps in UWP-Apps  
 Windows bietet nun Möglichkeiten, vorhandene Windows Desktop-Apps, einschließlich WPF- und Windows Forms-Apps, auf der Universal Windows Platform (UWP) bereitzustellen. Diese Technologie agiert als Brücke, indem sie Ihnen ermöglicht, Ihre vorhandene Codebasis nach und nach zu UWP zu migrieren und so Ihre App auf allen Windows 10-Geräten bereitzustellen.  
  
 Konvertierte Desktop-Apps erlangen eine App-Identität ähnlich der App-Identität von UWP-Apps, wodurch UWP-APIs zugänglich gemacht werden, um Funktionen wie Live-Kacheln und Benachrichtigungen zu aktivieren. Die App verhält sich weiterhin wie zuvor und wird als voll vertrauenswürdige App ausgeführt. Sobald die App konvertiert ist, kann ein App-Container-Prozess zum vorhandenen voll vertrauenswürdigen Prozess hinzugefügt werden, um eine adaptive Benutzeroberfläche hinzuzufügen. Wenn alle Funktionen in den App-Container-Prozess verschoben werden, kann der vollständig vertrauenswürdige Prozess entfernt werden, und die neue UWP-App kann auf allen Windows 10-Geräten zur Verfügung gestellt werden.  
  
<a name="Debug462"></a>   
### <a name="debugging-improvements"></a>Verbesserungen beim Debugging  
 Die *nicht verwaltete Debug-API* wurde in .NET Framework 4.6.2 verbessert, um zusätzlichen Analysen durchzuführen, wenn eine [NullReferenceException](assetId:///T:System.NullReferenceException?qualifyHint=False&autoUpgrade=True)-Klasse ausgelöst wird, sodass es möglich ist, zu bestimmen, welche Variablen in einer einzelnen Zeile des Quellcodes `null` ist.   Um dieses Szenario zu unterstützen, wurden die folgenden APIs der nicht verwalteten Debug-API hinzugefügt.  
  
-   Die Schnittstellen [ICorDebugCode4](../Topic/ICorDebugCode4%20Interface.md), [ICorDebugVariableHome](../Topic/ICorDebugVariableHome%20Interface.md), und [ICorDebugVariableHomeEnum](../Topic/ICorDebugVariableHomeEnum%20Interface.md), die den Ursprungsort verwalteter Variablen verfügbar machen. Dadurch können Debugger Codeflussanalysen durchführen, wenn eine [NullReferenceException](assetId:///T:System.NullReferenceException?qualifyHint=False&autoUpgrade=True) auftritt, und auf dieser Grundlage die verwaltete Variable zu bestimmen, die dem nativen Speicherort entspricht, der `null` war.  
  
-   Die Methode [ICorDebugType2::GetTypeID](../Topic/ICorDebugType2::GetTypeID%20Method.md) bietet eine Zuordnung für die Schnittstelle „ICorDebugType“ zur Struktur [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md), wodurch der Debugger eine [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md)-Struktur ohne eine Instanz der Schnittstelle „ICorDebugType“ abrufen kann. Vorhandenen APIs auf der [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md)-Struktur kann dann verwendet werden, um das Klassenlayout des Typs zu bestimmen.  
  
<a name="v461"></a>   
## <a name="whats-new-in-the-net-framework-461"></a>Neuigkeiten in .NET Framework 4.6.1  
 .NET Framework 4.6.1 umfasst neue Features in den folgenden Bereichen:  
  
-   [Kryptografie](#Crypto)  
  
-   [ADO.NET](#ADO.NET461)  
  
-   [Windows Presentation Foundation (WPF)](#WPF461)  
  
-   [Windows Workflow Foundation](#WWF461)  
  
-   [Profilerstellung](#Profile461)  
  
-   [NGen](#NGEN461)  
  
 Weitere Einzelheiten zu .NET Framework 4.6.1 finden Sie in den folgenden Themen:  
  
-   [Liste der Änderungen in .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=622964)  
  
-   [Anwendungskompatibilität in 4.6.1](../Topic/Application%20Compatibility%20in%20the%20.NET%20Framework%204.6.1.md)  
  
-   [Unterschiede der .NET Framework-API](http://go.microsoft.com/fwlink/?LinkId=622989) (auf GitHub)  
  
<a name="Crypto"></a>   
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Kryptografie: Unterstützung für X509-Zertifikate mit ECDSA  
 RSACng-Unterstützung für X509-Zertifikate in .NET Framework 4.6. .NET Framework 4.6.1 fügt Unterstützung für ECDSA (Elliptic Curve Digital Signature Algorithm) X509-Zertifikate hinzu.  
  
 ECDSA bietet eine bessere Leistung und einen sichereren Kryptografiealgorithmus als RSA. Somit ist die Lösung eine hervorragende Wahl, wenn es um TLS (Transport Layer Security)-Leistung und Skalierbarkeit geht. Die .NET Framework-Implementierung schließt Aufrufe in die vorhandene Windows-Funktionalität ein.  
  
 Im folgenden Codebeispiel wird gezeigt, wie einfach es ist, eine Signatur für einen Bytedatenstrom mit der neuen in .NET Framework 4.6.1 enthaltenen ECDSA-Unterstützung für X509-Zertifikate zu generieren.  
  
<!-- TODO: review snippet reference  [!CODE [whatsnew.461.crypto#1](../CodeSnippet/VS_Snippets_CLR/whatsnew.461.crypto#1)]  -->  
  
 Dies steht in deutlichem Gegensatz zu dem Code, der zum Generieren einer Signatur in .NET Framework 4.6 erforderlich war.  
  
<!-- TODO: review snippet reference  [!CODE [whatsnew.461.crypto#2](../CodeSnippet/VS_Snippets_CLR/whatsnew.461.crypto#2)]  -->  
  
<a name="ADO.NET461"></a>   
### ADO.NET wurde um die folgenden Features erweitert:  
  
 "Always Encrypted"-Unterstützung für hardwaregeschützte Schlüssel  
 ADO.NET unterstützt jetzt die systemeigene Speicherung von "Always Encrypted"-Spaltenhauptschlüsseln in Hardwaresicherheitsmodulen (Hardware Security Modules, HSMs). Mit dieser Unterstützung profitieren Kunden von asymmetrischen, in HSMs gespeicherten Schlüsseln, ohne benutzerdefinierte Spaltenhauptschlüssel-Speicheranbieter zu schreiben und in Anwendungen registrieren zu müssen.  
  
 Kunden müssen die vom HSM-Anbieter bereitgestellten CSP-Anbieter oder CNG-Schlüsselspeicheranbieter auf den App-Servern oder Clientcomputern installieren, um über die in einem HSM gespeicherten Spaltenhauptschlüssel auf die mit "Always Encrypted" geschützten Daten zuzugreifen.  
  
 Verbessern des [MultiSubnetFailover](assetId:///P:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover?qualifyHint=False&autoUpgrade=True)-Verbindungsverhaltens für AlwaysOn  
 SqlClient ermöglicht jetzt automatisch schnellere Verbindungen mit einer AlwaysOn-Verfügbarkeitsgruppe (Availability Group, AG). Er erkennt auf transparente Weise, ob die Anwendung eine Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe in einem anderen Subnetz herstellt, ermittelt schnell den aktiven Server und stellt eine Verbindung mit dem Server her. Vor dieser Version musste eine Anwendung `“MultisubnetFailover=true”` in die Verbindungszeichenfolge einschließen, um anzugeben, dass eine Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe hergestellt wurde. Wenn das Verbindungsschlüsselwort nicht auf `true` festgelegt wird, kann bei der Verbindung mit einer AlwaysOn-Verfügbarkeitsgruppe ein Anwendungstimeout auftreten. Bei dieser Version muss eine Anwendung [MultiSubnetFailover](assetId:///P:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover?qualifyHint=False&autoUpgrade=True) *nicht* mehr auf `true` festlegen. Weitere Informationen zur SqlClient-Unterstützung für AlwaysOn-Verfügbarkeitsgruppen finden Sie unter [SqlClient-Unterstützung für hohe Verfügbarkeit, Notfallwiederherstellung](../Topic/SqlClient%20Support%20for%20High%20Availability,%20Disaster%20Recovery.md).  
  
<a name="WPF461"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 Windows Presentation Foundation umfasst eine Reihe von Verbesserungen und Änderungen.  
  
 Leistungssteigerung  
 Die Verzögerung beim Auslösen von Touchereignissen wurde in .NET Framework 4.6.1 behoben. Wenn eine Eingabe in ein [RichTextBox](assetId:///T:System.Windows.Controls.RichTextBox?qualifyHint=False&autoUpgrade=True)-Steuerelement erfolgt, wird außerdem der Renderthread während der schnellen Eingabe nicht mehr vollständig beansprucht.  
  
 Verbesserte Rechtschreibprüfung  
 Die Rechtschreibprüfung in WPF wurde unter Windows 8.1 und höheren Versionen aktualisiert, um die Betriebssystemunterstützung für die Rechtschreibprüfung zusätzlicher Sprachen zu nutzen.  Bezüglich der Funktionalität in Windows-Versionen vor Windows 8.1 gibt es keine Änderung.  
  
 Wie in früheren .NET Framework-Versionen wird die Sprache eines [TextBox](assetId:///T:System.Windows.Controls.TextBox?qualifyHint=False&autoUpgrade=True)-Steuerelements oder [RichTextBox](assetId:///T:System.Windows.Controls.RichTextBox?qualifyHint=False&autoUpgrade=True)-Blocks ermittelt, indem in der folgenden Reihenfolge nach Informationen gesucht wird:  
  
-   `xml:lang`, falls vorhanden.  
  
-   Aktuelle Eingabesprache  
  
-   Aktuelle Threadkultur  
  
 Weitere Informationen zur Sprachunterstützung in WPF finden Sie im [WPF-Blogbeitrag zu .NET Framework 4.6.1-Features](http://go.microsoft.com/fwlink/?LinkID=691819).  
  
 Zusätzliche Unterstützung für benutzerdefinierte Wörterbücher pro Benutzer  
 In .NET Framework 4.6.1 erkennt WPF benutzerdefinierte Wörterbücher, die global registriert sind. Diese Funktion ist zusätzlich zur Registrierung der Wörterbücher pro Steuerelement verfügbar.  
  
 In früheren WPF-Versionen wurden Listen ausgeschlossener Wörter und AutoKorrektur-Listen von benutzerdefinierten Wörterbüchern nicht erkannt. Diese werden unter Windows 8.1 und Windows 10 mittels Dateien unterstützt, die im Verzeichnis `%AppData%\Microsoft\Spelling\<language tag>` abgelegt werden können.  Für diese Dateien gelten die folgenden Regeln:  
  
-   Die Dateien sollten über die Erweiterungen ".dic" (hinzugefügte Wörter), ".exc" (ausgeschlossene Wörter) oder ".acl" (AutoKorrektur-Wörter) verfügen.  
  
-   Außerdem sollten sie das UTF-16LE-Nur-Text-Format aufweisen, das mit der Bytereihenfolgenmarke (Byte Order Mark, BOM) beginnt.  
  
-   Jede Zeile sollte aus einem Wort (aus der Liste hinzugefügter und ausgeschlossener Wörter) oder einem AutoKorrektur-Paar bestehen, bei dem die Wörter durch einen senkrechten Strich („&#124;“) (in der AutoKorrektur-Wortliste) getrennt sind.  
  
-   Diese Dateien sind schreibgeschützt und werden vom System nicht geändert.  
  
> [!NOTE]
>  Diese neuen Dateiformate werden von der WPF-Rechtschreibprüfungs-API nicht direkt unterstützt, sodass die benutzerdefinierten Wörterbücher, die in Anwendungen für WPF bereitgestellt werden, weiterhin LEX-Dateien verwenden sollten.  
  
 Proben  
 Auf MSDN finden sich eine Reihe von [WPF-Beispielen](https://msdn.microsoft.com/library/ms771633.aspx). Mehr als 200 der bekanntesten Beispiele werden (basierend auf ihrer Verwendung) in ein [Open Source-GitHub-Repository](https://github.com/Microsoft/WPF-Samples) verschoben. Helfen Sie uns bei der Verbesserung unserer Beispiele, indem Sie uns einen Pull Request senden oder ein [GitHub-Problem](https://github.com/Microsoft/WPF-Samples/issues) eröffnen.  
  
 DirectX-Erweiterungen  
 WPF enthält ein [NuGet-Paket](http://go.microsoft.com/fwlink/?LinkID=691342) mit neuen Implementierungen von [D3DImage](assetId:///T:System.Windows.Interop.D3DImage?qualifyHint=False&autoUpgrade=True). Diese erleichtern die Interoperabilität mit DX10- und DX11-Inhalten. Der Code für dieses Paket steht als Open Source-Code auf [GitHub](https://github.com/Microsoft/WPFDXInterop) zur Verfügung.  
  
<a name="WWF461"></a>   
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: Transaktionen  
 Von der [Transaction.EnlistPromotableSinglePhase](assetId:///Overload:System.Transactions.Transaction.EnlistPromotableSinglePhase?qualifyHint=True&autoUpgrade=True)-Methode kann jetzt ein anderer Manager für verteilte Aktionen als MSDTC verwendet werden, um die Transaktion höherzustufen. Dazu geben Sie einen Bezeichner zur Höherstufung der GUID-Transaktion für die neue [Transaction.EnlistPromotableSinglePhase(IPromotableSinglePhaseNotification, Guid)](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification,System.Guid)?qualifyHint=True&autoUpgrade=False)-Überladung an. Wenn dieser Vorgang erfolgreich ist, unterliegt die Transaktionsfunktionalität gewissen Einschränkungen. Sobald ein Nicht-MSDTC-Transaktionspromoter eingetragen wird, lösen die folgenden Methoden eine [TransactionPromotionException](assetId:///T:System.Transactions.TransactionPromotionException?qualifyHint=False&autoUpgrade=True) aus, da diese Methoden die Höherstufung auf MSDTC erfordern:  
  
-   [Transaction.EnlistDurable](assetId:///Overload:System.Transactions.Transaction.EnlistDurable?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetDtcTransaction](assetId:///M:System.Transactions.TransactionInterop.GetDtcTransaction(System.Transactions.Transaction)?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetExportCookie](assetId:///M:System.Transactions.TransactionInterop.GetExportCookie(System.Transactions.Transaction,System.Byte[])?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetTransmitterPropagationToken](assetId:///M:System.Transactions.TransactionInterop.GetTransmitterPropagationToken(System.Transactions.Transaction)?qualifyHint=True&autoUpgrade=True)  
  
 Sobald ein Nicht-MSDTC-Transaktionspromoter eingetragen wird, muss er mit dauerhaften Eintragungen verwendet werden. Dabei werden die von ihm definierten Protokolle verwendet. Die [Guid](assetId:///T:System.Guid?qualifyHint=False&autoUpgrade=True) des Transaktionspromoters kann mithilfe der [PromoterType](assetId:///P:System.Transactions.Transaction.PromoterType?qualifyHint=False&autoUpgrade=True)-Eigenschaft abgerufen werden. Bei der Höherstufung der Transaktion stellt der Transaktionspromoter ein [Byte](assetId:///T:System.Byte?qualifyHint=False&autoUpgrade=True)-Array bereit, das das höher gestufte Token darstellt. Eine Anwendung kann das höher gestufte Token für eine nicht von MSDTC höher gestufte Transaktion mit der [GetPromotedToken](assetId:///M:System.Transactions.Transaction.GetPromotedToken?qualifyHint=False&autoUpgrade=True)-Methode abrufen.  
  
 Benutzer der neuen [Transaction.EnlistPromotableSinglePhase(IPromotableSinglePhaseNotification, Guid)](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification,System.Guid)?qualifyHint=True&autoUpgrade=False)-Überladung müssen einer bestimmten Aufrufsequenz folgen, damit die Höherstufung erfolgreich abgeschlossen werden kann. Diese Regeln werden in der Dokumentation der Methode beschrieben.  
  
<a name="Profile461"></a>   
### <a name="profiling"></a>Profilerstellung  
 Die nicht verwaltete Profilerstellungs-API wurde wie folgt erweitert:  
  
 Bessere Unterstützung für den Zugriff auf PDBs in der [ICorProfilerInfo7](../Topic/ICorProfilerInfo7%20Interface.md)-Schnittstelle  
 In ASP.Net 5 werden Assemblys im Arbeitsspeicher immer häufiger mit Roslyn kompiliert. Für Entwickler von Profilertools bedeutet dies, dass PDB-Dateien, die früher auf Datenträgern serialisiert wurden, u. U. nicht mehr vorkommen. Profilertools verwenden PDB-Dateien häufig, um Codezeilen wieder den Quellzeilen zuzuordnen, beispielsweise für die Codeabdeckung oder zeilenweise Leistungsanalysen. Die [ICorProfilerInfo7](../Topic/ICorProfilerInfo7%20Interface.md)-Schnittstelle enthält jetzt zwei neue Methoden, [ICorProfilerInfo7::GetInMemorySymbolsLength](../Topic/ICorProfilerInfo7::GetInMemorySymbolsLength%20Method.md) und [ICorProfilerInfo7::ReadInMemorySymbols](../Topic/ICorProfilerInfo7::ReadInMemorySymbols.md), um diesen Profilertools Zugriff auf die PDB-Daten im Arbeitsspeicher zu gewähren. Mithilfe der neuen APIs kann ein Profiler Inhalte einer im Arbeitsspeicher enthaltenen PDB-Datei als Bytearray abrufen und dieses anschließend verarbeiten oder auf den Datenträger serialisieren.  
  
 Bessere Instrumentation mit der ICorProfiler-Schnittstelle  
 Profiler, die die ReJit-Funktionalität der `ICorProfiler`-API für die dynamische Instrumentation verwenden, sind jetzt in der Lage, einige Metadaten zu ändern. Früher konnte IL durch diese Tools jederzeit instrumentiert werden, während Metadaten nur zur Ladezeit des Moduls geändert werden konnten. Da IL auf Metadaten verweist, sind die möglichen Instrumentationsarten eingeschränkt. Wir haben einige dieser Beschränkungen durch Hinzufügen der [ICorProfilerInfo7::ApplyMetaData](../Topic/ICorProfilerInfo7::ApplyMetaData%20Method.md)-Methode aufgehoben. Dadurch werden einige Metadatenbearbeitungen nach dem Laden des Moduls ermöglicht, insbesondere das Hinzufügen neuer `AssemblyRef`-, `TypeRef`-, `TypeSpec`-, `MemberRef`-, `MemberSpec`- und `UserString`-Datensätze. Diese Änderung erweitert die Möglichkeiten der dynamischen Instrumentation.  
  
<a name="NGEN461"></a>   
### <a name="native-image-generator-ngen-pdbs"></a>NGEN (Native Image Generator)-PDBs  
 Die computerübergreifende Ereignisablaufverfolgung ermöglicht Kunden die Profilerstellung für ein Programm auf Computer A und die Anzeige der Profilerstellungsdaten per Quellzeilenzuordnung auf Computer B. Unter früheren .NET Framework-Versionen musste der Benutzer alle Module und systemeigenen Images vom Profilcomputer auf den Analysecomputer kopieren, der die IL PDB-Datei für die Zuordnung zwischen Quellzeilen und systemeigenen Images enthielt. Während dies bei kleineren Dateien wie Handy-Apps durchaus gut funktionieren kann, können Desktopsystemdateien ziemlich anwachsen und beträchtliche Zeit für das Kopieren erfordern.  
  
 Bei NGEN PDB-Dateien kann NGen eine PDB-Datei erstellen, die die Zuordnung zwischen IL und systemeigenen Images enthält, ohne dass eine Abhängigkeit von der IL PDB-Datei besteht. In diesem Szenario für die computerübergreifende Ereignisablaufverfolgung muss lediglich die von Computer A generierte PDB-Datei für systemeigene Images auf Computer B kopiert werden, und die [Debug Interface Access-APIs](https://docs.microsoft.com/en-us/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) müssen verwendet werden, um die „Quellzeilen-zu-IL“-Zuordnung der IL PDB-Datei und die „IL-zu-systemeigene Images“-Zuordnung der PDB-Datei für systemeigene Images zu lesen. Durch die Kombination beider Zuordnungen entsteht eine Zuordnung zwischen Quellzeilen und systemeigenem Image. Da die PDB-Datei für systemeigene Images viel kleiner als alle Module und systemeigenen Images ist, wird das Kopieren von Computer A auf Computer B deutlich beschleunigt.  
  
<a name="v46"></a>   
## <a name="whats-new-in-net-2015"></a>Neuigkeiten in .NET 2015  
 .NET Framework 2015 führt .NET Framework 4.6 und .NET Core ein. Einige neue Features gelten für beide, während andere Funktionen für .NET Framework 4.6 bzw. .NET Core spezifisch sind.  
  
-   **ASP.NET 5**  
  
     .NET 2015 enthält ASP.NET 5, eine schlanke .NET-Plattform zum Erstellen moderner, cloudbasierter Apps. Die Plattform ist modular aufgebaut, sodass Sie nur die Funktionen aufnehmen können, die Sie in Ihrer Anwendung benötigen. Sie kann auf IIS oder eigenständig in einem benutzerdefinierten Prozess gehostet werden, und Sie können Apps mit verschiedenen Versionen von .NET Framework auf demselben Server ausführen. Sie umfasst ein neues Umgebungskonfigurationssystem, das für die Cloudbereitstellung entwickelt wurde.  
  
     MVC, Web-API und Webseiten sind in einem einzigen Framework namens MVC 6 vereint. Sie erstellen ASP.NET 5-Apps mithilfe der neuen Tools in Visual Studio 2015. Ihre vorhandenen Anwendungen funktionieren im neuen .NET Framework. Um jedoch eine App zu erstellen, die MVC 6 oder SignalR 3 verwendet, müssen Sie das Projektsystem in Visual Studio 2015 verwenden.  
  
     Weitere Informationen finden Sie unter [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).  
  
-   **Updates für ASP.NET**  
  
    -   **Aufgabenbasierte API für die asynchrone Antwortleerung**  
  
         ASP.NET verfügt nun mit [HttpResponse.FlushAsync](assetId:///M:System.Web.HttpResponse.FlushAsync?qualifyHint=True&autoUpgrade=True) über eine einfache aufgabenbasierte API für die asynchrone Antwortleerung. Hiermit wird mithilfe der `async/await`-Unterstützung für Ihre Sprache die asynchrone Leerung von Antworten ermöglicht.  
  
    -   `Model binding supports task-returning methods`  
  
         In .NET Framework 4.5 wurde ASP.NET das Modellbindungsfeature hinzugefügt, das einen erweiterbaren, codeorientierten Ansatz für CRUD-basierte Datenvorgänge in Web Forms-Seiten und Benutzersteuerelementen ermöglicht. Das Modellbindungssystem unterstützt nun wiederkehrende [Task](assetId:///T:System.Threading.Tasks.Task?qualifyHint=False&autoUpgrade=True)-Modellbindungsmethoden. Dadurch erhalten Web Forms-Entwickler die Vorteile hinsichtlich der Asynchronität und die Einfachheit des Datenbindungssystems beim Verwenden neuerer Versionen von ORMs, einschließlich des Entity Frameworks.  
  
         Die asynchrone Modellbindung wird durch die `aspnet:EnableAsyncModelBinding`-Konfigurationseinstellung gesteuert.  
  
        ```  
  
        <appSettings>  
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />  
        </appSettings>  
  
        ```  
  
         Bei auf .NET Framework 4.6 ausgerichteten Apps wird der Standardwert auf `true` festgelegt. Bei Apps in .NET Framework 4.6, die auf eine frühere Version von .NET Framework ausgerichtet sind, ist `false` der Standard. Dies kann aktiviert werden, indem die Konfigurationseinstellung auf `true` festgelegt wird.  
  
    -   **HTTP/2-Unterstützung (Windows 10)**  
  
         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) ist eine neue Version des HTTP-Protokolls, die eine wesentlich bessere Nutzung von Verbindungen ermöglicht (weniger Roundtrips zwischen Client und Server) und so die Latenz beim Laden von Webseiten für Benutzer verringert.  Webseiten profitieren am meisten von HTTP/2 (im Gegensatz zu Services), da das Protokoll Anforderungen mehrerer Artefakte in einem Aufruf zusammenfasst und so optimiert. Die HTTP/2-Unterstützung wurde zu ASP.NET in .NET Framework 4.6 hinzugefügt. Da Netzwerkfunktionen auf mehreren Ebenen vorhanden sind, waren neue Funktionen in Windows, IIS und ASP.NET erforderlich, um HTTP/2 nutzen zu können. Sie müssen Windows 10 ausführen, um HTTP/2 mit ASP.NET nutzen zu können.  
  
         HTTP/2 wird auch unterstützt und ist standardmäßig für Windows 10-UWP-Apps aktiviert, die die [System.Net.Http.HttpClient](assetId:///T:System.Net.Http.HttpClient?qualifyHint=True&autoUpgrade=True)-API verwenden.  
  
         Zum Bereitstellen einer Möglichkeit für die Verwendung des Features [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) in ASP.NET-Anwendungen wurde der Klasse [HttpResponse](assetId:///T:System.Web.HttpResponse?qualifyHint=False&autoUpgrade=True) eine neue Methode mit zwei Überladungen ([PushPromise(String)](assetId:///M:System.Web.HttpResponse.PushPromise(System.String)?qualifyHint=False&autoUpgrade=False) und [PushPromise(String, String, NameValueCollection)](assetId:///M:System.Web.HttpResponse.PushPromise(System.String,System.String,System.Collections.Specialized.NameValueCollection)?qualifyHint=False&autoUpgrade=False)) hinzugefügt.  
  
        > [!NOTE]
        >  Während ASP.NET 5 Unterstützung für HTTP/2 enthält, wurde noch keine Unterstützung für das PUSH PROMISE-Feature hinzugefügt.  
  
         Browser und Webserver (IIS unter Windows) erledigen die gesamte Arbeit. Sie müssen keine umfangreichen Aufgaben für Ihre Benutzer ausführen.  
  
         Die meisten [gängigen Browser unterstützen HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), sodass Ihre Benutzer wahrscheinlich vom HTTP/2-Protokoll profitieren können, sofern Ihr Server dies unterstützt.  
  
    -   **Unterstützung für das Tokenbindungsprotokoll**  
  
         Microsoft und Google haben gemeinsam einen neuen Ansatz für die Authentifizierung erarbeitet, das so genannte [Tokenbindungsprotokoll](https://github.com/TokenBinding/Internet-Drafts). Die Prämisse: Authentifizierungstoken (im Browsercache) können von Internetkriminellen gestohlen und verwendet werden, um auf ansonsten sichere Ressourcen (z. B. Bankkonten) zuzugreifen, ohne Ihr Kennwort oder andere geschützte Informationen zu kennen. Das neue Protokoll zielt darauf ab, dieses Problem zu minimieren.  
  
         Das Tokenbindungsprotokoll wird in Windows 10 als Browserfunktion implementiert. ASP.NET-Anwendungen werden in das Protokoll einbezogen, damit die Legitimität von Authentifizierungstoken überprüft werden kann. Die Client- und Serverimplementierungen stellen den durch das Protokoll angegebenen umfassenden Schutz bereit.  
  
    -   **Zufällige Zeichenfolgen-Hashalgorithmen**  
  
         Mit .NET Framework 4.5 wurde ein [zufälliger Zeichenfolgen-Hashalgorithmus](https://msdn.microsoft.com/library/jj152924.aspx) eingeführt. Dieser wurde jedoch durch ASP.NET nicht unterstützt, da einige der ASP.NET von einem stabilen Hash abhängig sind. In .NET Framework 4.6 werden nun zufällige Zeichenfolgen-Hashalgorithmen unterstützt. Verwenden Sie zum Aktivieren dieses Features die `aspnet:UseRandomizedStringHashAlgorithm`-Konfigurationseinstellung.  
  
        ```  
  
        <appSettings>  
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />  
        </appSettings>  
  
        ```  
  
-   **ADO.NET**  
  
     ADO .NET unterstützt jetzt das in SQL Server 2016 Community Technology Preview 2 (CTP2) verfügbare Feature zum grundsätzlichen Verschlüsseln. Mit der grundsätzlichen Verschlüsselung kann SQL Server Operationen zu verschlüsselten Daten durchführen und das Beste ist, der Verschlüsselungsschlüssel ist bei der Anwendung in der vertrauenswürdigen Umgebung des Kunden abgelegt, nicht auf dem Server. Die grundsätzliche Verschlüsselung sichert Kundendaten so, dass DBAs keinen Zugriff auf Textdaten haben. Die Verschlüsselung und Entschlüsselung von Daten erfolgt transparent auf Treiberebene, dadurch werden die an vorhandenen Anwendungen erforderlichen Änderungen auf ein Mindestmaß reduziert. Weitere Informationen finden Sie unter [Always Encrypted (Datenbankmodul)](https://msdn.microsoft.com/library/mt163865\(v=sql.130\).aspx) und [Always Encrypted (Cliententwicklung)](https://msdn.microsoft.com/library/mt147923\(v=sql.130\).aspx).  
  
-   **64-Bit-JIT-Compiler für verwalteten Code**  
  
     .NET Framework 4.6 umfasst eine neue Version des 64-Bit-JIT-Compilers (ursprünglicher Codename „RyuJIT“). Der neue 64-Bit-Compiler bietet erhebliche Leistungsverbesserungen im Vergleich zum älteren 64-Bit-JIT-Compiler. Der neue 64-Bit-Compiler wird für 64-Bit-Prozesse aktiviert, die zusätzlich zu .NET Framework 4.6 ausgeführt werden. Ihre App wird in einem 64-Bit-Prozess ausgeführt, wenn sie als 64 Bit oder AnyCPU kompiliert ist und auf einem 64-Bit-Betriebssystem ausgeführt wird. Obwohl der Übergang zum neuen Compiler so transparent wie möglich verlief, sind Änderungen im Verhalten möglich. Wir möchten Sie bitten, uns direkt über Probleme zu informieren, die beim Verwenden des neuen JIT-Compilers auftreten. Kontaktieren Sie uns über [Microsoft Connect](http://connect.microsoft.com/), wenn Sie ein Problem feststellen, das möglicherweise mit dem neuen 64-Bit-JIT-Compiler zusammenhängt.  
  
     Der neue 64-Bit-Compiler umfasst zudem Hardware-SIMD-Beschleunigungsfeatures, wenn er mit SIMD-fähigen Typen im [System.Numerics](assetId:///N:System.Numerics?qualifyHint=False&autoUpgrade=True)-Namespace gekoppelt wird, was zu Leistungsverbesserungen führen kann.  
  
-   **Verbesserungen am Assemblyladeprogramm**  
  
     Das Assemblyladeprogramm verwendet nun den Arbeitsspeicher effizienter, indem IL-Assemblys entladen werden, nachdem ein entsprechendes NGEN-Image geladen wurde. Durch diese Änderung wird der virtuelle Arbeitsspeicher verringert. Dies ist besonders bei großen 32-Bit-Apps (wie Visual Studio) hilfreich. Zudem wird dadurch physischer Arbeitsspeicher eingespart.  
  
-   **Änderungen an Basisklassenbibliotheken**  
  
     Viele neue APIs wurden im Umfeld von .NET Framework 4.6 hinzugefügt, um wichtige Szenarien zu ermöglichen. Dazu zählen die folgenden Änderungen und Ergänzungen:  
  
    -   **IReadOnlyCollection\<T>-Implementierungen**  
  
         Zusätzliche Auflistungen implementieren [IReadOnlyCollection\<T>](assetId:///T:System.Collections.Generic.IReadOnlyCollection`1?qualifyHint=False&autoUpgrade=True), wie z. B. [Queue<T\>](assetId:///T:System.Collections.Generic.Queue`1?qualifyHint=False&autoUpgrade=True) und [Stack\<T>](assetId:///T:System.Collections.Generic.Stack`1?qualifyHint=False&autoUpgrade=True).  
  
    -   **CultureInfo.CurrentCulture und CultureInfo.CurrentUICulture**  
  
         Die Eigenschaften [CultureInfo.CurrentCulture](assetId:///P:System.Globalization.CultureInfo.CurrentCulture?qualifyHint=True&autoUpgrade=True) und [CultureInfo.CurrentUICulture](assetId:///P:System.Globalization.CultureInfo.CurrentUICulture?qualifyHint=True&autoUpgrade=True) bieten nun Lese- und Schreibzugriff und sind nicht mehr schreibgeschützt. Wenn Sie diesen Eigenschaften ein neues [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True)-Objekt zuweisen, ändern sich ebenfalls die aktuelle Threadkultur, die durch die Eigenschaft `Thread.CurrentThread.CurrentCulture` definiert ist, sowie die aktuelle UI-Threadkultur, die durch die Eigenschaft `Thread.CurrentThread.CurrentUICulture` definiert ist.  
  
    -   **Verbesserungen bei der Garbage Collection (GC)**  
  
         Die [GC](assetId:///T:System.GC?qualifyHint=False&autoUpgrade=True)-Klasse enthält nun die Methoden [TryStartNoGCRegion](assetId:///M:System.GC.TryStartNoGCRegion(System.Int64)?qualifyHint=False&autoUpgrade=True) und [EndNoGCRegion](assetId:///M:System.GC.EndNoGCRegion?qualifyHint=False&autoUpgrade=True), die es Ihnen ermöglichen, die Garbage Collection während der Ausführung eines kritischen Pfads zu unterbinden.  
  
         Eine neue Überladung der [GC.Collect(Int32, GCCollectionMode, Boolean, Boolean)](assetId:///M:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean,System.Boolean)?qualifyHint=True&autoUpgrade=False)-Methode erlaubt Ihnen die Kontrolle, ob für den kleinen und großen Objektheap eine Komprimierung und ein Sweep ausgeführt werden, ober ob nur ein Sweep für sie ausgeführt wird.  
  
    -   **SIMD-fähige Typen**  
  
         Der Namespace [System.Numerics](assetId:///N:System.Numerics?qualifyHint=False&autoUpgrade=True) enthält nun verschiedene SIMD-aktivierte Typen wie [Matrix3x2](assetId:///T:System.Numerics.Matrix3x2?qualifyHint=False&autoUpgrade=True), [Matrix4x4](assetId:///T:System.Numerics.Matrix4x4?qualifyHint=False&autoUpgrade=True), [Plane](assetId:///T:System.Numerics.Plane?qualifyHint=False&autoUpgrade=True), [Quaternion](assetId:///T:System.Numerics.Quaternion?qualifyHint=False&autoUpgrade=True), [Vector2](assetId:///T:System.Numerics.Vector2?qualifyHint=False&autoUpgrade=True), [Vector3](assetId:///T:System.Numerics.Vector3?qualifyHint=False&autoUpgrade=True) und [Vector4](assetId:///T:System.Numerics.Vector4?qualifyHint=False&autoUpgrade=True).  
  
         Da der neue 64-Bit-JIT-Compiler zudem Hardware-SIMD-Beschleunigungsfeatures enthält, liegen insbesondere erhebliche Leistungsverbesserungen beim Verwenden von SIMD-fähigen Typen mit dem neuen 64-Bit-JIT-Compiler vor.  
  
    -   **Kryptografieupdates**  
  
         Die [System.Security.Cryptography](assetId:///N:System.Security.Cryptography?qualifyHint=True&autoUpgrade=True)-API wird aktualisiert, um die [Kryptografie-APIs von Windows CNG](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx) zu unterstützen. Frühere Versionen von .NET Framework basierten vollständig auf einer [früheren Version der Kryptografie-APIs von Windows](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) als Grundlage der [System.Security.Cryptography](assetId:///N:System.Security.Cryptography?qualifyHint=True&autoUpgrade=True)-Implementierung. Benutzer forderten die Unterstützung der CNG-API, da diese [moderne Kryptografiealgorithmen](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support) unterstützt, die für bestimmte Kategorien von Apps wichtig sind.  
  
         .NET Framework 4.6 umfasst die folgenden neuen Erweiterungen, um die Kryptografie-API von Windows CNG zu unterstützen:  
  
        -   Ein Satz von Erweiterungsmethoden für X509-Zertifikate, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` und `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, die nach Möglichkeit anstelle einer CAPI-basierten Implementierung eine CNG-basierte Implementierung zurückgeben. (Für einige Smartcards usw. ist weiterhin CAPI erforderlich, und die APIs verarbeiten den Fallback).  
  
        -   Die [System.Security.Cryptography.RSACng](assetId:///T:System.Security.Cryptography.RSACng?qualifyHint=True&autoUpgrade=True)-Klasse, die eine CNG-Implementierung des RSA-Algorithmus bietet.  
  
        -   Erweiterungen an der RSA-API, damit für allgemeine Aktionen keine Umwandlung mehr erforderlich ist. Beispielsweise war für das Verschlüsseln von Daten mithilfe eines [X509Certificate2](assetId:///T:System.Security.Cryptography.X509Certificates.X509Certificate2?qualifyHint=False&autoUpgrade=True)-Objekts Code wie der folgende in vorherigen Versionen von .NET Framework erforderlich.  
  
<!-- TODO: review snippet reference              [!CODE [WhatsNew.Casting#1](../CodeSnippet/VS_Snippets_CLR/whatsnew.casting#1)]  -->  
  
             Code that uses the new cryptography APIs in the .NET Framework 4.6 can be rewritten as follows to avoid the cast.  
  
<!-- TODO: review snippet reference              [!CODE [WhatsNew.Casting#2](../CodeSnippet/VS_Snippets_CLR/whatsnew.casting#2)]  -->  
  
    -   **Unterstützung für das Konvertieren von Datumsangaben und Uhrzeiten zur oder aus der Unix-Zeit**  
  
         Die folgenden neuen Methoden wurden zur [DateTimeOffset](assetId:///T:System.DateTimeOffset?qualifyHint=False&autoUpgrade=True)-Struktur hinzugefügt, um das Konvertieren von Datums- und Uhrzeitangaben zur oder aus der UNIX-Zeit zu unterstützen:  
  
        -   [DateTimeOffset.FromUnixTimeSeconds](assetId:///M:System.DateTimeOffset.FromUnixTimeSeconds(System.Int64)?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.FromUnixTimeMilliseconds](assetId:///M:System.DateTimeOffset.FromUnixTimeMilliseconds(System.Int64)?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.ToUnixTimeSeconds](assetId:///M:System.DateTimeOffset.ToUnixTimeSeconds?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.ToUnixTimeMilliseconds](assetId:///M:System.DateTimeOffset.ToUnixTimeMilliseconds?qualifyHint=True&autoUpgrade=True)  
  
    -   **Kompatibilitätsoptionen**  
  
         Die neue [AppContext](assetId:///T:System.AppContext?qualifyHint=False&autoUpgrade=True)-Klasse fügt eine neue Kompatibilitätsfunktion hinzu, die es Bibliotheksautoren ermöglicht, ihren Benutzern einen einheitlichen Abwahlmechanismus für neue Funktionalitäten bereitzustellen. Sie richtet einen lose gekoppelten Vertrag zwischen den Komponenten ein, um eine Anforderung zur Abwahl zu übermitteln. Diese Möglichkeit ist in der Regel wichtig, wenn vorhandene Funktionalitäten verändert werden. Im Gegensatz dazu existiert bereits eine implizite Auswahloption für neue Funktionalitäten.  
  
         Mit [AppContext](assetId:///T:System.AppContext?qualifyHint=False&autoUpgrade=True) definieren Bibliotheken Kompatibilitätsoptionen und machen diese verfügbar, während im Code, der von diesen Bibliotheken abhängig ist, diese Optionen festgelegt werden können, um das Verhalten der Bibliothek zu beeinflussen. Standardmäßig stellen Bibliotheken die neue Funktionalität bereit. Nur wenn die Option festgelegt ist, stellen sie die vorherige Funktionalität bereit.  
  
         Eine Anwendung (oder eine Bibliothek) kann den Wert einer Option deklarieren (hierbei handelt es sich immer um einen [Boolean](assetId:///T:System.Boolean?qualifyHint=False&autoUpgrade=True)-Wert), die von einer abhängige Bibliothek definiert wird. Die Option ist immer implizit `false`. Durch Festlegen der Option auf `true` wird diese aktiviert. Durch explizites Festlegen der Option auf `false` wird das neue Verhalten aktiviert.  
  
        ```csharp  
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);  
        ```  
  
         Die Bibliothek muss überprüfen, ob ein Consumer den Wert der Option deklariert hat, und dann entsprechend reagieren.  
  
        ```  
  
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
  
        -   *Switch*.*namespace*.*switchname*  
  
        -   *Switch*.*library*.*switchname*  
  
    -   **Änderungen am aufgabenbasierten asynchronen Entwurfsmuster (TAP)**  
  
         Bei Apps, die auf .NET Framework 4.6 ausgerichtet sind, erben die Objekte [Task](assetId:///T:System.Threading.Tasks.Task?qualifyHint=False&autoUpgrade=True) und [Task\<TResult>](assetId:///T:System.Threading.Tasks.Task`1?qualifyHint=False&autoUpgrade=True) die Kultur und die UI-Kultur des aufrufenden Threads. Das Verhalten von Apps, die mit früheren Versionen von .NET Framework arbeiten oder auf keine bestimmte Version von .NET Framework ausgelegt sind, ist davon nicht betroffen. Weitere Informationen finden Sie im Abschnitt „Kultur und aufgabenbasierte asynchrone Vorgänge“ im Thema zur [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True)-Klasse.  
  
         Die [System.Threading.AsyncLocal\<T>](assetId:///T:System.Threading.AsyncLocal`1?qualifyHint=True&autoUpgrade=True)-Klasse ermöglicht Ihnen das Darstellen von Umgebungsdaten, die für eine angegebene asynchrone Ablaufsteuerung wie eine `async`-Methode lokal sind. Sie kann zum threadübergreifenden Beibehalten von Daten verwendet werden. Sie können zudem eine Rückrufmethode definieren, die benachrichtigt wird, sobald sich die Umgebungsdaten ändern, und zwar entweder aufgrund der expliziten Änderung der [AsyncLocal<T\>.Value](assetId:///P:System.Threading.AsyncLocal`1.Value?qualifyHint=True&autoUpgrade=True)-Eigenschaft oder weil der Thread einen Kontextübergang ermittelt hat.  
  
         Dem aufgabenbasierten asynchronem Muster (Task-based Asynchronous Pattern, TAP) wurden die drei Hilfsmethoden [Task.CompletedTask](assetId:///P:System.Threading.Tasks.Task.CompletedTask?qualifyHint=True&autoUpgrade=True), [Task.FromCanceled](assetId:///M:System.Threading.Tasks.Task.FromCanceled(System.Threading.CancellationToken)?qualifyHint=True&autoUpgrade=True) und [Task.FromException](assetId:///M:System.Threading.Tasks.Task.FromException(System.Exception)?qualifyHint=True&autoUpgrade=True) hinzugefügt, um abgeschlossene Aufgaben in einem bestimmten Status zurückzugeben.  
  
         Die [NamedPipeClientStream](assetId:///T:System.IO.Pipes.NamedPipeClientStream?qualifyHint=False&autoUpgrade=True)-Klasse unterstützt nun die asynchrone Kommunikation mit der zugehörigen [ConnectAsync](assetId:///M:System.IO.Pipes.NamedPipeClientStream.ConnectAsync?qualifyHint=False&autoUpgrade=True). -Methode.  
  
    -   **EventSource unterstützt jetzt das Schreiben in das Ereignisprotokoll**  
  
         Sie können nun die [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True)-Klasse verwenden, um Verwaltungs- oder Betriebsnachrichten in das Ereignisprotokoll zu schreiben, und zwar zusätzlich zu vorhandenen auf dem Computer erstellten ETW-Sitzungen. Früher mussten Sie das „Microsoft.Diagnostics.Tracing.EventSource“-NuGet-Paket für diese Funktionalität verwenden. Diese Funktionalität ist nun in .NET Framework 4.6 integriert.  
  
         Sowohl das NuGet-Paket als auch .NET Framework 4.6 wurden mit den folgenden Features aktualisiert:  
  
        -   **Dynamische Ereignisse**  
  
             Ermöglichen das „spontane“ Definieren von Ereignissen, und zwar ohne das Erstellen von Ereignismethoden.  
  
        -   **Umfangreiche Nutzlasten**  
  
             Ermöglicht, dass speziell attributierte Klassen und Arrays sowie primitive Typen als eine Nutzlast übergeben werden.  
  
        -   **Aktivitätsnachverfolgung**  
  
             Löst Start- und Stoppereignisse aus, um Ereignisse zwischen ihnen mit einer ID zu kennzeichnen, die alle aktuell aktiven Aktivitäten darstellt.  
  
         Zum Unterstützen dieses Features wurde der [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True)-Klasse die überladene [Write](assetId:///M:System.Diagnostics.Tracing.EventSource.Write(System.String)?qualifyHint=False&autoUpgrade=True)-Methode hinzugefügt.  
  
-   **Windows Presentation Foundation (WPF)**  
  
    -   **HDPI-Verbesserungen**  
  
         Die HDPI-Unterstützung in WPF ist in .NET Framework 4.6 nun besser. Es wurden Änderungen an der Layoutglättung vorgenommen, um die Instanzen von Clipping in Steuerelementen mit Begrenzungen zu reduzieren. Dieses Feature ist standardmäßig nur dann aktiviert, wenn das [TargetFrameworkAttribute](assetId:///T:System.Runtime.Versioning.TargetFrameworkAttribute?qualifyHint=False&autoUpgrade=True) auf .NET 4.6 festgelegt ist.  Anwendungen, die auf frühere Versionen des Frameworks ausgerichtet sind, aber in .NET Framework 4.6 ausgeführt werden, können das neue Verhalten übernehmen, indem die folgende Zeile zum Abschnitt [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) der Datei „app.config“ hinzugefügt wird:  
  
        ```  
  
        <AppContextSwitchOverrides  
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"  
        />  
  
        ```  
  
         Sich auf mehrere Monitore erstreckende WPF-Fenster mit unterschiedlichen DPI-Einstellungen (Multi-DPI-Einrichtung) wurden nun vollständig gerendert, und zwar ohne verdunkelte Bereiche. Sie können dieses Verhalten deaktivieren, indem Sie die folgende Zeile zum `<appSettings>`-Abschnitt der Datei „app.config“ hinzufügen, um dieses neue Verhalten zu deaktivieren:  
  
        ```  
  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
  
        ```  
  
         Unterstützung für das automatische Laden des richtigen Cursors, und zwar abhängig davon, ob die DPI-Einstellung zu [System.Windows.Input.Cursor](assetId:///T:System.Windows.Input.Cursor?qualifyHint=True&autoUpgrade=True) hinzugefügt wurde.  
  
    -   **Toucheingabe ist besser**  
  
         Über [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) meldet der Kunde, dass das unvorhersehbare Verhalten der Toucheingabe in .NET Framework 4.6 behoben wurde. Der Schwellenwert für das Doppeltippen für Windows Store- und WPF-Anwendungen entspricht nun dem in Windows 8.1 und höher.  
  
    -   **Unterstützung für das transparente untergeordnete Fenster**  
  
         WPF in .NET Framework 4.6 unterstützte transparente untergeordnete Fenster in Windows 8.1 und höher. Dadurch können Sie untergeordnete Fenster, die weder viereckig noch transparent sind, in Ihren Fenstern auf oberster Ebene erstellen. Sie können dieses Feature durch Festlegen der [HwndSourceParameters.UsesPerPixelTransparency](assetId:///P:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency?qualifyHint=True&autoUpgrade=True)-Eigenschaft auf `true` aktivieren.  
  
-   **Windows Communication Foundation (WCF)**  
  
    -   **SSL-Unterstützung**  
  
         WCF unterstützt nun SSL Version TLS 1.1 und TLS 1.2 neben SSL 3.0 und TLS 1.0 beim Verwenden von NetTcp mit Transportsicherheit und Clientauthentifizierung. Es ist nun möglich, auszuwählen, welches Protokoll verwendet werden soll, oder ältere und zugleich unsicherere Protokolle zu deaktivieren. Dies kann durch das Festlegen der [SslProtocols](assetId:///P:System.ServiceModel.TcpTransportSecurity.SslProtocols?qualifyHint=False&autoUpgrade=True)-Eigenschaft oder durch das Hinzufügen der folgenden Elemente zu einer Konfigurationsdatei erfolgen.  
  
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
  
    -   **Senden von Nachrichten mithilfe von unterschiedlichen HTTP-Verbindungen**  
  
         WCF ermöglicht Benutzern nun, sicherzustellen, dass bestimmte Nachrichten unter Verwendung von zugrunde liegenden HTTP-Verbindungen gesendet wurden. Hierfür gibt es zwei Möglichkeiten:  
  
        -   **Verwenden eines Verbindungsgruppen-Namenspräfix**  
  
             Benutzer können eine Zeichenfolge angeben, die WCF als ein Präfix für den Verbindungsgruppennamen verwendet. Unter Verwendung von unterschiedlichen zugrunde liegenden HTTP-Verbindungen werden zwei Nachrichten mit unterschiedlichen Präfixen gesendet. Sie legen das Präfix fest, indem Sie ein Schlüssel-/Wert-Paar zur [Message.Properties](assetId:///P:System.ServiceModel.Channels.Message.Properties?qualifyHint=True&autoUpgrade=True)-Eigenschaft der Nachricht hinzufügen. Der Schlüssel ist „HttpTransportConnectionGroupNamePrefix“ und der Wert ist das gewünschte Präfix.  
  
        -   **Verwenden von unterschiedlichen Kanalfaktoren**  
  
             Benutzer können zudem ein Feature aktivieren, das sicherstellt, dass die mithilfe von anhand unterschiedlicher Kanalfaktoren erstellten Kanälen gesendeten Nachrichten unterschiedliche zugrunde liegende HTTP-Verbindungen verwenden. Zum Aktivieren dieses Features müssen die Benutzer die folgende `appSetting` auf `true` festlegen:  
  
            ```  
  
            <appSettings>  
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />  
            </appSettings>  
  
            ```  
  
-   **Windows Workflow Foundation (WWF)**  
  
     Sie können nun die Anzahl der Sekunden angeben, die ein Workflowdienst an einer gestörten Vorgangsanforderung festhält, wenn ein ausstehendes Nicht-Protokoll-Lesezeichen vorliegt, bevor für die Anforderung ein Timeout ausgelöst wird. Ein Nicht-Protokoll-Lesezeichen ist ein Lesezeichen, das nicht mit ausstehenden Receive-Aktivitäten verknüpft ist. Bei einigen Aktivitäten werden Nicht-Protokoll-Lesezeichen in ihrer Implementierung erstellt. Es ist daher ggf. nicht offensichtlich, ob ein Nicht-Protokoll-Lesezeichen vorhanden ist. Dazu zählen der Status und die Auswahl. Wenn Sie über einen Workflowdienst verfügen, der mit einem Statuscomputer implementiert wurde oder eine Auswahlaktivität enthält, verfügen Sie sehr wahrscheinlich über Nicht-Protokoll-Lesezeichen. Sie geben das Intervall an, indem Sie eine Zeile wie die folgende zum `appSettings`-Abschnitt Ihrer „app.config“-Datei hinzufügen:  
  
    ```  
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>  
    ```  
  
     Der Standardwert beträgt 60 Sekunden. Wenn `value` auf „0“ festgelegt ist, werden gestörte Anforderungen sofort mit einem Fehlertext abgelehnt, der wie folgt aussieht:  
  
    ```Output  
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.   
    ```  
  
     Hierbei handelt es sich um dieselbe Meldung, die Sie empfangen, wenn Sie eine Meldung in Bezug auf einen gestörten Vorgang empfangen und keine Nicht-Protokoll-Lesezeichen vorliegen.  
  
     Wenn der Wert des `FilterResumeTimeoutInSeconds`-Elements nicht null entspricht, liegen keine Nicht-Protokoll-Lesezeichen vor, und das Timeoutintervall läuft ab, wobei beim Vorgang Fehler auftreten und eine Timeoutmeldung angezeigt wird.  
  
-   **Transaktionen**  
  
     Sie können die ID für die verteilte Transaktion nun für die Transaktion einbeziehen, die eine Ausnahme verursacht hat, die von der auszulösenden [TransactionException](assetId:///T:System.Transactions.TransactionException?qualifyHint=False&autoUpgrade=True) abgeleitet wurde. Hierzu müssen Sie den folgenden Schlüssel zum `appSettings`-Abschnitt Ihrer „app.config“-Datei hinzufügen.  
  
    ```  
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>   
    ```  
  
     Der Standardwert ist `false`.  
  
-   **Netzwerk**  
  
    -   **Socket-Wiederverwendung**  
  
         Windows 10 umfasst einen neuen hochskalierbaren Netzwerkalgorithmus, der eine bessere Verwendung von Computerressourcen ermöglicht, indem lokale Ports für ausgehende TCP-Verbindungen verwendet werden. .NET Framework 4.6 unterstützt den neuen Algorithmus, wodurch .NET-Apps von diesem neuen Verhalten profitieren können. In früheren Windows-Versionen gab es einen Grenzwert für gleichzeitige, künstliche Verbindungen (für gewöhnlich 16.384, die Standardgröße des dynamischen Portbereichs), wodurch die Skalierbarkeit eines Diensts begrenzt werden konnte, indem unter Lastbedingungen eine Portauslastung verursacht werden konnte.  
  
         In .NET Framework 4.6 wurden zwei neue APIs hinzugefügt, um die Portwiederverwendung zu aktivieren, wodurch die Begrenzung von 64.000 für gleichzeitige Verbindungen effektiv aufgehoben wurde:  
  
        -   Der Wert der [SocketOptionName.ReuseUnicastPort](assetId:///T:System.Net.Sockets.SocketOptionName?qualifyHint=True&autoUpgrade=True)-Enumeration.  
  
        -   Die [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True)-Eigenschaft.  
  
         Standardmäßig lautet die [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True)-Eigenschaft `false`, sofern der Wert `HWRPortReuseOnSocketBind` des Registrierungsschlüssels `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` nicht auf „0x1“ festgelegt ist. Legen Sie zum Aktivieren der lokalen Portwiederverwendung bei HTTP-Verbindungen die [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True)-Eigenschaft auf `true` fest. Dadurch verwenden alle ausgehenden TCP-Socketverbindungen von [HttpClient](assetId:///T:System.Net.Http.HttpClient?qualifyHint=False&autoUpgrade=True) und [HttpWebRequest](assetId:///T:System.Net.HttpWebRequest?qualifyHint=False&autoUpgrade=True) die neue Windows 10-Socketoption [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), die die lokale Portwiederverwendung ermöglicht.  
  
         Entwickler, die reine Socketanwendungen schreiben, können die [SocketOptionName.ReuseUnicastPort](assetId:///T:System.Net.Sockets.SocketOptionName?qualifyHint=True&autoUpgrade=True)-Option beim Aufrufen einer Methode wie [Socket.SetSocketOption](assetId:///M:System.Net.Sockets.Socket.SetSocketOption(System.Net.Sockets.SocketOptionLevel,System.Net.Sockets.SocketOptionName,System.Byte[])?qualifyHint=True&autoUpgrade=True) angeben, sodass die ausgehenden Sockets die lokale Ports während der Bindung erneut verwenden.  
  
    -   **Unterstützung für internationale Domänennamen und PunyCode**  
  
         Der Klasse [Uri](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True) wurde die neue Eigenschaft [IdnHost](assetId:///P:System.Uri.IdnHost?qualifyHint=False&autoUpgrade=True) hinzugefügt, um internationale Domänennamen und PunyCode besser zu unterstützen.  
  
-   **Größenänderungen in Windows Forms-Steuerelementen**  
  
     Dieses Feature wurde in .NET Framework 4.6 erweitert und enthält nun die Typen [DomainUpDown](assetId:///T:System.Windows.Forms.DomainUpDown?qualifyHint=False&autoUpgrade=True), [NumericUpDown](assetId:///T:System.Windows.Forms.NumericUpDown?qualifyHint=False&autoUpgrade=True), [DataGridViewComboBoxColumn](assetId:///T:System.Windows.Forms.DataGridViewComboBoxColumn?qualifyHint=False&autoUpgrade=True), [DataGridViewColumn](assetId:///T:System.Windows.Forms.DataGridViewColumn?qualifyHint=False&autoUpgrade=True) und [ToolStripSplitButton](assetId:///T:System.Windows.Forms.ToolStripSplitButton?qualifyHint=False&autoUpgrade=True) und das Rechteck, das von der [Bounds](assetId:///P:System.Drawing.Design.PaintValueEventArgs.Bounds?qualifyHint=False&autoUpgrade=True)-Eigenschaft angegeben wird, die beim Zeichen von [UITypeEditor](assetId:///T:System.Drawing.Design.UITypeEditor?qualifyHint=False&autoUpgrade=True) verwendet wird.  
  
     Dies ist ein Opt-in-Feature. Setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element in der Anwendungskonfigurationsdatei (app.config) auf `true`, um dieses Feature zu aktivieren:  
  
    ```  
  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
  
    ```  
  
-   **Unterstützung für Codepagecodierungen**  
  
     .NET Core unterstützt primär Unicode-Codierungen und bietet standardmäßig eingeschränkte Unterstützung für Codepagecodierungen. Sie können Unterstützung für Codeseitencodierungen, die im .NET Framework zur Verfügung stellen, in .NET Core jedoch nicht unterstützt werden, hinzufügen, indem Sie die Codepagecodierungen mithilfe der Methode [Encoding.RegisterProvider](assetId:///M:System.Text.Encoding.RegisterProvider(System.Text.EncodingProvider)?qualifyHint=True&autoUpgrade=True) registrieren. Weitere Informationen finden Sie in der Dokumentation zur [System.Text.CodePagesEncodingProvider](xref:System.Text.CodePagesEncodingProvider)-Klasse.  
  
-   **.NET Native**  
  
     Windows-Apps für Windows 10, die auf .NET Core ausgerichtet und in C# oder Visual Basic geschrieben sind, können eine neue Technologie nutzen, die Apps in systemeigenen Code kompiliert statt in IL. Sie erzeugen Apps, die sich durch kürzere Start- und Ausführungszeiten auszeichnen. Weitere Informationen finden Sie unter [Kompilieren von Anwendungen mit .NET Native](../Topic/Compiling%20Apps%20with%20.NET%20Native.md). Eine Übersicht über .NET Native, in der untersucht wird, wie es sich sowohl von der JIT-Kompilierung als auch von NGEN unterscheidet und was dies für Ihren Code bedeutet, finden Sie unter [.NET Native und Kompilierung](../Topic/.NET%20Native%20and%20Compilation.md).  
  
     Ihre Apps werden beim Kompilieren mit Visual Studio 2015 standardmäßig in systemeigenen Code kompiliert. Weitere Informationen finden Sie unter [Erste Schritte mit .NET Native](../Topic/Getting%20Started%20with%20.NET%20Native.md).  
  
     Um das Debuggen von .NET Native-Apps zu unterstützen, wurden der API für nicht verwaltetes Debugging eine Reihe neuer Schnittstellen und Enumerationen hinzugefügt. Weitere Informationen finden Sie im Thema [Debuggen (Referenz zur nicht verwalteten API)](../Topic/Debugging%20\(Unmanaged%20API%20Reference\).md).  
  
-   **Open-Source-Pakete von .NET Framework**  
  
     .NET Core-Pakete wie „immutable collections“, [SIMD-APIs](http://go.microsoft.com/fwlink/?LinkID=518639) und Netzwerk-APIs wie diejenigen im [System.Net.Http](assetId:///N:System.Net.Http?qualifyHint=False&autoUpgrade=True)-Namespace stehen jetzt auf [GitHub](https://github.com/) als Open-Source-Pakete zur Verfügung. Informationen über den Codezugriff finden Sie unter [NetFx auf GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). Weitere Informationen und wie Sie zu diesen Paketen beitragen können, finden Sie unter [.NET Core und Open-Source](../Topic/.NET%20Core%20and%20Open-Source.md), [.NET-Homepage auf GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="v452"></a>   
## <a name="whats-new-in-the-net-framework-452"></a>Neuigkeiten in .NET Framework 4.5.2  
  
-   **Neue APIs für ASP.NET-Apps** Mithilfe der neuen Methoden [HttpResponse.AddOnSendingHeaders](assetId:///M:System.Web.HttpResponse.AddOnSendingHeaders(System.Action{System.Web.HttpContext})?qualifyHint=True&autoUpgrade=True) und [HttpResponseBase.AddOnSendingHeaders](assetId:///M:System.Web.HttpResponseBase.AddOnSendingHeaders(System.Action{System.Web.HttpContextBase})?qualifyHint=True&autoUpgrade=True) können Sie Antwortheader untersuchen und ändern. Zudem wird Statuscode als Antwort in die Client-App geschrieben. Erwägen Sie die Verwendung dieser Methoden anstelle der Ereignisse [PreSendRequestHeaders](assetId:///E:System.Web.HttpApplication.PreSendRequestHeaders?qualifyHint=False&autoUpgrade=True) und [PreSendRequestContent](assetId:///E:System.Web.HttpApplication.PreSendRequestContent?qualifyHint=False&autoUpgrade=True). Diese Methoden sind effizienter und zuverlässiger.  
  
     Mithilfe der [HostingEnvironment.QueueBackgroundWorkItem](assetId:///M:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem(System.Action{System.Threading.CancellationToken})?qualifyHint=True&autoUpgrade=True)-Methode können Sie kleine Arbeitsaufgaben für die Ausführung im Hintergrund planen. ASP.NET überwacht diese Aufgaben und verhindert, dass IIS den Arbeitsprozess abrupt beendet, bevor alle Hintergrund-Arbeitsaufgaben abgeschlossen wurden. Diese Methode kann nicht außerhalb von verwalteten ASP.NET-App-Domänen aufgerufen werden.  
  
     Die neuen Eigenschaften [HttpResponse.HeadersWritten](assetId:///P:System.Web.HttpResponse.HeadersWritten?qualifyHint=True&autoUpgrade=False) und [HttpResponseBase.HeadersWritten](assetId:///P:System.Web.HttpResponseBase.HeadersWritten?qualifyHint=True&autoUpgrade=False) geben boolesche Werte zurück, die angeben, ob die Antwortheader geschrieben wurden. Mit diesen Eigenschaften können Sie sicherstellen, dass API-Aufrufe wie z. B. [HttpResponse.StatusCode](assetId:///P:System.Web.HttpResponse.StatusCode?qualifyHint=True&autoUpgrade=True) (die Ausnahmen auslösen, wenn die Header geschrieben wurden) erfolgreich ausgeführt werden.  
  
-   **Größenänderungen in Windows Forms-Steuerelementen** Dieses Feature wurde erweitert. Sie können nun die systemeigene DPI-Einstellung verwenden, um die Größe von Komponenten der folgenden zusätzlichen Steuerelemente anzupassen (z. B. der Dropdownpfeil in Combofeldern):  
  
     [ComboBox](assetId:///T:System.Windows.Forms.ComboBox?qualifyHint=False&autoUpgrade=True)   
     [ToolStripComboBox](assetId:///T:System.Windows.Forms.ToolStripComboBox?qualifyHint=False&autoUpgrade=True)   
     [ToolStripMenuItem](assetId:///T:System.Windows.Forms.ToolStripMenuItem?qualifyHint=False&autoUpgrade=True)   
     [Cursor](assetId:///T:System.Windows.Forms.Cursor?qualifyHint=False&autoUpgrade=True)   
     [DataGridView](assetId:///T:System.Windows.Forms.DataGridView?qualifyHint=False&autoUpgrade=True)   
     [DataGridViewComboBoxColumn](assetId:///T:System.Windows.Forms.DataGridViewComboBoxColumn?qualifyHint=False&autoUpgrade=True)  
  
     Dies ist ein Opt-in-Feature. Setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element in der Anwendungskonfigurationsdatei (app.config) auf `true`, um dieses Feature zu aktivieren:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
-   **Neues Workflow-Feature** Ein Ressourcen-Manager, der die [EnlistPromotableSinglePhase](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification)?qualifyHint=False&autoUpgrade=True)-Methode verwendet (und daher die [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True)-Schnittstelle implementiert), kann die neue [Transaction.PromoteAndEnlistDurable](assetId:///M:System.Transactions.Transaction.PromoteAndEnlistDurable(System.Guid,System.Transactions.IPromotableSinglePhaseNotification,System.Transactions.ISinglePhaseNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True)-Methode verwenden, um Folgendes anzufordern:  
  
    -   Stufen Sie die Transaktion zu einer Microsoft Distributed Transaction Coordinator (MSDTC)-Transaktion herauf.  
  
    -   Ersetzen Sie [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True) durch eine [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True), die eine dauerhafte Eintragung darstellt, die einphasige Commits unterstützt.  
  
     Dies kann innerhalb derselben App-Domäne erfolgen, und erfordert keinen zusätzlichen nicht verwalteten Code für die Interaktion mit MSDTC für die Höherstufung. Die neue Methode kann nur aufgerufen werden, wenn ein ausstehender Aufruf von [System.Transactions](assetId:///N:System.Transactions?qualifyHint=True&autoUpgrade=True) für die [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True)`Promote`-Methode vorliegt, der von der heraufstufbaren Eintragung implementiert wird.  
  
-   **Profilerstellungsverbesserungen** Die folgenden neuen, nicht verwalteten Profilerstellungs-APIs bieten eine robustere Profilerstellung:  
  
     [COR_PRF_ASSEMBLY_REFERENCE_INFO-Struktur](../Topic/COR_PRF_ASSEMBLY_REFERENCE_INFO%20Structure.md)   
     [COR_PRF_HIGH_MONITOR-Enumeration](../Topic/COR_PRF_HIGH_MONITOR%20Enumeration.md)   
     [GetAssemblyReferences-Methode](../Topic/ICorProfilerCallback6::GetAssemblyReferences%20Method.md)   
     [GetEventMask2-Methode](../Topic/ICorProfilerInfo5::GetEventMask2%20Method.md)   
     [SetEventMask2-Methode](../Topic/ICorProfilerInfo5::SetEventMask2%20Method.md)   
     [AddAssemblyReference-Methode](../Topic/ICorProfilerAssemblyReferenceProvider::AddAssemblyReference%20Method.md)  
  
     Frühere `ICorProfiler`-Implementierungen unterstützten Lazy Loading für abhängige Assemblys. Die neue Profilerstellungs-API benötigt abhängige Assemblys, die vom Profiler zum sofortigen Laden eingefügt werden, anstatt nach der vollständigen Initialisierung der App geladen zu werden. Diese Änderung betrifft keine Benutzer der existierenden `ICorProfiler`-APIs.  
  
-   **Verbesserungen beim Debugging** Die folgenden neuen, nicht verwalteten Debugging-APIs bieten bessere Profilerintegration. Beim Debuggen von Abbildern haben Sie nun Zugriff auf die vom Profiler eingefügten Metadaten sowie auf lokale Variablen und den von ReJIT-Anfragen des Compilers eingefügten Code.  
  
     [SetWriteableMetadataUpdateMode-Methode](../Topic/ICorDebugProcess7::SetWriteableMetadataUpdateMode%20Method.md)   
     [EnumerateLocalVariablesEx-Methode](../Topic/ICorDebugILFrame4::EnumerateLocalVariablesEx%20Method.md)   
     [GetLocalVariableEx-Methode](../Topic/ICorDebugILFrame4::GetLocalVariableEx%20Method.md)   
     [GetCodeEx-Methode](../Topic/ICorDebugILFrame4::GetCodeEx%20Method.md)   
     [GetActiveReJitRequestILCode-Methode](../Topic/ICorDebugFunction3::GetActiveReJitRequestILCode%20Method.md)   
     [GetInstrumentedILMap-Methode](../Topic/ICorDebugILCode2::GetInstrumentedILMap%20Method.md)  
  
-   **Änderungen an der Ereignisablaufverfolgung** .NET Framework 4.5.2 unterstützt prozessexterne Ereignisablaufverfolgung für Windows (ETW)-basierte Aktivitätsverfolgung für eine größere Oberfläche. Auf diese Weise können Advanced Power Management (APM)-Hersteller einfache Tools zur Messung der Kosten einzelner threadübergreifender Anfragen und Aktivitäten anbieten.  Diese Ereignisse werden nur ausgelöst, wenn sie von einem ETW-Controller aktiviert wurden. Die Änderungen betreffen daher keinen zuvor geschriebenen ETW-Code oder Code, der mit deaktivierter ETW ausgeführt wird.  
  
-   **Höherstufen einer Transaktion mit entsprechender Konvertierung zu einer dauerhaften Eintragung**  
  
     [Transaction.PromoteAndEnlistDurable](assetId:///M:System.Transactions.Transaction.PromoteAndEnlistDurable(System.Guid,System.Transactions.IPromotableSinglePhaseNotification,System.Transactions.ISinglePhaseNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True) ist eine neue API, die .NET Framework 4.5.2 und 4.6 hinzugefügt wurde:  
  
    ```  
  
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,  
                                              IPromotableSinglePhaseNotification promotableNotification,  
                                              ISinglePhaseNotification enlistmentNotification,  
                                              EnlistmentOptions enlistmentOptions)  
  
    ```  
  
     Die Methode kann als Eintragung verwendet werden, die zuvor von [Transaction.EnlistPromotableSinglePhase](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification)?qualifyHint=True&autoUpgrade=True) als Antwort auf die [ITransactionPromoter.Promote](assetId:///M:System.Transactions.ITransactionPromoter.Promote?qualifyHint=True&autoUpgrade=True)-Methode erstellt wurde. Sie fragt `System.Transactions` ab, um die Transaktion zu einer MSDTC-Transaktion heraufzustufen und um die heraufstufbare Eintragung zu einer dauerhaften Eintragung zu „konvertieren“. Nach dem erfolgreichen Abschluss dieser Methode wird nicht mehr durch `System.Transactions` auf die [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True)-Schnittstelle verwiesen, und alle künftigen Benachrichtigungen gelangen zur bereitgestellten [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True)-Schnittstelle. Die entsprechende Eintrag muss als eine dauerhafte Eintragung fungieren und die Transaktionsprotokollierung und -wiederherstellung unterstützen. Details finden Sie unter [Transaction.EnlistDurable](assetId:///M:System.Transactions.Transaction.EnlistDurable(System.Guid,System.Transactions.IEnlistmentNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True). Darüber hinaus muss die Eintragung [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True) unterstützen.  Diese Methode kann *nur* während der Verarbeitung eines [ITransactionPromoter.Promote](assetId:///M:System.Transactions.ITransactionPromoter.Promote?qualifyHint=True&autoUpgrade=True)-Aufrufs aufgerufen werden. Wenn dies nicht der Fall ist, wird eine [TransactionException](assetId:///T:System.Transactions.TransactionException?qualifyHint=False&autoUpgrade=True)-Ausnahme ausgelöst.  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="v451"></a>   
## <a name="whats-new-in-the-net-framework-451"></a>Neuigkeiten in .NET Framework 4.5.1  
 **Updates für April 2014**:  
  
-   [Visual Studio 2013 Update 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) enthält Updates für die Vorlagen der portablen Klassenbibliothek, um die folgenden Szenarien zu unterstützen:  
  
    -   Sie können die Windows-Runtime APIs in portablen Bibliotheken einsetzen, die Windows 8.1, Windows Phone 8.1 und Windows Phone Silverlight 8.1 als Ziel verwenden.  
  
    -   Sie können XAML (Windows.UI.XAML-Typen) in portablen Bibliotheken einsetzen, wenn Sie Windows 8.1 oder Windows Phone 8.1 als Ziel verwenden. Die folgenden XAML-Vorlagen werden unterstützt: Leere Seite, Ressourcenverzeichnis, Steuerelement mit Vorlagen und Benutzersteuerelement.  
  
    -   Sie können eine portable Komponente für Windows-Runtime (.winmd-Datei) für den Einsatz in Store-Apps erstellen, die Windows 8.1 und Windows Phone 8.1 als Ziel verwenden.  
  
    -   Sie können eine Windows Store- oder Windows Phone Store-Klassenbibliothek wie eine portable Klassenbibliothek neu zuweisen.  
  
     Weitere Informationen zu diesen Änderungen finden Sie unter [Portable Klassenbibliothek](../Topic/Cross-Platform%20Development%20with%20the%20Portable%20Class%20Library.md).  
  
-   Der .NET Framework-Inhaltssatz enthält nun Dokumentation für .NET Native, eine Vorkompilierungstechnologie für die Erstellung und Bereitstellung von Windows-Apps. .NET Native kompiliert Ihre Apps direkt zu nativem Code anstatt zu einer Intermediate Language (IL) und erzielt dadurch eine bessere Leistung. Details hierzu finden Sie unter [Kompilieren von Anwendungen mit .NET Native](../Topic/Compiling%20Apps%20with%20.NET%20Native.md).  
  
-   Die [.NET Framework-Verweisquelle](http://referencesource.microsoft.com/) bietet ein neues Browsererlebnis und erweiterte Funktionen. Sie können den Quellcode von .NET Framework online durchsuchen, die [Referenz herunterladen](http://referencesource.microsoft.com/download.html), um diese offline anzuzeigen, und den Quellcode (inklusive Patches und Updates) beim Debuggen schrittweise durchlaufen. Weitere Informationen finden Sie im Blogeintrag [A new look for .NET Reference Source](http://blogs.msdn.com/b/dotnet/archive/2014/02/24/a-new-look-for-net-reference-source.aspx).  
  
 .NET Framework 4.5.1 enthält die folgenden neuen Kernfunktionen und -optimierungen:  
  
-   Automatische Bindungsumleitung für Assemblys. Ab Visual Studio 2013 können beim Kompilieren einer App, die auf .NET Framework 4.5.1 ausgerichtet ist, Bindungsumleitungen zur App-Konfigurationsdatei hinzugefügt werden, wenn die App oder ihre Komponenten sich auf mehrere Versionen derselben Assembly beziehen. Sie können diese Funktion auch für Projekte aktivieren, die frühere Versionen von .NET Framework als Ziel haben. Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren und Deaktivieren der Bindungsumleitung](../Topic/How%20to:%20Enable%20and%20Disable%20Automatic%20Binding%20Redirection.md).  
  
-   Fähigkeit, Diagnoseninformationen zu erfassen, um Entwicklern zu helfen, die Leistung von Server- und Cloud-Anwendungen zu verbessern. Weitere Informationen finden Sie unter den Methoden [WriteEventWithRelatedActivityId](assetId:///M:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId(System.Int32,System.Guid,System.Object[])?qualifyHint=False&autoUpgrade=True) und [WriteEventWithRelatedActivityIdCore](assetId:///M:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore(System.Int32,System.Guid*,System.Int32,System.Diagnostics.Tracing.EventSource.EventData*)?qualifyHint=False&autoUpgrade=True) der [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True)-Klasse.  
  
-   Fähigkeit, während einer Garbage Collection den großen Objektheap (Large Object Heap, LOH) explizit zu komprimieren. Weitere Informationen finden Sie unter der [GCSettings.LargeObjectHeapCompactionMode](assetId:///P:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?qualifyHint=True&autoUpgrade=True)-Eigenschaft.  
  
-   Zusätzliche Leistungsverbesserungen wie ASP.NET-App-Unterbrechung, Multikern-JIT-Verbesserungen und schnellere App-Starts nach einem .NET Framework-Update. Ausführliche Informationen finden Sie in der [.NET Framework 4.5.1-Ankündigung](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx) und im Blogbeitrag [ASP.NET App Suspend](http://blogs.msdn.com/b/dotnet/archive/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting.aspx).  
  
 Verbesserungen für Windows Forms-Anwendungen:  
  
-   Größenänderungen in Windows Forms-Steuerelementen. Sie können die systemeigene DPI-Einstellung verwenden, um die Größe von Komponenten von Steuerelementen anzupassen (z. B. die Symbole in einem Eigenschaftenraster), indem Sie diese Funktion über einen Eintrag in der Anwendungskonfigurationsdatei (app.config) für Ihre App aktivieren. Dieses Feature wird zurzeit für die folgenden Windows Forms-Steuerelemente unterstützt:  
  
     [PropertyGrid](assetId:///T:System.Windows.Forms.PropertyGrid?qualifyHint=False&autoUpgrade=True)   
     [TreeView](assetId:///T:System.Windows.Forms.TreeView?qualifyHint=False&autoUpgrade=True)   
     Einige Aspekte von [DataGridView](assetId:///T:System.Windows.Forms.DataGridView?qualifyHint=False&autoUpgrade=True) (unter [Neue Features in 4.5.2](#v452) finden Sie weitere unterstützte Steuerelemente)  
  
     Fügen Sie ein neues \<appSettings>-Element zur Konfigurationsdatei (app.config) hinzu und setzen Sie das `EnableWindowsFormsHighDpiAutoResizing`-Element auf `true`, um dieses Feature zu aktivieren:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
 Zu Verbesserungen beim Debuggen Ihrer .NET Framework-Apps in Visual Studio 2013 zählen u. a.:  
  
-   Rückgabewerte im Visual Studio-Debugger. Wenn Sie eine verwaltete App in Visual Studio 2013 debuggen, werden Rückgabetypen und -werte für Methoden im Fenster „Auto“ angezeigt. Diese Informationen sind für Desktop-, Windows Store- und Windows Phone-Apps verfügbar. Weitere Informationen finden Sie unter [Überprüfen von Rückgabewerten der Methodenaufrufe](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) in der MSDN Library.  
  
-   „Bearbeiten und fortfahren“ für 64-Bit-Apps. Visual Studio 2013 unterstützt die Funktion „Bearbeiten und fortfahren“ für verwaltete 64-Bit-Apps für Desktops, Windows Store und Windows Phone. Die vorhandenen Einschränkungen bleiben für 32-Bit- und 64-Bit-Apps wirksam (siehe den letzten Abschnitt des Artikels [Unterstützte Codeänderungen (C#)](http://msdn.microsoft.com/library/ms164927\(v=vs.120\).aspx)).  
  
-   Async-bewusstes Debuggen. Um das Debuggen asynchroner Apps in Visual Studio 2013 zu vereinfachen, wird der Infrastrukturcode, der von Compilern zur Unterstützung asynchronen Programmierens bereitgestellt wird, in der Aufrufliste ausgeblendet. Ebenfalls erfolgt dort eine Verkettung mit logisch übergeordneten Rahmen, sodass der logischen Programmausführung übersichtlicher gefolgt werden kann. Ein Aufgabenfenster ersetzt das Fenster "Parallele Aufgaben" und zeigt Aufgaben an, die sich auf einen bestimmten Haltepunkt beziehen. Außerdem werden alle anderen Aufgaben angezeigt, die momentan aktiv oder in der App geplant sind. Informationen zu diesem Feature finden Sie im Abschnitt „Async-bewusstes Debuggen“ in der [.NET Framework 4.5.1-Ankündigung](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
-   Bessere Ausnahmeunterstützung für Windows-Runtime-Komponenten. In Windows 8.1 behalten Ausnahmen, die in Windows Store-Apps auftreten, Informationen zum Fehler, der die Ausnahme ausgelöst hat, sogar über Sprachgrenzen bei. Informationen zu diesem Feature finden Sie im Abschnitt „Windows Store-App-Entwicklung“ in der [.NET Framework 4.5.1-Ankündigung](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
 Ab Visual Studio 2013 können Sie zusätzlich das [Managed Profile Guided Optimization Tool (Mpgo.exe)](../Topic/Mpgo.exe%20\(Managed%20Profile%20Guided%20Optimization%20Tool\).md) verwenden, um sowohl Windows 8.x Store-Apps als auch Desktop-Apps zu optimieren.  
  
 Informationen zu neuen Funktionen in ASP.NET 4.5.1 finden Sie unter [ASP.NET 4.5.1 und Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) auf der ASP.NET-Website.  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="core"></a>   
## <a name="whats-new-in-the-net-framework-45"></a>Neuigkeiten in .NET Framework 4.5  
  
### <a name="core-new-features-and-improvements"></a>Wichtige neue Features und Verbesserungen  
  
-   Weniger Systemneustarts durch Erkennen und Schließen von .NET Framework 4-Anwendungen bei der Bereitstellung. Siehe [Reduzieren von Systemneustarts bei .NET Framework 4.5-Installationen](../Topic/Reducing%20System%20Restarts%20During%20.NET%20Framework%204.5%20Installations.md).  
  
-   Unterstützung von mehr als 2 Gigabyte (GB) großen Arrays auf 64-Bit-Plattformen. Sie können die Funktion in der Anwendungskonfiguration aktivieren. Siehe das [\<gcAllowVeryLargeObjects>-Element](../Topic/%3CgcAllowVeryLargeObjects%3E%20Element.md), das auch andere Einschränkungen zur Objekt- und Arraygröße auflistet.  
  
-   Bessere Leistung durch Garbage Collection im Hintergrund für Server. Wenn Sie die Garbage Collection auf dem Server in .NET Framework 4.5 verwenden, wird die Garbage Collection im Hintergrund automatisch aktiviert. Siehe im Abschnitt „Garbage Collection auf dem Server im Hintergrund“ des Themas [Grundlagen der Garbage Collection](../Topic/Fundamentals%20of%20Garbage%20Collection.md).  
  
-   Just-In-Time (JIT)-Kompilierung im Hintergrund zur Verbesserung der Anwendungsleistung, die optional auf Mehrkernprozessoren verfügbar ist. Siehe [ProfileOptimization](assetId:///T:System.Runtime.ProfileOptimization?qualifyHint=False&autoUpgrade=True).  
  
-   Festlegen der Zeit, die das Modul für reguläre Ausdrücke zum Auflösen eines regulären Ausdrucks bis zum Timeout benötigen darf. Siehe die [Regex.MatchTimeout](assetId:///P:System.Text.RegularExpressions.Regex.MatchTimeout?qualifyHint=True&autoUpgrade=True)-Eigenschaft.  
  
-   Definieren der Standardkultur für eine Anwendungsdomäne. Siehe die [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True)-Klasse.  
  
-   Konsolenunterstützung für Unicode-Codierung (UTF-16). Siehe die [Console](assetId:///T:System.Console?qualifyHint=False&autoUpgrade=True)-Klasse.  
  
-   Unterstützung für die Versionierung kulturabhängiger Zeichenfolgenreihenfolgen und -vergleichsdaten. Siehe die [SortVersion](assetId:///T:System.Globalization.SortVersion?qualifyHint=False&autoUpgrade=True)-Klasse.  
  
-   Bessere Leistung beim Abrufen von Ressourcen. Siehe [Verpacken und Bereitstellen von Ressourcen](../Topic/Packaging%20and%20Deploying%20Resources%20in%20Desktop%20Apps.md).  
  
-   Verbesserte ZIP-Komprimierung zur Reduzierung der Größe einer komprimierten Datei. Siehe den [System.IO.Compression](assetId:///N:System.IO.Compression?qualifyHint=True&autoUpgrade=True)-Namespace.  
  
-   Anpassen eines Reflektionskontexts zum Überschreiben des Standardreflektionsverhaltens mit der [CustomReflectionContext](assetId:///T:System.Reflection.Context.CustomReflectionContext?qualifyHint=False&autoUpgrade=True)-Klasse.  
  
-   Unterstützung der Version 2008 des IDNA-Standards (Internationalized Domain Names in Applications) beim Verwenden der [System.Globalization.IdnMapping](assetId:///T:System.Globalization.IdnMapping?qualifyHint=True&autoUpgrade=True)-Klasse in Windows 8.  
  
-   Delegieren des Zeichenfolgenvergleichs an das Betriebssystem, wobei Unicode 6.0 implementiert wird, wenn .NET Framework in Windows 8 verwendet wird. Bei Ausführung auf anderen Plattformen verwendet .NET Framework eigene Zeichenfolgenvergleichsdaten, wobei Unicode 5.x. implementiert wird. Siehe die [String](assetId:///T:System.String?qualifyHint=False&autoUpgrade=True)-Klasse und den Abschnitt „Hinweise“ in der [SortVersion](assetId:///T:System.Globalization.SortVersion?qualifyHint=False&autoUpgrade=True)-Klasse.  
  
-   Berechnen der Hashcodes für Zeichenfolgen pro Anwendungsdomäne. Siehe [\<UseRandomizedStringHashAlgorithm>-Element](../Topic/%3CUseRandomizedStringHashAlgorithm%3E%20Element.md).  
  
-   Typspiegelung unterstützt eine Teilung zwischen den Klassen [Type](assetId:///T:System.Type?qualifyHint=False&autoUpgrade=True) und [TypeInfo](assetId:///T:System.Reflection.TypeInfo?qualifyHint=False&autoUpgrade=True). Siehe [Reflektion in .NET Framework für Windows Store-Apps](../Topic/Reflection%20in%20the%20.NET%20Framework%20for%20Windows%20Store%20Apps.md).  
  
### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)  
 In .NET Framework 4.5 bietet das Managed Extensibility Framework (MEF) folgende neuen Features:  
  
-   Unterstützung von generischen Typen.  
  
-   Konventionsbasiertes Programmiermodell zum Erstellen von Teilen auf Grundlage von Namenskonventionen anstelle von Attributen.  
  
-   Mehrere Bereiche.  
  
-   Eine Teilmenge von MEF, die Sie verwenden können, wenn Sie Windows 8.x Store-Apps erstellen. Diese Teilmenge steht als [herunterladbares Paket](http://go.microsoft.com/fwlink/?LinkId=256238) in der NuGet Gallery zur Verfügung. Öffnen Sie zum Installieren des Pakets das Projekt in Visual Studio, wählen Sie im Menü **Projekt** die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Composition`-Paket.  
  
 Weitere Informationen finden Sie unter [Übersicht über das Managed Extensibility Framework](../Topic/Managed%20Extensibility%20Framework%20\(MEF\).md).  
  
### <a name="asynchronous-file-operations"></a>Asynchrone Dateivorgänge  
 In .NET Framework 4.5 wurden neue asynchrone Features den Programmiersprachen C# und Visual Basic hinzugefügt. Diese Funktionen ergänzen ein aufgabenbasiertes Modell zum Ausführen von asynchronen Vorgängen. Verwenden Sie dieses neue Modell mithilfe der asynchronen Methoden in den E/A-Klassen. Siehe [Asynchrone Datei-E/A](../Topic/Asynchronous%20File%20I-O.md).  
  
<a name="tools"></a>   
### <a name="tools"></a>Tools  
 In .NET Framework 4.5 können Sie mit dem Resource File Generator-Tool (Resgen.exe) aus einer RESOURCES-Datei, die in einer .NET Framework-Assembly eingebettet ist, eine RESW-Datei für Windows 8.x Store-Apps erstellen. Weitere Informationen finden Sie unter [Resgen.exe (Resource File Generator)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md).  
  
 Mit Managed Profile Guided Optimization (Mpgo.exe) können Sie die Anwendungsstartzeit, die Arbeitsspeicherauslastung (Workingsetgröße) und den Durchsatz verbessern, indem Sie die Assemblys systemeigener Abbilder optimieren. Das Befehlszeilentool generiert Profildaten für Anwendungsassemblys systemeigener Abbilder. Siehe [Mpgo.exe (verwaltetes, profilgesteuertes Optimierungstool)](../Topic/Mpgo.exe%20\(Managed%20Profile%20Guided%20Optimization%20Tool\).md). Ab Visual Studio 2013 können Sie zusätzlich „Mpgo.exe“ verwenden, um sowohl Windows 8.x Store-Apps als auch Desktop-Apps zu optimieren.  
  
<a name="parallel"></a>   
### <a name="parallel-computing"></a>Parallele Computervorgänge  
 .NET Framework 4.5 stellt mehrere neue Features und Verbesserungen für parallele Berechnung bereit. Dazu gehören leistungsfähigere, erweiterte Steuerungsmöglichkeiten, verbesserte Unterstützung für asynchrone Programmierung, eine neue Datenflussbibliothek und verbesserte Unterstützung für paralleles Debuggen und Leistungsanalyse. Siehe den Eintrag zu den [Neuerungen hinsichtlich der Parallelität in .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) im Blog zur parallelen Programmierung mit .NET.  
  
<a name="web"></a>   
### <a name="web"></a>Web  
 In ASP.NET 4.5 und 4.5.1 wurden die Modellbindung für Webformulare, WebSocket-Unterstützung, asynchrone Handler, Leistungserweiterungen und viele weitere Funktionen hinzugefügt. Weitere Informationen finden Sie in den folgenden Ressourcen:  
  
-   [ASP.NET 4.5 und Visual Studio 2012](../Topic/ASP.NET%20Core%20and%20Visual%20Studio%202015.md) in der MSDN Library.  
  
-   [ASP.NET 4.5.1 und Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) auf der ASP.NET-Website.  
  
<a name="networking"></a>   
### <a name="networking"></a>Netzwerk  
 .NET Framework 4.5 stellt eine neue Programmierschnittstelle für HTTP-Anwendungen bereit. Weitere Informationen finden Sie in den neuen Namespaces [System.Net.Http](assetId:///N:System.Net.Http?qualifyHint=True&autoUpgrade=True) und [System.Net.Http.Headers](assetId:///N:System.Net.Http.Headers?qualifyHint=True&autoUpgrade=True).  
  
 Unterstützt wird jetzt auch eine neue Programmierschnittstelle, um eine WebSocket-Verbindung mithilfe der vorhandenen [HttpListener](assetId:///T:System.Net.HttpListener?qualifyHint=False&autoUpgrade=True)-Klasse und verknüpften Klassen anzunehmen und mit dieser zu interagieren. Weitere Informationen finden Sie unter dem neuen [System.Net.WebSockets](assetId:///N:System.Net.WebSockets?qualifyHint=False&autoUpgrade=True)-Namespace und der [HttpListener](assetId:///T:System.Net.HttpListener?qualifyHint=False&autoUpgrade=True)-Klasse.  
  
 Darüber hinaus bietet .NET Framework 4.5 folgende Netzwerkverbesserungen:  
  
-   RFC-kompatible URI-Unterstützung. Weitere Informationen finden Sie in der [Uri](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True)-Klasse und verknüpften Klassen.  
  
-   Unterstützung für IDN (Internationalized Domain Name)-Analysen. Weitere Informationen finden Sie in der [Uri](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True)-Klasse und verknüpften Klassen.  
  
-   Unterstützung für E-Mail-Adressen-Internationalisierung (EAI). Weitere Informationen finden Sie unter dem [System.Net.Mail](assetId:///N:System.Net.Mail?qualifyHint=False&autoUpgrade=True)-Namespace.  
  
-   Verbesserte IPv6-Unterstützung. Weitere Informationen finden Sie unter dem [System.Net.NetworkInformation](assetId:///N:System.Net.NetworkInformation?qualifyHint=False&autoUpgrade=True)-Namespace.  
  
-   Dual-Modus-Socket-Unterstützung. Weitere Informationen finden Sie unter den Klassen [Socket](assetId:///T:System.Net.Sockets.Socket?qualifyHint=False&autoUpgrade=True) und [TcpListener](assetId:///T:System.Net.Sockets.TcpListener?qualifyHint=False&autoUpgrade=True).  
  
<a name="client"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 In .NET Framework 4.5 wurde Windows Presentation Foundation (WPF) in vielen Bereichen überarbeitet und verbessert. Dazu gehören:  
  
-   Das neue [Ribbon](assetId:///T:System.Windows.Controls.Ribbon.Ribbon?qualifyHint=False&autoUpgrade=True)-Steuerelement, mit dem Sie eine Menüband-Benutzeroberfläche implementieren können, die eine Symbolleiste für den Schnellzugriff, ein Anwendungsmenü und Registerkarten hostet.  
  
-   Die neue [INotifyDataErrorInfo](assetId:///T:System.ComponentModel.INotifyDataErrorInfo?qualifyHint=False&autoUpgrade=True)-Schnittstelle, die die synchrone und asynchrone Datenüberprüfung unterstützt.  
  
-   Neue Features für die Klassen [VirtualizingPanel](assetId:///T:System.Windows.Controls.VirtualizingPanel?qualifyHint=False&autoUpgrade=True) und [Dispatcher](assetId:///T:System.Windows.Threading.Dispatcher?qualifyHint=False&autoUpgrade=True).  
  
-   Verbesserte Leistung beim Anzeigen großer Datengruppierungen sowie durch den Zugriff auf Auflistungen in Nicht-UI-Threads.  
  
-   Datenbindung an statische Eigenschaften, Datenbindung an benutzerdefinierte Typen, die die [ICustomTypeProvider](assetId:///T:System.Reflection.ICustomTypeProvider?qualifyHint=False&autoUpgrade=True)-Schnittstelle implementieren, und Abrufen von Datenbindungsinformationen aus einem Bindungsausdruck.  
  
-   Neupositionierung von Daten bei Wertänderung (Live-Strukturierung).  
  
-   Überprüfen einer möglicherweise getrennten Verbindung des Datenkontexts für einen Elementcontainer.  
  
-   Festlegen der Zeit, die zwischen Eigenschaftenänderungen und Datenquellenupdates verstreichen soll.  
  
-   Verbesserte Unterstützung für das Implementieren schwacher Ereignismuster. Zudem können Ereignisse jetzt Markuperweiterungen akzeptieren.  
  
<a name="windows_communication_foundation"></a>   
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
 Um das Schreiben und Verwalten von WCF-Anwendungen (Windows Communication Foundation) zu erleichtern, wurden in .NET Framework 4.5 folgende Features hinzugefügt:  
  
-   Vereinfachung von generierten Konfigurationsdateien.  
  
-   Unterstützung für Contract-First-Entwicklung.  
  
-   Leichteres Konfigurieren des ASP.NET-Kompatibilitätsmodus.  
  
-   Änderungen in den standardmäßigen Transporteigenschaftswerten, um die Wahrscheinlichkeit zu reduzieren, dass Sie sie festlegen müssen.  
  
-   Aktualisierungen der [XmlDictionaryReaderQuotas](assetId:///T:System.Xml.XmlDictionaryReaderQuotas?qualifyHint=False&autoUpgrade=True)-Klasse, um die Wahrscheinlichkeit zu reduzieren, dass Sie Kontingente für XML-Wörterbuchreader manuell konfigurieren müssen.  
  
-   Validierung von WCF-Konfigurationsdateien von Visual Studio als Teil des Buildprozesses, sodass Sie Konfigurationsfehler erkennen können, bevor Sie die Anwendung ausführen.  
  
-   Neue Unterstützung für asynchrones Streaming.  
  
-   Neue HTTPS-Protokollzuordnung zur leichteren Bereitstellung eines Endpunkts über HTTPS mit IIS (Internetinformationsdienste).  
  
-   Generieren von Metadaten in einem einzelnen WSDL-Dokument durch Anfügen von `?singleWSDL` an die Dienst-URL.  
  
-   Websockets-Unterstützung für echte bidirektionale Kommunikation über die Ports 80 und 443 mit TCP-transportähnlichen Leistungsmerkmalen.  
  
-   Unterstützung für das Konfigurieren von Diensten im Code.  
  
-   XML-Editor-QuickInfos.  
  
-   Unterstützung der [ChannelFactory](assetId:///T:System.ServiceModel.ChannelFactory?qualifyHint=False&autoUpgrade=True)-Zwischenspeicherung.  
  
-   Unterstützung für die Komprimierung binärer Encoder.  
  
-   Unterstützung für einen UDP-Transport, mit dem Entwickler "Fire and Forget" (Auslösen und Vergessen)-Messaging-Dienste schreiben können. Ein Client sendet eine Nachricht an einen Dienst und erwartet von diesem keine Antwort.  
  
-   Unterstützung mehrerer Authentifizierungsmodi auf einem einzelnen WCF-Endpunkt beim Verwenden von HTTP-Transport und -Transportsicherheit.  
  
-   Unterstützung für WCF-Dienste, die internationale Domänennamen (IDNs) verwenden.  
  
 Weitere Informationen finden Sie unter [Neues in Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).  
  
<a name="windows_workflow_foundation"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 .NET Framework 4.5 bietet viele neue Features für Windows Workflow Foundation (WF), so z. B.:  
  
-   Zustandsautomatworkflows, die zunächst als Teil von .NET Framework 4.0.1 ([.NET Framework 4 Platform-Update 1](http://go.microsoft.com/fwlink/?LinkID=215092)) eingeführt wurden. Dieses Update umfasste mehrere neue Klassen und Aktivitäten, sodass Entwickler Zustandsautomatworkflows erstellen konnten. Diese Klassen und Aktivitäten wurden für .NET Framework 4.5 aktualisiert und umfassen nun Folgendes:  
  
    -   Festlegen von Haltepunkten für Zustände.  
  
    -   Kopieren und Einfügen von Übergängen im Workflow Designer.  
  
    -   Designerunterstützung für das Erstellen von freigegebenen Triggerübergängen.  
  
    -   Aktivitäten zum Erstellen von Zustandsautomatworkflows, einschließlich [StateMachine](assetId:///T:System.Activities.Statements.StateMachine?qualifyHint=False&autoUpgrade=True), [State](assetId:///T:System.Activities.Statements.State?qualifyHint=False&autoUpgrade=True) und [Transition](assetId:///T:System.Activities.Statements.Transition?qualifyHint=False&autoUpgrade=True).  
  
-   Verbesserte Workflow Designer-Funktionen, z. B.:  
  
    -   Verbesserte Workflowsuchfunktionen in Visual Studio, einschließlich **Schnellsuche** und **In Dateien suchen**.  
  
    -   Automatisches Erstellen einer Sequenzaktivität, wenn eine zweite untergeordnete Aktivität zu einer Containeraktivität hinzugefügt wird, und Einschließen beider Aktivitäten in die Sequenzaktivität.  
  
    -   Schwenk-Unterstützung zur Änderung des sichtbaren Teils eines Workflows ohne die Verwendung von Bildlaufleisten.  
  
    -   Die neue Ansicht **Dokumentgliederung**, die die Gliederungsansicht der Workflowkomponenten in einer Baumstruktur anzeigt und die Auswahl einer Komponente in der Ansicht **Dokumentgliederung** ermöglicht.  
  
    -   Hinzufügen von Anmerkungen zu Aktivitäten.  
  
    -   Definieren und Verarbeiten von Aktivitätsdelegaten mit dem Workflow Designer.  
  
    -   Automatisches Verbinden und Einfügen für Aktivitäten und Übergänge in Zustandsautomaten- und Flussdiagrammworkflows.  
  
-   Speichern der Ansichtszustandsinformationen für einen Workflow in einem einzelnen Element in der XAML-Datei, sodass Sie die Ansichtszustandsinformationen leicht finden und bearbeiten können.  
  
-   Eine NoPersistScope-Containeraktivität, damit untergeordnete Aktivitäten nicht beibehalten werden.  
  
-   Unterstützung von C#-Ausdrücken:  
  
    -   Visual Basic-Workflowprojekte verwenden Visual Basic-Ausdrücke, und C#-Workflowprojekte verwenden C#-Ausdrücke.  
  
    -   C#-Workflowprojekte, die in Visual Studio 2010 erstellt wurden und Visual Basic-Ausdrücke verwenden, sind mit C#-Workflowprojekten, die C#-Ausdrücke verwenden, kompatibel.  
  
-   Versionsverwaltungserweiterungen:  
  
    -   Die neue [WorkflowIdentity](assetId:///T:System.Activities.WorkflowIdentity?qualifyHint=False&autoUpgrade=True)-Klasse, die eine Zuordnung zwischen einer beibehaltenen Workflowinstanz und ihrer Workflowdefinition bietet.  
  
    -   Parallele Ausführung mehrerer Workflowversionen im selben Host, einschließlich [WorkflowServiceHost](assetId:///T:System.ServiceModel.Activities.WorkflowServiceHost?qualifyHint=False&autoUpgrade=True).  
  
    -   Die Änderbarkeit der Definition einer beibehaltenen Workflowinstanz im Rahmen eines dynamischen Updates.  
  
-   Contract-First-Workflowdienstentwicklung, die das automatische Generieren von Aktivitäten zur Übereinstimmung mit einem vorhandenen Dienstvertrag unterstützt.  
  
 Weitere Informationen finden Sie unter [Neues in Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).  
  
<a name="tailored"></a>   
### <a name="net-for-windows-8x-store-apps"></a>.NET für Windows 8.x Store-Apps  
 Windows 8.x Store-Apps werden für bestimmte Formfaktoren entworfen und nutzen die Leistungsfähigkeit des Windows-Betriebssystems. Eine Teilmenge von .NET Framework 4.5 oder 4.5.1 kann mithilfe von C# oder Visual Basic zum Erstellen von Windows 8.x Store-Apps für Windows verwendet werden. Diese Teilmenge wird .NET for Windows 8.x Store genannt und in einer [Übersicht](http://go.microsoft.com/fwlink/?LinkId=228491) im Windows Developer Center erläutert.  
  
<a name="portable"></a>   
### <a name="portable-class-libraries"></a>Portable Klassenbibliotheken  
 Mit dem Projekt „Portable Klassenbibliothek“ in Visual Studio 2012 (und Folgeversionen) können Sie verwaltete Assemblys, die auf mehreren .NET Framework-Plattformen ausgeführt werden können, schreiben und erstellen. Bei Verwenden eines Projekts des Typs „Portable Klassenbibliothek“ wählen Sie die Zielplattformen (wie Windows Phone- und .NET for Windows 8.x Store-Apps). Die verfügbaren Typen und Member im Projekt werden automatisch auf die allgemeinen Typen und Member dieser Plattformen beschränkt. Weitere Informationen finden Sie in der Dokumentation zur [Portablen Klassenbibliothek](../Topic/Cross-Platform%20Development%20with%20the%20Portable%20Class%20Library.md).  
  
## <a name="see-also"></a>Siehe auch  
 [.NET Framework und Out-of-Band-Releases](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Neues in Visual Studio 2013](http://msdn.microsoft.com/library/bb386063\(v=vs.120\).aspx)   
 [ASP.NET 4.5.1 und Webtools für Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094)   
 [ASP.NET und Visual Studio für Web](../Topic/ASP.NET%20and%20Visual%20Studio%20for%20Web.md)   
 [Neues in Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173)   
 [Neues in Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176)   
 [Neues in Visual C++](http://msdn.microsoft.com/library/hh409293\(v=vs.120\).aspx)

