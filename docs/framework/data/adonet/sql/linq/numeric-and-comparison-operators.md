---
title: "Numerische Operatoren und Vergleichoperatoren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Numerische Operatoren und Vergleichoperatoren
Arithmetische Operatoren und Vergleichsoperatoren funktionieren mit folgenden Ausnahmen wie in der Common Language Runtime \(CLR\):  
  
-   SQL unterstützt den Modulusoperator bei Gleitkommazahlen nicht.  
  
-   SQL unterstützt ungeprüfte arithmetische Operatoren nicht.  
  
-   Inkrementoperatoren und Dekrementoperatoren führen zu Nebeneffekten, wenn Sie diese in Ausdrücken verwenden, die nicht in SQL repliziert werden können und daher nicht unterstützt werden.  
  
## Unterstützte Operatoren  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden Operatoren.  
  
-   Grundlegende arithmetische Operatoren  
  
    -   `+`  
  
    -   `-` \(Subtraktion\)  
  
    -   `*`  
  
    -   `/`  
  
    -   Visual Basic\-Ganzzahlendivision \(`\`\)  
  
    -   `%` \(Visual Basic `Mod`\)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` \(unäre Negation\)  
  
-   Grundlegende Vergleichsoperatoren:  
  
    -   Visual Basic `=` und C\# `==`  
  
    -   Visual Basic `<>` und C\# `!=`  
  
    -   Visual Basic `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## Siehe auch  
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)   
 [C\#\-Operatoren](../Topic/C%23%20Operators.md)   
 [Operators](../Topic/Operators%20\(Visual%20Basic\).md)