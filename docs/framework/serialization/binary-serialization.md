---
title: "Bin&#228;re Serialisierung | Microsoft Docs"
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
  - "Binäre Serialisierung, Info zu Serialisierung"
  - "Deserialisierung"
  - "Serialisierung, Info zu Serialisierung"
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Bin&#228;re Serialisierung
Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden.Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird.Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.  
  
 Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden.Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben.Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen.In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der vom .NET Framework bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.  
  
> [!NOTE]
>  Der Zustand eines UTF\-8\- oder UTF\-7\-codierten Objekts wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.  
  
## In diesem Abschnitt  
 [Serialisierungskonzepte](../../../docs/framework/serialization/serialization-concepts.md)  
 Erläutert zwei Szenarien, in denen die Serialisierung sinnvoll eingesetzt werden kann: wenn Daten im Speicher beibehalten werden sollen und wenn Objekte über Anwendungsdomänen hinweg übergeben werden.  
  
 [Einfache Serialisierung](../../../docs/framework/serialization/basic-serialization.md)  
 Beschreibt, wie die Binärdatei und SOAP\-Formatierungsprogramme verwendet werden, um Objekte zu serialisieren.  
  
 [Selektive Serialisierung](../../../docs/framework/serialization/selective-serialization.md)  
 Beschreibt, wie verhindert wird, dass einige Member einer Klasse serialisiert werden.  
  
 [Benutzerdefinierte Serialisierung](../../../docs/framework/serialization/custom-serialization.md)  
 Beschreibt, wie mithilfe der <xref:System.Runtime.Serialization.ISerializable>\-Schnittstelle die Serialisierung für eine Klasse angepasst wird.  
  
 [Schritte im Serialisierungsprozess](../../../docs/framework/serialization/steps-in-the-serialization-process.md)  
 Beschreibt die einzelnen Serialisierungsschritte, die ausgeführt werden, wenn die <xref:System.Runtime.Serialization.Formatter.Serialize%2A>\-Methode für ein Formatierungsprogramm aufgerufen wird.  
  
 [Versionstolerante Serialisierung](../../../docs/framework/serialization/version-tolerant-serialization.md)  
 Erklärt, wie serialisierbare Typen erstellt werden, die im Lauf der Zeit modifiziert werden können, ohne dass dies zur Folge hat, dass Anwendungen Ausnahmen auslösen.  
  
 [Serialisierungsrichtlinien](../../../docs/framework/serialization/serialization-guidelines.md)  
 Stellt einige allgemeine Richtlinien zur Entscheidung der Frage bereit, wann ein Objekt serialisiert werden sollte.  
  
## Referenz  
 <xref:System.Runtime.Serialization>  
 Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.  
  
## Verwandte Abschnitte  
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 Beschreibt den XML\-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.  
  
 [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)  
 Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von Code befolgt werden sollten, mit dem Serialisierungen durchgeführt werden.  
  
 [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58)  
 Beschreibt die verschiedenen Kommunikationsverfahren, die in .NET Framework für die Remotekommunikation zur Verfügung stehen.  
  
 [XML Web Services Created Using ASP.NET and XML Web Service Clients](http://msdn.microsoft.com/de-de/1e64af78-d705-4384-b08d-591a45f4379c)  
 Stellt Themen bereit, in denen beschrieben und erklärt wird, wie mit ASP.NET erstellte XML\-Webdienste programmiert werden.