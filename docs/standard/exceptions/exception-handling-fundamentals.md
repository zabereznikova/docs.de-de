---
title: "Grundlagen der Ausnahmebehandlung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Common Language Runtime, Ausnahmen"
  - "Ausnahmen, Beispiele"
  - "Laufzeit, Ausnahmen"
ms.assetid: e865d48c-b862-4448-833e-09fcd48adf6b
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Grundlagen der Ausnahmebehandlung
Die CLR \(Common Language Runtime\) unterstützt ein auf Ausnahmeobjekten und geschützten Codeblöcken basierendes Modell der Ausnahmebehandlung.  Von der CLR wird ein Objekt erstellt, das eine auftretende Ausnahme repräsentiert.  Sie können auch Ihre eigenen Ausnahmeklassen durch Ableitung von einer entsprechenden Basisausnahme erstellen.  
  
 Alle Sprachen, die mit der CLR arbeiten, behandeln Ausnahmen auf die gleiche Weise.  Jede Sprache verwendet eine Form der Ausnahmebehandlung mit einer try\/catch\/finally\-Struktur.  Dieser Abschnitt enthält verschiedene Beispiele grundlegender Ausnahmebehandlungen.  
  
## In diesem Abschnitt  
 [Gewusst wie: Verwenden des Try\-Catch\-Blocks zum Abfangen von Ausnahmen](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)  
 Beschreibt die Behandlung von Ausnahmen mit dem try\/catch\-Block.  
  
 [Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch\-Block](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)  
 Beschreibt das Abfangen spezifischer Ausnahmen.  
  
 [Gewusst wie: Explizites Auslösen von Ausnahmen](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)  
 Beschreibt das Auslösen, Abfangen und erneute Auslösen von Ausnahmen.  
  
 [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)  
 Beschreibt das Erstellen von eigenen Ausnahmeklassen.  
  
 [Verwenden benutzergefilterter Handler](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)  
 Beschreibt das Einrichten gefilterter Ausnahmen.  
  
 [Gewusst wie: Verwenden eines Finally\-Blocks](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)  
 Erläutert die Verwendung der finally\-Anweisung in einem Ausnahmeblock.  
  
## Verwandte Abschnitte  
 [Ausnahmen](../../../docs/standard/exceptions/index.md)  
 Übersicht über Ausnahmen der Common Language Runtime.  
  
 [Exception\-Klasse und Exception\-Eigenschaften](../../../docs/standard/exceptions/exception-class-and-properties.md)  
 Beschreibt die Elemente eines Ausnahmeobjekts.