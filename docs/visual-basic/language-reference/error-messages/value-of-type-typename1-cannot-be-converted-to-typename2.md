---
title: "Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30955"
  - "bc30955"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30955"
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Der Wert vom Typ '\<Typname1\>' kann nicht in '\<Typname2\>' konvertiert werden.Der Typenkonflikt könnte auf das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly "\<Assemblyname\>" zurückzuführen sein.Ersetzen Sie den Dateiverweis auf "\<Dateipfad\>" in Projekt "\<Projektname1\>" durch einen Projektverweis auf "\<Projektname2\>"'  
  
 Wenn ein Projekt sowohl einen Projektverweis als auch einen Dateiverweis enthält, kann der Compiler die Konvertierung zwischen den Typen nicht gewährleisten.  
  
 Im folgenden Pseudocode wird eine Situation veranschaulicht, die diesen Fehler verursachen kann.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 Projekt `P1` enthält einen indirekten Projektverweis über Projekt `P2` auf Projekt `P3` sowie einen direkten Dateiverweis auf `P3`.  In der Deklaration von `commonObject` wird der Dateiverweis auf `P3` verwendet, während im Aufruf von `P2.getCommonClass` der Projektverweis auf `P3` verwendet wird.  
  
 Das Problem in diesem Fall ist, dass im Dateiverweis ein Dateipfad und \-name für die Ausgabedatei von `P3` \(normalerweise p3.dll\) angegeben wird, während die Projektverweise das Quellprojekt \(`P3`\) mit dem Projektname bezeichnen.  Daher kann der Compiler nicht gewährleisten, dass der Typ `P3.commonClass` von demselben Quellcode über zwei unterschiedliche Verweise stammt.  
  
 Diese Situation tritt i. d. R. auf, wenn Projektverweise und Dateiverweise gemeinsam verwendet werden.  Im vorhergehenden Beispiel tritt das Problem nicht auf, wenn `P1` statt eines Dateiverweises einen direkten Projektverweis auf `P3` enthält.  
  
 **Fehler\-ID:** BC30955  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie den Dateiverweis in einen Projektverweis.  
  
## Siehe auch  
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Verwalten von Verweisen in einem Projekt](/visual-studio/ide/managing-references-in-a-project)   
 [Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweise hinzufügen"](http://msdn.microsoft.com/de-de/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)