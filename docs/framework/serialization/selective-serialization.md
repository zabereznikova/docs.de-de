---
title: "Selektive Serialisierung | Microsoft Docs"
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
  - "Binäre Serialisierung, Selektive Serialisierung"
  - "Serialisierung, Selektive Serialisierung"
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Selektive Serialisierung
Eine Klasse enthält oft Felder, die nicht serialisiert werden sollten.Angenommen, eine Klasse speichert in einer Membervariablen eine Thread\-ID.Wenn die Klasse deserialisiert wird, wird der Thread, dessen ID bei der Serialisierung der Klasse gespeichert wurde, möglicherweise nicht mehr ausgeführt. Daher ist es nicht sinnvoll, diesen Wert zu serialisieren.Sie können verhindern, dass Membervariablen serialisiert werden, indem Sie sie wie folgt mit dem [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic)\-Attribut markieren.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```  
  
 Legen Sie nach Möglichkeit jedes Objekt, das sicherheitsrelevante Daten enthalten kann, als nicht serialisierbar fest.Wenn das Objekt serialisiert werden muss, übernehmen Sie das **NonSerialized**\-Attribut für bestimmte Felder, die vertraulichee Daten speichern.Wenn diese Felder nicht von der Serialisierung ausgeschlossen werden, werden die darin gespeicherten für jeglichen Code verfügbar gemacht, der zur Serialisierung berechtigt ist.Weitere Informationen zum Schreiben von sicherem Serialisierungscode finden Sie unter [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md).  
  
## Siehe auch  
 [Binäre Serialisierung](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)