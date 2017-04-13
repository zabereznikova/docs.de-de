---
title: "Programmieren austauschbarer Protokolle | Microsoft Docs"
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
  - "Herunterladen von Internetressourcen, austauschbare Protokolle"
  - "WebRequest-Klasse, austauschbare Protokolle"
  - "Antwort auf Internetanforderung, austauschbare Protokolle"
  - "WebResponse-Klasse, austauschbare Protokolle"
  - "Senden von Daten, austauschbare Protokolle"
  - "Netzwerkressourcen, austauschbare Protokolle"
  - "Internet, austauschbare Protokolle"
  - "Programmieren austauschbarer Protokolle"
  - "Austauschbare Protokolle, programmieren"
  - "Anfordern von Daten aus dem Internet, austauschbare Protokolle"
  - "Empfangen von Daten, austauschbare Protokolle"
  - "Protokolle, austauschbare"
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Programmieren austauschbarer Protokolle
Abstrakte <xref:System.Net.WebRequest> und die <xref:System.Net.WebResponse>\-Klassen stellen die Basis für austauschbare Protokolle bereit.  Durch die Ableitung von protokollspezifischen Klassen von <xref:System.Net.WebRequest> und von <xref:System.Net.WebResponse> berechnet, kann eine Anwendung Daten aus einer Internetressource anfordern und die Antwort lesen, ohne das Protokoll anzugeben, das verwendet wird.  
  
 Bevor Sie protokollspezifisches <xref:System.Net.WebRequest> erstellen können, müssen Sie die entsprechenden Erstellungsmethode registrieren.  Verwenden Sie die statische <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29>\-Methode von <xref:System.Net.WebRequest>, um einen <xref:System.Net.WebRequest> Nachfolger zu registrieren, um einen Satz von Anforderungen zu einem bestimmten Internet\-Schema, zu einem Schema und einem Server oder in einem Schema, auf einen Server und einen Pfad zu bearbeiten.  
  
 In den meisten Fällen können Sie auch Daten mithilfe der Methoden und Eigenschaften der <xref:System.Net.WebRequest>\-Klasse senden und empfangen.  Wenn Sie jedoch auf protokollspezifische Eigenschaften zugreifen müssen, können Sie <xref:System.Net.WebRequest> verwendete zu einer bestimmten Instanz der abgeleiteten Klasse.  
  
 Um austauschbare Protokolle zu nutzen, müssen die <xref:System.Net.WebRequest> Nachfolger eine standardmäßige Anforderung\-undAntwort Transaktion bereitstellen nicht die protokollspezifische Eigenschaften muss festgelegt werden.  Beispielsweise stellt die <xref:System.Net.HttpWebRequest>\-Klasse, die die <xref:System.Net.WebRequest>\-Klasse für HTTP implementiert, eine `GET` Anforderung standardmäßig und gibt <xref:System.Net.HttpWebResponse> zurück, die den Stream enthält, der vom Webserver zurückgegeben wird.  
  
## Siehe auch  
 [Ableiten von WebRequest](../../../docs/framework/network-programming/deriving-from-webrequest.md)   
 [Ableiten von WebResponse](../../../docs/framework/network-programming/deriving-from-webresponse.md)   
 [Netzwerkprogrammierung in .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Gewusst wie: Typumwandlung für ein WebRequest in zugriffsprotokollspezifische Eigenschaften](../../../docs/framework/network-programming/how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)