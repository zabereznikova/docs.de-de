---
title: "Schritte im Serialisierungsprozess | Microsoft Docs"
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
  - "Binäre Serialisierung, Schritte"
  - "Serialisierung, Schritte"
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Schritte im Serialisierungsprozess
Wenn die [Serialize](frlrfSystemRuntimeSerializationFormatterClassSerializeTopic)\-Methode für ein [Formatierungsprogramm](frlrfSystemRuntimeSerializationFormatterClassTopic) aufgerufen wird, erfolgt die Objektserialisierung nach den folgenden Regeln:  
  
-   Es wird überprüft, ob das Formatierungsprogramm über einen Ersatzselektor verfügt.Ist dies beim vorliegenden Formatierungsprogramm der Fall, wird geprüft, ob der Ersatzselektor Objekte des gegebenen Typs handhaben kann.Wenn er den Objekttyp handhaben kann, wird die **ISerializable.GetObjectData**\-Methode des Ersatzselektors aufgerufen.  
  
-   Wenn kein Ersatzselektor vorhanden ist oder wenn der gegebene Ersatzselektor den Objekttyp nicht handhaben kann, wird geprüft, ob das Objekt mit dem [Serializable](frlrfSystemSerializableAttributeClassTopic)\-Attribut markiert ist.Wenn das Objekt nicht markiert ist, wird eine Ausnahme des Typs [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic) ausgelöst.  
  
-   Wenn das Objekt entsprechend markiert ist, wird geprüft, ob das Objekt die [ISerializable](frlrfSystemRuntimeSerializationISerializableClassTopic)\-Schnittstelle implementiert.Falls dem so ist, wird die [GetObjectData](frlrfSystemRuntimeSerializationISerializableClassGetObjectDataTopic)\-Methode des Objekts aufgerufen.  
  
-   Wenn das Objekt die **ISerializable**\-Schnittstelle nicht implementiert, wird nach der Standardserialisierungsrichtlinie verfahren, und alle Felder, die nicht als [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic) markiert sind, werden serialisiert.  
  
## Siehe auch  
 [Binäre Serialisierung](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)