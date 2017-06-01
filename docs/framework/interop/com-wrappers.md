---
title: "COM Wrappers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "wrapper classes"
  - "COM interop, COM wrappers"
  - "COM wrappers"
  - "COM, wrappers"
  - "interoperation with unmanaged code, COM wrappers"
  - "COM callable wrappers"
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# COM Wrappers
COM unterscheidet sich vom .NET Framework\-Objektmodell in einigen wichtigen Punkten:  
  
-   Clients von COM\-Objekten müssen die Lebensdauer dieser Objekte verwalten; Common Language Runtime verwaltet die Lebensdauer der Objekte in ihrer Umgebung.  
  
-   Clients von COM\-Objekten ermitteln die Verfügbarkeit eines Dienstes durch Anfrage bei einer Schnittstelle, die diesen Dienst bereitstellt. Daraufhin wird entweder ein Schnittstellenzeiger zurückgegeben oder nicht.  Clients von .NET\-Objekten können eine Beschreibung der Objektfunktionen durch Reflektion erhalten.  
  
-   .NET\-Objekte befinden sich in dem Speicher, der durch die .NET Framework\-Ausführungsumgebung verwaltet wird.  In der Ausführungsumgebung können Objekte aus Kapazitätsgründen innerhalb des Speichers bewegt und alle Verweise auf diese Objekte aktualisiert werden.  Nicht verwaltete Clients, die einen Zeiger auf ein Objekt erhalten haben, gehen davon aus, dass das Objekt an derselben Position bleibt.  Diesen Clients steht kein Mechanismus für den Umgang mit Objekten ohne festgelegte Position zur Verfügung.  
  
 Zur Bewältigung dieser Unterschiede stellt Common Language Runtime Wrapperklassen bereit, die verwalteten und nicht verwalteten Clients suggerieren, dass sie Objekte innerhalb ihrer jeweiligen Umgebung aufrufen.  Bei jedem Aufruf einer Methode für ein COM\-Objekt durch einen verwalteten Client wird von Common Language Runtime ein RCW \([Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)\) erstellt.  RCWs abstrahieren u. a. von den Unterschieden zwischen verwalteten und nicht verwalteten Verweismechanismen.  Darüber hinaus wird von Common Language Runtime ein CCW \([COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)\) zur Umkehrung des Prozesses erstellt, um einem COM\-Client den nahtlosen Aufruf einer Methode für ein .NET\-Objekt zu ermöglichen.  Wie die folgende Abbildung zeigt, bestimmt die Perspektive des aufrufenden Codes, welche Wrapperklasse von Common Language Runtime erstellt wird.  
  
 ![Übersicht über COM&#45;Wrapper](../../../docs/framework/interop/media/bidirectional.gif "bidirectional")  
Übersicht über COM\-Wrapper  
  
 In den meisten Fällen bietet der durch Common Language Runtime generierte Standard\-RCW oder Standard\-CCW angemessenes Marshallen für Aufrufe, welche die Grenze zwischen COM und .NET Framework überschreiten.  Unter Verwendung benutzerdefinierter Attribute können Sie optional festlegen, auf welche Weise verwalteter und nicht verwalteter Code durch Common Language Runtime repräsentiert wird.  
  
## Siehe auch  
 [Advanced COM Interoperability](http://msdn.microsoft.com/de-de/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)   
 [Customizing Standard Wrappers](http://msdn.microsoft.com/de-de/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [How to: Customize Runtime Callable Wrappers](http://msdn.microsoft.com/de-de/4a4bb3da-4d60-4517-99f2-78d46a681732)