---
title: "Dauerhafte Speicherung | Microsoft Docs"
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
  - "Binäre Serialisierung, Dauerhafte Speicherung"
  - "Dauerhafte Speicherung"
  - "Serialisierung, Dauerhafte Speicherung"
ms.assetid: b112c0dd-93e2-4eef-908d-5963f80bab65
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Dauerhafte Speicherung
Es ist häufig notwendig, die Werte der Felder eines Objekts auf einem Datenträger zu speichern und diese Daten später abzurufen.Dies lässt sich zwar auch ohne die Serialisierung erreichen, aber dieser Ansatz ist häufig mühsam und fehleranfällig und wird zunehmend komplex, wenn eine Hierarchie von Objekten verfolgt werden muss.Stellen Sie sich vor, Sie programmieren eine große Geschäftsanwendung mit Tausenden von Objekten und müssen Code schreiben, mit dem die Felder und Eigenschaften der einzelnen Objekte auf dem Datenträger gespeichert und von diesem wieder abgerufen und in den jeweiligen Objekten wiederhergestellt werden.Die Serialisierung stellt einen zweckmäßigen Mechanismus zur Erreichung dieses Ziels bereit.  
  
 Die Common Language Runtime verwaltet, wie Objekte im Speicher gespeichert werden und stellt einen automatischen Serialisierungsmechanismus bereit, der sich auf die[Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md) stütztWenn ein Objekt serialisiert wird, werden der Name der Klasse, die Assembly und alle Datenmember der Klasseninstanz auf das Speichermedium geschrieben.Objekte speichern oft in Membervariablen Verweise auf andere Instanzen.Beim Serialisieren der Klasse verfolgt das Serialisierungsmodul Objekte, auf die verwiesen wird und die bereits serialsiert sind, um sicherzustellen, dass ein Objekt nicht zweimal serialisiert wird.Die mit dem [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] bereitgestellte Serialisierungsarchitektur behandelt Objektdiagramme und Zirkelverweise automatisch richtig.Objektdiagramme müssen nur die Anforderung erfüllen, dass alle Objekte, auf die das serialisierte Objekt verweist, auch als [Serializable](frlrfSystemSerializableAttributeClassTopic) markiert sein müssen \(weitere Informationen finden Sie unter [Einfache Serialisierung](../../../docs/framework/serialization/basic-serialization.md)\).Ist dies nicht der Fall, wird eine Ausnahme ausgelöst, wenn versucht wird, das nicht markierte Objekt zu serialisieren.  
  
 Wenn die serialisierte Klasse deserialisiert wird, wird sie neu erstellt, und die Werte aller Datenmember werden automatisch wiederhergestellt.  
  
## Siehe auch  
 [Serialisierungskonzepte](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)