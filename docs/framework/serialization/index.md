---
title: "Serialisierung | Microsoft Docs"
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
  - "Binäre Serialisierung"
  - "Objekte, Serialisieren"
  - "Serialisierung"
  - "Serialisieren von Objekten"
  - "XML-Serialisierung, Definition"
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Serialisierung
Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann.Das Gegenstück zur Serialisierung ist die Deserialisierung, die einen Stream in ein Objekt konvertiert.Zusammen ermöglichen es diese Prozesse, dass Daten einfach gespeichert und übertragen werden.  
  
 .NET Framework zeichnet sich durch zwei Serialisierungstechnologien aus:  
  
-   Bei der binären Serialisierung wird die Typtreue beibehalten. Dies ist nützlich, um den Zustand eines Objekts zwischen verschiedenen Aufrufen einer Anwendung zu speichern.So können Sie z. B. ein Objekt für unterschiedliche Anwendungen freigeben, indem Sie es in die Zwischenablage serialisieren.Sie können ein Objekt in einen Stream, einen Datenträger, den Arbeitsspeicher, über das Netzwerk usw. serialisieren.Die Serialisierung wird vom Remotingsystem dazu verwendet, um Objekte "als Wert" von einem Computer bzw. einer Anwendungsdomäne an einen anderen Computer bzw. eine andere Anwendungsdomäne zu übergeben.  
  
-   Bei der XML\-Serialisierung werden nur öffentliche Eigenschaften und Felder serialisiert, und die Typtreue wird nicht beibehalten.Dies ist hilfreich, wenn Daten bereitgestellt oder benutzt werden sollen, ohne die Anwendung, welche die Daten verwendet, zu beschränken.Da XML ein offener Standard ist, stellt XML eine attraktive Möglichkeit für den Datenaustausch im Internet dar.Ebenso ist SOAP ein offener Standard und damit auch eine attraktive Alternative.  
  
## In diesem Abschnitt  
 [Gewusst\-wie\-Themen zur Serialisierung](../../../docs/framework/serialization/serialization-how-to-topics.md)  
 Enthält eine Liste mit Links zu den Gewusst\-wie\-Themen in diesem Abschnitt.  
  
 [Binäre Serialisierung](../../../docs/framework/serialization/binary-serialization.md)  
 Beschreibt den binären Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.  
  
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 Beschreibt den XML\- und SOAP\-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.  
  
 [Serialisierungstools](../../../docs/framework/serialization/serialization-tools.md)  
 Diese Tools sind hilfreich bei der Entwicklung von Serialisierungscode.  
  
 [Serialisierungsbeispiele](../../../docs/framework/serialization/serialization-samples.md)  
 In den Beispielen wird veranschaulicht, wie die Serialisierung stattfindet.  
  
## Referenz  
 <xref:System.Runtime.Serialization>  
 Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.  
  
 <xref:System.Xml.Serialization>  
 Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im XML\-Format verwendet werden können.  
  
## Verwandte Abschnitte  
 [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58)  
 Beschreibt die verschiedenen Kommunikationsverfahren, die in .NET Framework für die Remotekommunikation zur Verfügung stehen.  
  
 [Advanced Development Technologies](http://msdn.microsoft.com/de-de/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
 Enthält Links zu weiteren Informationen über anspruchsvolle Aufgaben und Verfahren für die Entwicklung in .NET Framework.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/de-de/1e64af78-d705-4384-b08d-591a45f4379c)  
 Stellt Themen bereit, in denen beschrieben und erklärt wird, wie mit ASP.NET erstellte XML\-Webdienste programmiert werden.