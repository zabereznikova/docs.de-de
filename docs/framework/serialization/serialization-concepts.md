---
title: "Serialisierungskonzepte | Microsoft Docs"
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
ms.assetid: e1ff4740-20a1-4c76-a8ad-d857db307054
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Serialisierungskonzepte
Warum ist es sinnvoll, die Serialisierung zu verwenden?Die beiden wichtigsten Gründe bestehen darin, dass der Objektstatus auf einem Speichermedium dauerhaft gespeichert werden soll, damit zu einem späteren Zeitpunkt eine genaue Kopie angefertigt werden kann, und dass das Objekt als Wert von einer Anwendungsdomäne zu einer anderen Anwendungsdomäne übertragen werden soll.Die Serialisierung wird beispielsweise eingesetzt, um den Sitzungsstatus in ASP.NET zu speichern und Objekte in die Zwischenablage von Windows Forms zu kopieren.Sie wird auch vom Remotingsystem verwendet, um Objekte als Wert von einer Anwendungsdomäne an eine andere zu übergeben.  
  
## In diesem Abschnitt  
 [Dauerhafte Speicherung](../../../docs/framework/serialization/persistent-storage.md)  
 Beschreibt, warum Objekte serialisiert werden.  
  
 [Marshallen als Wert](../../../docs/framework/serialization/marshal-by-value.md)  
 Beschreibt den Vorgang des Marshallens als Wert.  
  
## Verwandte Abschnitte  
 [Binäre Serialisierung](../../../docs/framework/serialization/binary-serialization.md)  
 Beschreibt den binären Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.  
  
 [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58)  
 Beschreibt die verschiedenen Kommunikationsverfahren, die in .NET Framework für die Remotekommunikation zur Verfügung stehen.  
  
 [XML\- und SOAP\-Serialisierung](../../../docs/framework/serialization/xml-and-soap-serialization.md)  
 Beschreibt den XML\- und SOAP\-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.