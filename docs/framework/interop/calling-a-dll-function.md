---
title: "Calling a DLL Function | Microsoft Docs"
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
  - "unmanaged functions, calling"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "platform invoke, calling unmanaged functions"
  - "interoperation with unmanaged code, platform invoke"
  - "DLL functions"
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Calling a DLL Function
Nicht verwaltete DLL\-Funktionen werden in nahezu identischer Weise aufgerufen wie anderer verwalteter Code. Dennoch gibt es kleine Unterschiede, und möglicherweise sind die DLL\-Funktionen dadurch zunächst verwirrend.  In diesem Abschnitt werden einige ungewöhnliche Aspekte beim Aufrufen beschrieben.  
  
 Strukturen, die von Plattformaufrufen zurückgegeben werden, müssen Datentypen sein, die über die gleiche Darstellung in verwaltetem und nicht verwaltetem Code verfügen.  Solche Typen werden als *blitfähige Typen* bezeichnet, da sie keine Konvertierung erfordern \(siehe [Blittable and Non\-Blittable Types](../../../docs/framework/interop/blittable-and-non-blittable-types.md)\).  Um eine Funktion aufzurufen, deren Rückgabetyp eine nicht blitfähige Struktur ist, können Sie einen blitfähigen Hilfstyp definieren, der dieselbe Größe wie der nicht blitfähige Typ aufweist, und die Daten nach der Rückgabe der Funktion konvertieren.  
  
## In diesem Abschnitt  
 [Übergeben von Strukturen](../../../docs/framework/interop/passing-structures.md)  
 Behandelt Aspekte beim Übergeben von Datenstrukturen mit einem vordefinierten Layout.  
  
 [Rückruffunktionen](../../../docs/framework/interop/callback-functions.md)  
 Stellt grundlegende Informationen über Rückruffunktionen bereit.  
  
 [Gewusst wie: Implementieren von Rückruffunktionen](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 Beschreibt die Implementierung von Rückruffunktionen in verwaltetem Code.  
  
## Verwandte Abschnitte  
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Beschreibt das Aufrufen nicht verwalteter DLL\-Funktionen mithilfe von Plattformaufruf.  
  
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 Beschreibt, wie Methodenparameter deklariert und Argumente an Funktionen übergeben werden, die durch nicht verwaltete Bibliotheken exportiert wurden.