---
title: "Ordinal is not valid | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID452"
dev_langs: 
  - "VB"
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ordinal is not valid
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Beim Aufruf einer Dynamic Link Library \(DLL\) wurde mit der `#num`\-Syntax angegeben, dass eine Zahl anstelle eines Prozedurnamens verwendet wird.  Dieser Fehler hat die folgenden möglichen Ursachen:  
  
-   Fehler beim Versuch, den `#num`\-Ausdruck in einen Ordinalwert zu konvertieren.  
  
-   Der angegebene `#num`\-Ausdruck gibt keine Funktion in der DLL an.  
  
-   Eine Typbibliothek weist eine ungültige Deklaration auf. Aus diesem Grund wird ein ungültiger Ordinalwert intern verwendet.  
  
### So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass der Ausdruck eine gültige Zahl darstellt, oder rufen Sie die Prozedur nach Name auf.  
  
2.  Stellen Sie sicher, dass mit `#num` eine gültige Funktion in der DLL bezeichnet wird.  
  
3.  Isolieren Sie den Prozeduraufruf, der das Problem verursacht, indem Sie den Code als Kommentar kennzeichnen.  Schreiben Sie eine `Declare`\-Anweisung für die Prozedur, und leiten Sie das Problem an den Hersteller der Typbibliothek weiter.  
  
## Siehe auch  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)