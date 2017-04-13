---
title: "Marshallen als Wert | Microsoft Docs"
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
  - "Binäre Serialisierung, Als Wert gemarshallt"
  - "Als Wert gemarshallte Objekte"
  - "Serialisierung, Als Wert gemarshallt"
ms.assetid: ee91e8f0-92e0-4732-8015-d17dee154be1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Marshallen als Wert
Objekte sind in nur der Anwendungsdomäne gültig, in der sie erstellt werden.Jeder Versuch, das Objekt als Parameter zu übergeben oder es als Ergebnis zurückzugeben, schlägt fehl, sofern das Objekt nicht von [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic) abgeleitet wurde oder mit dem Attribut [Serializable](frlrfSystemSerializableAttributeClassTopic) markiert ist.Wenn das Objekt als **Serializable** markiert ist, wird das Objekt automatisch serialisiert, von einer Anwendungsdomäne in die andere transportiert und dann deserialisiert, um in der zweiten Anwendungsdomäne eine genaue Kopie des Objekts zu erstellen.Dieser Vorgang wird in der Regel "Mashallen als Wert" genannt.  
  
 Wenn ein Objekt von **MarshalByRefObject** abgeleitet ist, wird statt des Objekts ein Objektverweis von einer Anwendungsdomäne einer anderen Anwendungsdomäne übergeben.Sie können auch ein von **MarshalByRefObject** abgeleitetes Objekt als **Serializable** markieren.Wenn dieses Objekt in Verbindung mit Remoting verwendet wird, übernimmt das für die Serialisierung zuständige Formatierungsprogramm, das mit einem Ersatzselektor \([SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic)\) vorkonfiguriert wurde, die Steuerung des Serialisierungsvorgangs und ersetzt alle von [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic) abgeleiteten Objekte durch einen Proxy.Wenn kein [](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic) gegeben ist, hält sich die Serialisierungsarchitektur an die Standardregeln für die Serialisierung, die unter [Schritte im Serialisierungsprozess](../../../docs/framework/serialization/steps-in-the-serialization-process.md) beschrieben sind.  
  
## Siehe auch  
 [Serialisierungskonzepte](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)