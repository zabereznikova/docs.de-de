---
title: "Vorgehensweise: Segmentieren serialisierter Daten | Microsoft Docs"
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
  - "Binäre Serialisierung, Segmentieren von Daten"
  - "Binäre Serialisierung, Beispiele"
  - "Segmentieren serialisierter Daten"
  - "Datensegmentierung"
  - "Segmentieren von umfangreichen Datensätzen"
  - "Serialisierung, Segmentieren von Daten"
  - "Serialisierung, Beispiele"
ms.assetid: 22f1b818-7e0d-428a-8680-f17d6ebdd185
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Vorgehensweise: Segmentieren serialisierter Daten
Beim Senden großer Datasätze in Webdienstnachrichten treten die zwei Probleme auf:  
  
1.  Ein großes Workingset \(Arbeitsspeicher\) aufgrund der Pufferung durch das Serialisierungsmodul  
  
2.  Unregelmäßige Bandbreitennutzung aufgrund von 33 % Inflation nach der Base64\-Codierung  
  
 Zur Lösung dieser Probleme implementieren Sie die <xref:System.Xml.Serialization.IXmlSerializable>\-Schnittstelle, um die Serialisierung und Deserialisierung zu steuern.Implementieren Sie insbesondere die <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>\-Methode und die <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>\-Methode, um die Daten zu segmentieren.  
  
### So implementieren Sie serverseitige Segmentierung:  
  
1.  Die Webmethode muss die ASP.NET\-Pufferung auf dem Servercomputer deaktivieren und einen Typ zurückgeben, der <xref:System.Xml.Serialization.IXmlSerializable> implementiert.  
  
2.  Der Typ, der <xref:System.Xml.Serialization.IXmlSerializable> implementiert, segmentiert die Daten in der <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>\-Methode.  
  
### So implementieren Sie clientseitige Verarbeitung  
  
1.  Ändern Sie die Webmethode auf dem Clientproxy so, dass der Typ zurückgegeben wird, der <xref:System.Xml.Serialization.IXmlSerializable> implementiert.Sie können <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> verwenden, um diesen Vorgang automatisch auszuführen, aber dies wird hier nicht beschrieben.  
  
2.  Implementieren Sie die <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>\-Methode, um den segmentierten Datenstream zu lesen und die Bytes auf den Datenträger zu schreiben.Diese Implementierung löst auch Statusereignisse aus, die von einem grafischen Steuerelement, z. B. einer Statusleiste, verwendet werden können.  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht die Webmethode auf dem Client, mit der die ASP.NET\-Pufferung deaktiviert wird.Es zeigt zudem die clientseitige Implementierung der <xref:System.Xml.Serialization.IXmlSerializable>\-Schnittstelle, die die Daten in der <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>\-Methode segmentiert.  
  
 [!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
 [!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## Kompilieren des Codes  
  
-   In diesem Code werden die folgenden Namespaces verwendet: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization> und <xref:System.Xml.Schema>.  
  
## Siehe auch  
 [Benutzerdefinierte Serialisierung](../../../docs/framework/serialization/custom-serialization.md)