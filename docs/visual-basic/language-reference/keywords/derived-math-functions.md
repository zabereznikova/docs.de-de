---
title: "Derived Math Functions (Visual Basic) | Microsoft Docs"
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
  - "arithmetic operations, derived math functions"
  - "cosecant function"
  - "arcsecant function"
  - "arccotangent function"
  - "functions [Visual Basic], derived math functions"
  - "inverse functions"
  - "math functions, derived"
  - "derived math functions"
  - "cotangent function"
  - "angles"
  - "secant function"
  - "trigonometric functions"
  - "logarithms"
  - "arccosecant function"
  - "hyperbolic functions"
  - "arcsine function"
  - "degrees"
  - "arccosine function"
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Derived Math Functions (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die folgende Tabelle enthält nicht systeminterne mathematische Funktionen, die aus den systeminternen mathematischen Funktionen des <xref:System.Math?displayProperty=fullName>\-Objekts abgeleitet werden können:  Sie können auf die systeminternen mathematischen Funktionen zugreifen, indem Sie der Datei oder dem Projekt `Imports System.Math` hinzufügen.  
  
|Funktion|Abgeleitete Äquivalente|  
|--------------|-----------------------------|  
|Sekans \(Sec\(x\)\)|1 \/ Cos\(x\)|  
|Kosekans \(Csc\(x\)\)|1 \/ Sin\(x\)|  
|Kotangens \(Ctan\(x\)\)|1 \/ Tan\(x\)|  
|Arkussinus \(Asin\(x\)\)|Atan\(x \/ Sqrt\(\-x \* x \+ 1\)\)|  
|Arkuskosinus \(Acos\(x\)\)|Atan\(\-x \/ Sqrt\(\-x \* x \+ 1\)\) \+ 2 \* Atan\(1\)|  
|Arkussekans \(Asec\(x\)\)|2 \* Atan\(1\) – Atan\(Sign\(x\) \/ Sqrt\(x \* x – 1\)\)|  
|Arkuskosekans \(Acsc\(x\)\)|Atan\(Sign\(x\) \/ Sqrt\(x \* x – 1\)\)|  
|Arkuskotangens \(Acot\(x\)\)|2 \* Atan\(1\) \- Atan\(x\)|  
|Hyperbelsinus \(Sinh\(x\)\)|\(Exp\(x\) – Exp\(\-x\)\) \/ 2|  
|Hyperbelkosinus \(Cosh\(x\)\)|\(Exp\(x\) \+ Exp\(\-x\)\) \/ 2|  
|Hyperbeltangens \(Tanh\(x\)\)|\(Exp\(x\) – Exp\(\-x\)\) \/ \(Exp\(x\) \+ Exp\(\-x\)\)|  
|Hyperbelsekans \(Sech\(x\)\)|2 \/ \(Exp\(x\) \+ Exp\(\-x\)\)|  
|Hyperbelkosekans \(Csch\(x\)\)|2 \/ \(Exp\(x\) – Exp\(\-x\)\)|  
|Hyperbelkotangens \(Coth\(x\)\)|\(Exp\(x\) \+ Exp\(\-x\)\) \/ \(Exp\(x\) – Exp\(\-x\)\)|  
|Hyperbol. Arkussinus \(Asinh\(x\)\)|Log\(x \+ Sqrt\(x \* x \+ 1\)\)|  
|Hyperbol. Arkuskosinus \(Acosh\(x\)\)|Log\(x \+ Sqrt\(x \* x – 1\)\)|  
|Hyperbol. Arkustangens \(Atanh\(x\)\)|Log\(\(1 \+ x\) \/ \(1 – x\)\) \/ 2|  
|Hyperbol. Arkussekans \(AsecH\(x\)\)|Log\(\(Sqrt\(\-x \* x \+ 1\) \+ 1\) \/ x\)|  
|Hyperbol. Arkuskosekans \(Acsch\(x\)\)|Log\(\(Sign\(x\) \* Sqrt\(x \* x \+ 1\) \+ 1\) \/ x\)|  
|Hyperbol. Arkuskotangens \(Acoth\(x\)\)|Log\(\(x \+ 1\) \/ \(x – 1\)\) \/ 2|  
  
## Siehe auch  
 [Mathematische Funktionen](../../../visual-basic/language-reference/functions/math-functions.md)