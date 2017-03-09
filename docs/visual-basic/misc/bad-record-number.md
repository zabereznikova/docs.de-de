---
title: "Ung&#252;ltige Datensatznummer | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID63"
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Ung&#252;ltige Datensatznummer
Die Datensatznummer in der `a FileGet`, `FilePut`, `FileGetObject` oder `FilePutObject`\-Anweisung ist kleiner oder gleich 0 \(null\).  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die zum Generieren der Datensatznummer verwendeten Berechnungen. Überprüfen Sie die Rechtschreibung der Variablen, die die Datensatznummer enthalten oder bei der Berechnung von Datensatznummern verwendet werden. Ein falsch geschriebener Variablenname wird implizit deklariert und zu 0 \(null\) initialisiert, es sei denn, Sie haben `Option Explicit On` im Modul verwendet.  
  
## Siehe auch  
 [Option Explicit Statement](../../visual-basic/language-reference/statements/option-explicit-statement.md)