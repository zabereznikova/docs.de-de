---
title: "How to: Declare an Object Variable and Assign an Object to It in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "object variables, declaring"
  - "declaring object variables"
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Declare an Object Variable and Assign an Object to It in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie deklarieren eine Variable vom Typ [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) durch die Angabe von `As Object` in einer [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)\-Anweisung.  Um einer solchen Variablen ein Objekt zuzuweisen, geben Sie das Objekt in einer Zuweisungsanweisung oder Initialisierungsklausel nach dem Gleichheitszeichen \(`=`\) an.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `Object`\-Variable deklariert und die aktuelle Klasseninstanz dieser Variablen zugewiesen.  
  
```  
  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 Sie können Deklaration und Zuweisung kombinieren, indem Sie die Variable im Rahmen der Deklaration initialisieren.  Das folgende Beispiel entspricht dem vorhergehenden.  
  
```  
Dim thisObject As Object = "This is an Object"  
```  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Verweis auf den <xref:System>\-Namespace.  
  
-   Klasse, Struktur oder Modul für die `Dim`\-Anweisung  
  
-   Prozedur, in welche die Zuweisungsanweisung eingefügt wird  
  
## Siehe auch  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)