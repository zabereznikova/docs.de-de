---
title: "Verwenden benutzergefilterter Ausnahmehandler | Microsoft Docs"
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
  - "Ausnahmen, Benutzergefiltert"
  - "Benutzergefilterte Ausnahmen"
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Verwenden benutzergefilterter Ausnahmehandler
Visual Basic unterstützt benutzergefilterte Ausnahmen.  Benutzergefilterte Handler fangen und behandeln Ausnahmen gemäß benutzerdefinierten Ausnahmebedingungen.  Diese Handler verwenden die **Catch**\-Anweisung mit dem Schlüsselwort **When**.  
  
 Dieses Verfahren ist nützlich, wenn ein bestimmtes einzelnes Ausnahmeobjekt mehreren Fehlern entspricht.  In diesem Fall verfügt das Objekt in der Regel über eine Eigenschaft, die den spezifischen, mit dem Fehler verknüpften Fehlercode enthält.  Die den Fehlercode enthaltende Eigenschaft kann im Ausdruck dazu verwendet werden, nur einen ganz bestimmten Fehler auszuwählen, der in der **Catch**\-Klausel behandelt werden soll.  
  
 Das folgende Beispiel in Visual Basic veranschaulicht die **Catch\/When**\-Anweisung.  
  
```  
Try  
      'Try statements.  
   Catch When Err = VBErr_ClassLoadException  
      'Catch statements.  
End Try  
```  
  
 Der Ausdruck mit der benutzergefilterten Klausel enthält keinerlei Einschränkungen.  Wenn während der Ausführung des benutzergefilterten Ausdrucks eine Ausnahme auftritt, wird diese Ausnahme verworfen, und der Filterausdruck wird als false betrachtet.  In diesem Fall setzt die Common Language Runtime die Suche nach einem Handler für die aktuelle Ausnahme fort.  
  
## Kombinieren von Klauseln mit spezifischen Ausnahmen und Benutzerfiltern  
 Eine **catch**\-Anweisung kann sowohl Klauseln mit einer spezifischen Ausnahme als auch mit einem Benutzerfilter enthalten.  Die CLR prüft zuerst die spezifische Ausnahme.  Ist die spezifische Ausnahme erfolgreich, führt die CLR den Benutzerfilter aus.  Der allgemeine Filter kann einen Verweis auf eine im Klassenfilter deklarierte Variable enthalten.  Beachten Sie, dass die Reihenfolge von zwei Filterklauseln nicht umkehrbar ist.  
  
 Das folgende Beispiel in Visual Basic zeigt die spezifische Ausnahme `ClassLoadException` in der **Catch**\-Anweisung sowie die benutzergefilterte Klausel mit dem Schlüsselwort **When**.  
  
```  
Try  
      'Try statements.  
   Catch cle As ClassLoadException When cle.IsRecoverable()  
      'Catch statements.  
End Try  
```  
  
## Siehe auch  
 [Gewusst wie: Verwenden des Try\-Catch\-Blocks zum Abfangen von Ausnahmen](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch\-Block](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Best Practices für Ausnahmen](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)