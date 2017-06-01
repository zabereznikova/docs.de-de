---
title: "R&#228;umliche Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# R&#228;umliche Funktionen
Es gibt kein Literalformat für räumliche Typen.  Sie können jedoch kanonische Entity Framework\-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT \(Well\-Known Text\)\-Format aufrufen.  Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 Auf der Seite [SpatialEdmFunctions\-Methoden](http://msdn.microsoft.com/library/hh749531.aspx) finden Sie eine Liste aller räumlichen kanonischen Entity Framework\-Methoden.  Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.