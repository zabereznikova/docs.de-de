---
title: "Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument. | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc41999"
  - "bc41999"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC41999"
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine Prozedur wird mit einem [ByRef](../../../visual-basic/language-reference/modifiers/byref.md)\-Argument von einem anderen Typ als dem Typ des entsprechenden Parameters aufgerufen.  
  
 Wenn Sie das Argument mit `ByRef` übergeben, kopiert [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben.  In diesem Fall muss [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] anschließend beim Beenden der Prozedur den Wert der lokalen Variablen in das Argument im aufrufenden Code zurückkopieren.  
  
 Wenn der Wert eines `ByRef`\-Arguments in die Prozedur kopiert wird und Argument sowie Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich.  Wenn sich die Typen jedoch unterscheiden, muss [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] in beide Richtungen konvertieren.  Da Sie `CType` oder eines der anderen Konvertierungsschlüsselwörter nicht für ein Argument oder einen Parameter einer Prozedur verwenden können, ist eine solche Konvertierung immer implizit.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC41999  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie nach Möglichkeit ein aufrufendes Argument von demselben Typ wie der Prozedurparameter, damit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] keine Konvertierung ausführen muss.  
  
-   Wenn Sie die Prozedur mit einem anderen Argumenttyp als dem Parametertyp aufrufen müssen, jedoch in das aufrufende Argument kein Wert zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) statt als `ByRef`.  
  
## Siehe auch  
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)