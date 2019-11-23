---
title: Caching in .NET Framework-Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- ASP.NET caching
- caching [.NET Framework]
- caching [ASP.NET]
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
ms.openlocfilehash: 2a0d138151722a76133da45c166c51d7f3bb0a31
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428190"
---
# <a name="caching-in-net-framework-applications"></a>Caching in .NET Framework-Anwendungen
Das Zwischenspeichern ermöglicht es Ihnen, Daten für schnellen Zugriff im Arbeitsspeicher zu speichern. Wenn erneut auf die Daten zugegriffen wird, erhalten Anwendungen die Daten aus dem Zwischenspeicher, anstatt sie aus der Originalquelle abzurufen. Dies kann die Leistung und Skalierbarkeit verbessern. Darüber hinaus macht das Zwischenspeichern Daten verfügbar, wenn die Datenquelle vorübergehend nicht verfügbar ist.  
  
 .NET Framework bietet Funktionen zum Zwischenspeichern, die Sie verwenden können, um die Leistung und Skalierbarkeit von Windows Client- und Serveranwendungen, einschließlich ASP.NET, zu verbessern.  
  
> [!NOTE]
> In the .NET Framework 3.5 and earlier versions, ASP.NET provided an in-memory cache implementation in the <xref:System.Web.Caching> namespace. In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes. In .NET Framework 4 enthält der <xref:System.Runtime.Caching>-Namespace APIs, die für Web- und nicht-Webanwendungen konzipiert sind.  
  
## <a name="caching-data"></a>Zwischenspeichern von Daten  
 Sie können Informationen mithilfe von Klassen im <xref:System.Runtime.Caching>-Namespace zwischenspeichern. Die zwischenspeichernden Klassen in diesem Namespace stellen die folgenden Features zur Verfügung:  
  
- Abstrakte Typen, die die Grundlage für das Erstellen von benutzerdefinierten Cache-Implementierungen bereitstellen.  
  
- Eine konkrete speicherinterne Cache-Implementierung von Objekten.  
  
 Die abstrakte zwischenspeichernde Basisklasse (<xref:System.Runtime.Caching.ObjectCache>) definiert die folgenden zwischenspeichernden Aufgaben:  
  
- Erstellen und Verwalten von Cacheeinträgen.  
  
- Angeben von Ablauf und Entfernung von Informationen.  
  
- Auslösen von Ereignissen, die als Reaktion auf Änderungen in Cacheeinträgen ausgelöst werden.  
  
 Die <xref:System.Runtime.Caching.MemoryCache>-Klasse ist eine speicherinterne Cache-Implementierung eines Objekts der <xref:System.Runtime.Caching.ObjectCache>-Klasse. Sie können die <xref:System.Runtime.Caching.MemoryCache>-Klasse für die meisten Cachingaufgaben verwenden.  
  
> [!NOTE]
> Die <xref:System.Runtime.Caching.MemoryCache>-Klasse wird für das ASP.NET-Cacheobjekt modelliert, das im <xref:System.Web.Caching>-Namespace definiert wird. Aus diesem Grund ist die interne Cachinglogik mit der Logik vergleichbar, die in früheren Versionen von ASP.NET bereitgestellt wurde.  
  
 Ein Beispiel zum Verwenden der Zwischenspeicherung in WPF-Anwendungen finden Sie unter [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung](../wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md).  
  
## <a name="caching-in-aspnet-applications"></a>Zwischenspeichern in ASP.NET-Anwendungen  
 Die zwischenspeichernden Klassen im <xref:System.Runtime.Caching>-Namespace bieten Funktionen zum Zwischenspeichern von Daten in ASP.NET.  
  
> [!NOTE]
> If your application targets the .NET Framework 3.5 or earlier, you must use the caching classes that are defined in the <xref:System.Web.Caching> namespace. Weitere Informationen finden Sie unter [Übersicht über die ASP.NET-Zwischenspeicherung](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).  
  
> [!NOTE]
> Wenn Sie neue Anwendungen entwickeln, empfehlen wir die Verwendung der <xref:System.Runtime.Caching.MemoryCache>-Klasse. Die API, die im <xref:System.Runtime.Caching>-Namespace bereitgestellt wird, ist wie die API, die im <xref:System.Web.Caching.Cache>-Namespace bereitgestellt wird. Aus diesem Grund wird Ihnen die API vertraut sein, wenn Sie den Zwischenspeicher bereits in früheren Versionen von ASP.NET verwendet haben. Ein Beispiel zum Verwenden der Zwischenspeicherung in ASP.NET-Anwendungen finden Sie unter [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in ASP.NET](https://docs.microsoft.com/previous-versions/ff477235(v=vs.100)).  
  
### <a name="output-caching"></a>Ausgabezwischenspeicherung  
 Sie können die <xref:System.Runtime.Caching.MemoryCache>-Klasse in ASP.NET verwenden, um manuell Anwendungsdaten zwischenzuspeichern. ASP.NET unterstützt auch das Zwischenspeichern der Ausgabe, das die generierte Ausgabe von Seiten, Steuerelementen und HTTP-Antworten im Arbeitsspeicher speichert. Sie können das Zwischenspeichern der Ausgabe deklarativ in einer ASP.NET-Webseite oder mithilfe von Einstellungen in der Datei „Web.config“ konfigurieren. Weitere Information finden Sie unter [OutputCache-Element für Caching (ASP.NET-Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms228124(v=vs.100)).  
  
 Mit ASP.NET können Sie das Zwischenspeichern der Ausgabe durch das Erstellen von benutzerdefinierten Ausgabecacheanbietern erweitern. Indem Sie benutzerdefinierte Anbieter verwenden, können Sie zwischengespeicherte Inhalte mit anderen Speichergeräten wie Festplatten, Cloudspeichern und verteilter Cache-Engines speichern. Erstellen Sie eine Klasse, die aus der <xref:System.Web.Caching.OutputCacheProvider>-Klasse abgeleitet ist, und konfigurieren Sie die Anwendung zur Verwendung des benutzerdefinierten Ausgabecacheanbieters, um einen benutzerdefinierten Ausgabecacheanbieter zu erstellen.  
  
## <a name="caching-in-wcf-rest-services"></a>Zwischenspeichern in WCF REST-Diensten  
 Durch .NET Framework können Sie für WCF REST-Dienste den deklarativen Ausgabecache nutzen, der nicht in ASP.NET verfügbar ist. Auf diese Weise können Sie Antworten der WCF REST-Dienstvorgänge zwischenspeichern. Wenn ein Benutzer eine HTTP GET-Anforderung an den Dienst sendet, der zum Zwischenspeichern konfiguriert ist, sendet ASP.NET die zwischengespeicherte Antwort zurück, und die Dienstmethode wird nicht aufgerufen. Wenn der Cache abgelaufen ist, wird beim nächsten Senden einer HTTP GET-Anforderung durch einen Benutzer die Dienstmethode aufgerufen und die Antwort erneut zwischengespeichert.  
  
 Mit .NET Framework können Sie auch den bedingten HTTP GET-Zwischenspeicher implementieren. In REST-Szenarios wird eine bedingte HTTP GET-Anforderung häufig von Diensten verwendet, um die intelligente HTTP-Zwischenspeicherung zu implementieren. Dies ist in der [HTTP-Spezifikation](https://www.w3.org/Protocols/rfc2616/rfc2616.html) beschrieben. Weitere Information finden Sie unter [Cacheunterstützung für WCF-Web-HTTP-Dienste](../wcf/feature-details/caching-support-for-wcf-web-http-services.md).  
  
## <a name="extending-caching-in-the-net-framework"></a>Erweitern von Caching in .NET Framework  
 Die Zwischenspeicherung in .NET Framework ist erweiterbar. Mit der <xref:System.Runtime.Caching.ObjectCache>-Klasse können Sie eine benutzerdefinierte Cacheimplementierung erstellen. Diese Klasse enthält Elemente, die auf allen verwalteten Anwendungen, einschließlich Windows Forms, Windows Presentation Foundation (WPF) und Windows Communications Foundation (WCF), verfügbar sind. Sie können dies vornehmen, um eine Cacheklasse zu erstellen, die einen anderen Speichermechanismus verwendet, oder wenn Sie eine präzise Kontrolle über Cachevorgänge erhalten möchten.  
  
 Zur Erweiterung der Zwischenspeicherung können Sie Folgendes tun:  
  
- Erstellen Sie eine benutzerdefinierte Klasse, die aus der <xref:System.Runtime.Caching.ObjectCache>-Klasse abgeleitet ist, und geben Sie eine benutzerdefinierte Cacheimplementierung in der abgeleiteten Klasse an.  
  
- Erstellen Sie eine Klasse, die aus der <xref:System.Runtime.Caching.MemoryCache>-Klasse abgleitet ist, und erweitern Sie die abgeleitete Klasse, oder passen Sie sie an. Ein Beispiel hierzu finden Sie unter [Zwischenspeichern von Anwendungsdaten mithilfe mehrerer Cacheobjekte in einer ASP.NET-Anwendung](https://blogs.msdn.microsoft.com/aspnetue/2010/03/22/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application/).  
  
- Erstellen Sie eine Klasse, die aus der <xref:System.Web.Caching.OutputCacheProvider>-Klasse abgeleitet ist, und konfigurieren Sie die Anwendung zur Verwendung des benutzerdefinierten Ausgabecacheanbieters.  
  
 Weitere Informationen finden Sie im Eintrag [Extensible Output Caching with ASP.NET 4 (VS 2010 and .NET 4.0 Series)](https://weblogs.asp.net/scottgu/extensible-output-caching-with-asp-net-4-vs-2010-and-net-4-0-series) (Erweiterbare Ausgabezwischenspeicherung in ASP.NET 4 (VS 2010 und .NET 4.0-Serie)) auf Scott Guthries Blog.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching.MemoryCache>
- [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung](../wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
- [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in ASP.NET](https://docs.microsoft.com/previous-versions/ff477235(v=vs.100))
