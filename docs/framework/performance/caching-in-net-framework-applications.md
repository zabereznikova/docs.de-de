---
title: "Caching in .NET Framework Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ASP.NET caching"
  - "caching [.NET Framework]"
  - "caching [ASP.NET]"
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
caps.latest.revision: 26
author: "tdykstra"
ms.author: "tdykstra"
manager: "wpickett"
caps.handback.revision: 26
---
# Caching in .NET Framework Applications
Mithilfe der Zwischenspeicherung können Daten für einen schnellen Zugriff im Arbeitsspeicher gespeichert werden.  Wenn erneut auf die Daten zugegriffen wird, können Anwendungen die Daten aus dem Cache anstatt aus der ursprünglichen Quelle abrufen.  Dadurch kann die Leistung und Skalierbarkeit verbessert werden.  Zudem bietet die Zwischenspeicherung den Vorteil, dass Daten auch zur Verfügung stehen, wenn die Datenquelle vorübergehend nicht verfügbar ist.  
  
 .NET Framework stellt Funktionen für die Zwischenspeicherung bereit, die Sie verwenden können, um die Leistung und die Skalierbarkeit von Windows\-Clients und Serveranwendungen zu verbessern. Dies schließt auch ASP.NET mit ein.  
  
> [!NOTE]
>  In [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] und früheren Versionen hat ASP.NET eine Cacheimplementierung im Arbeitsspeicher im <xref:System.Web.Caching>\-Namespace bereitgestellt.  In früheren Versionen von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] war das Zwischenspeichern nur im <xref:System.Web>\-Namespace verfügbar und erforderte daher eine Abhängigkeit von ASP.NET\-Klassen.  In .NET Framework 4 enthält der <xref:System.Runtime.Caching>\-Namespace APIs, die für Web\- und für Nicht\-Webanwendungen geeignet sind.  
  
## Zwischenspeichern von Daten  
 Sie können Informationen zwischenspeichern, indem Sie Klassen im <xref:System.Runtime.Caching>\-Namespace verwenden.  Die Klassen für die Zwischenspeicherung in diesem Namespace stellen folgende Funktionen bereit:  
  
-   Abstrakte Typen, die die Grundlage für das Erstellen benutzerdefinierter Cacheimplementierungen bilden.  
  
-   Eine konkrete Objektcacheimplementierung im Arbeitsspeicher.  
  
 Die abstrakte Basisklasse für die Zwischenspeicherung \(<xref:System.Runtime.Caching.ObjectCache>\) definiert die folgenden Aufgaben für die Zwischenspeicherung:  
  
-   Erstellen und Verwalten von Cacheeinträgen.  
  
-   Angeben von Laufzeit\- und Entfernungsinformationen.  
  
-   Initiieren von Ereignissen, die als Reaktion auf Änderungen in den Cacheeinträgen ausgelöst werden.  
  
 Die <xref:System.Runtime.Caching.MemoryCache>\-Klasse ist eine Objektcacheimplementierung im Speicher der <xref:System.Runtime.Caching.ObjectCache>\-Klasse.  Sie können die <xref:System.Runtime.Caching.MemoryCache>\-Klasse für die meisten Aufgaben der Zwischenspeicherung verwenden.  
  
> [!NOTE]
>  Die <xref:System.Runtime.Caching.MemoryCache>\-Klasse ist dem ASP.NET\-Cacheobjekt nachempfunden, das im <xref:System.Web.Caching>\-Namespace definiert ist.  Daher ist die interne Logik vergleichbar mit der Zwischenspeicherungslogik, die in früheren Versionen von ASP.NET bereitgestellt wurde.  
  
 Ein Beispiel zum Verwenden der Zwischenspeicherung in einer WPF\-Anwendung finden Sie unter [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF\-Anwendung](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md).  
  
## Zwischenspeicherung in ASP.NET\-Anwendungen  
 Die Zwischenspeicherungsklassen im <xref:System.Runtime.Caching>\-Namespace stellen Funktionen zum Zwischenspeichern von Daten in ASP.NET bereit.  
  
> [!NOTE]
>  Wenn für die Anwendung als Zielversion [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] oder älter festgelegt wurde, müssen Sie die Zwischenspeicherungsklassen verwenden, die im <xref:System.Web.Caching>\-Namespace definiert sind.  Weitere Informationen finden Sie unter [ASP.NET Caching Overview](../Topic/ASP.NET%20Caching%20Overview.md).  
  
> [!NOTE]
>  Wenn Sie neue Anwendungen entwickeln, wird empfohlen, die <xref:System.Runtime.Caching.MemoryCache>\-Klasse zu verwenden.  Die API, die im <xref:System.Runtime.Caching>\-Namespace bereitgestellt wird, gleicht der API im <xref:System.Web.Caching.Cache>\-Namespace.  Daher wird Ihnen die API vertraut sein, wenn Sie die Zwischenspeicherung bereits in früheren Versionen von ASP.NET verwendet haben. Ein Beispiel zur Verwendung der Zwischenspeicherung in ASP.NET\-Anwendungen finden Sie unter [Walkthrough: Caching Application Data in ASP.NET](../Topic/Walkthrough:%20Caching%20Application%20Data%20in%20ASP.NET.md).  
  
### Ausgabecache  
 Um manuell Anwendungsdaten zwischenzuspeichern, können Sie die <xref:System.Runtime.Caching.MemoryCache>\-Klasse in ASP.NET verwenden. ASP.NET unterstützt auch die Ausgabezwischenspeicherung, die die generierte Ausgabe von Seiten, Steuerelementen und HTTP\-Antworten im Arbeitsspeicher speichert.  Sie können die Ausgabezwischenspeicherung deklarativ auf einer ASP.NET\-Webseite oder über die Einstellungen in der Datei Web.config konfigurieren.  Weitere Informationen finden Sie unter [outputCache\-Element für caching \(ASP.NET\-Einstellungsschema\)](http://msdn.microsoft.com/de-de/47cd2b47-316f-4dfd-bbf8-539be3066fee).  
  
 Mit ASP.NET können Sie die Ausgabezwischenspeicherung erweitern, indem sie benutzerdefinierte Ausgabecacheanbieter erstellen.  Wenn Sie benutzerdefinierte Anbieter verwenden, können Sie die zwischengespeicherten Inhalte auf anderen Speichergeräten speichern, z. B. auf Festplatten, in einem Cloud\-Speicher oder mithilfe verteilter Cachemodule.  Um einen benutzerdefinierten Ausgabecacheanbieter zu erstellen, erstellen Sie eine Klasse, die von der <xref:System.Web.Caching.OutputCacheProvider>\-Klasse abgeleitet ist, und konfigurieren die Anwendung so, dass sie den benutzerdefinierten Ausgabecacheanbieter verwendet.  
  
## Zwischenspeicherung in WCF REST\-Diensten  
 Bei WCF REST\-Diensten können Sie mit .NET Framework die Vorteile der deklarativen Ausgabezwischenspeicherung nutzen, die in ASP.NET verfügbar ist. Auf diese Weise können Sie Antworten der WCF REST\-Dienstvorgänge zwischenspeichern.  Wenn ein Benutzer eine HTTP GET\-Anforderung an einen Dienst sendet, der für eine Zwischenspeicherung konfiguriert ist, sendet ASP.NET die zwischengespeicherte Antwort zurück, und die Dienstmethode wird nicht aufgerufen.  Sobald der Cache abgelaufen ist, wird die Dienstmethode erneut aufgerufen und die Antwort erneut zwischengespeichert, wenn ein Benutzer das nächste Mal eine HTTP GET\-Anforderung sendet.  
  
 Mit .NET Framework können Sie auch eine bedingte HTTP GET\-Zwischenspeicherung implementieren.  In REST\-Szenarien werden eine bedingte HTTP GET\-Anforderungen häufig von Diensten verwendet, intelligente HTTP\-Zwischenspeicherung zu implementieren, wie in der beschrieben [HTTP\-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=165800).  Weitere Informationen finden Sie unter [Zwischenspeichern der Unterstützung für WCF\-Web\-HTTP Dienste](http://go.microsoft.com/fwlink/?LinkId=184598).  
  
## Erweitern der Zwischenspeicherung in .NET Framework  
 Die Zwischenspeicherung in .NET Framework wurde so entworfen, dass Erweiterungen möglich sind.  Die <xref:System.Runtime.Caching.ObjectCache>\-Klasse ermöglicht es Ihnen, auch eine benutzerdefinierte Cacheimplementierung zu erstellen.  Diese Klasse stellt Member bereit, die für alle verwalteten Anwendungen verfügbar sind, einschließlich Windows Forms, Windows Presentation Foundation \(WPF\) und Windows Communications Foundation \(WCF\).  Möglicherweise möchten Sie eine Cacheklasse erstellen, die einen anderen Speichermechanismus verwendet oder eine präzise Kontrolle der Cachevorgänge gestattet.  
  
 Zum Erweitern der Zwischenspeicherung können Sie wie folgt vorgehen:  
  
-   Erstellen Sie eine benutzerdefinierte Klasse, die von der <xref:System.Runtime.Caching.ObjectCache>\-Klasse abgeleitet ist, und stellen Sie dann eine benutzerdefinierte Cacheimplementierung in der abgeleiteten Klasse bereit.  
  
-   Erstellen Sie eine Klasse, die von der <xref:System.Runtime.Caching.MemoryCache>\-Klasse abgeleitet ist, und bearbeiten oder erweitern Sie die abgeleitete Klasse.  Ein Beispiel, wie Sie dafür, finden Sie ausführt [Zwischenspeichern\-Anwendungsdaten mithilfe mehrerer Cache\-Objekten in einer ASP.NET\-Anwendung](http://blogs.msdn.com/aspnetue/archive/2010/03/22/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application.aspx).  
  
-   Erstellen Sie eine Klasse, die von der <xref:System.Web.Caching.OutputCacheProvider>\-Klasse abgeleitet ist, und konfigurieren Sie die Anwendung so, dass sie den benutzerdefinierten Ausgabecacheanbieter verwendet.  
  
 Weitere Informationen finden Sie im Eintrag [Erweiterbares Ausgabecaching mit ASP.NET 4 \(In VS 2010 und .NET 4.0\-Reihe\)](http://go.microsoft.com/fwlink/?LinkId=185772) für Scotts Blog Guthries.  
  
## Siehe auch  
 <xref:System.Runtime.Caching.ObjectCache>   
 <xref:System.Runtime.Caching.MemoryCache>   
 [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF\-Anwendung](../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)   
 [Walkthrough: Caching Application Data in ASP.NET](../Topic/Walkthrough:%20Caching%20Application%20Data%20in%20ASP.NET.md)