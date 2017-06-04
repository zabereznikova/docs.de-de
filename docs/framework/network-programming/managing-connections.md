---
title: "Verwalten von Verbindungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Internet, Verbindungen"
  - "HTTP, Klassen für Verbindungsherstellung"
  - "Anfordern von Daten aus dem Internet, Verbindungen"
  - "Senden von Daten, Verbindungen"
  - "Empfangen von Daten, Verbindungen"
  - "ServicePoint-Klasse, Infos über ServicePoint-Klasse"
  - "Antwort auf Internetanforderung, Verbindungen"
  - "Verbindungen [.NET Framework], Klassen"
  - "Netzwerkressourcen, Verbindungen"
  - "Downloaden von Internetressourcen, Verbindungen"
  - "ServicePointManager-Klasse, Infos über ServicePointManager-Klasse"
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Verwalten von Verbindungen
Anwendungen, die HTTP verwenden, um an Datenressourcen herzustellen, können die <xref:System.Net.ServicePoint>\- und <xref:System.Net.ServicePointManager>\-Klassen von .NET Framework verwenden, um Verbindungen zum Internet zu verwalten und zu reproduzieren, optimalen Umfang und Leistung zu erzielen.  
  
 Die **ServicePoint**\-Klasse bietet eine Anwendung mit einem Endpunkt, an den die Anwendung Zugriff auf Internetressourcen herstellen kann.  Jedes **ServicePoint** enthält Informationen, mit deren Hilfe Verbindungen mit einem Internetserver optimieren, indem sie Optimierungsinformationen zwischen Verbindungen gemeinsam, um die Leistung zu verbessern.  
  
 Jedes **ServicePoint** wird durch einen URI \(Uniform Resource Identifier\) identifiziert und wird entsprechend den Schemabezeichner\- und \-Hostfragmenten des URI kategorisiert.  Beispielsweise würde dieselbe Instanz **ServicePoint** Anforderungen an den URI http:\/\/www.contoso.com\/index.htm und http:\/\/www.contoso.com\/news.htm?date\=today bereitstellen, da sie den gleichen Schemabezeichner \(HTTP\) und die Hostfragmente \(www.contoso.com\).  Wenn die Anwendung bereits eine dauerhafte Verbindung zum Server www.contoso.com verfügt, wird diese Verbindung, um beide Anforderungen abzurufen und wird vermieden, zwei Verbindungen zu erstellen.  
  
 **ServicePointManager** ist eine statische Klasse, die die Erstellung und Zerstörung von **ServicePoint**\-Instanzen verwaltet.  **ServicePointManager** erstellt **ServicePoint**, wenn die Anwendung um eine Internetressource anfordert, die nicht in der Auflistung vorhandener **ServicePoint**\-Instanzen ist.  **ServicePoint**\-Instanzen werden zerstört, wenn sie ihre maximale Leerlaufzeit überschritten haben, oder wenn die Anzahl der vorhandenen **ServicePoint**\-Instanzen die maximale Anzahl von Instanzen **ServicePoint** für die Anwendung überschreitet.  Sie können die standardmäßige maximale Leerlaufzeit und die maximale Anzahl von **ServicePoint** \-Instanzen steuern, indem Sie die <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> und <xref:System.Net.ServicePointManager.MaxServicePoints%2A>\-Eigenschaften auf **ServicePointManager** festlegen.  
  
 Die Anzahl von Verbindungen zwischen einem Client und einem Server kann dramatische Auswirkungen auf Anwendungsdurchsatz haben.  Standardmäßig verwendet eine Anwendung mithilfe der <xref:System.Net.HttpWebRequest>\-Klasse maximal zwei persistenten Verbindungen zu einem angegebenen Server, aber Sie können die maximale Anzahl von Verbindungen pro Anwendung festlegen.  
  
> [!NOTE]
>  Die Grenzen der Spezifikation HTTP\/1.1 die Anzahl von Verbindungen von Anwendung zu Anwendung zwei Verbindungen pro Server.  
  
 Die optimale Anzahl von Verbindungen hängt von den Istzuständen ab, in der die Anwendung ausgeführt wird.  Die Erhöhung der Anzahl von Verbindungen, die für die Anwendung verfügbar sind, wirkt sich möglicherweise nicht die Anwendungsleistung.  Sie die Auswirkungen von mehr Verbindungen bestimmen, Ausführungsleistungsnachweise beim variierenden Anzahl der Verbindungen.  Sie können die Anzahl von Verbindungen, die eine Anwendung mit, die statische <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>\-Eigenschaft auf der **ServicePointManager**\-Klasse an der Anwendungsinitialisierung ändert, wie im folgenden Codebeispiel gezeigt ändern.  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 Das Ändern der **ServicePointManager.DefaultConnectionLimit**\-Eigenschaft beeinflusst nicht zuvor **ServicePoint** initialisierte Instanzen.  Im folgenden Code wird das Ändern des Verbindungslimits auf vorhandenen **ServicePoint** für den Server http:\/\/www.contoso.com zum Wert, der in `newLimit` gespeichert wird.  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## Siehe auch  
 [Verbindungsgruppierung](../../../docs/framework/network-programming/connection-grouping.md)   
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)