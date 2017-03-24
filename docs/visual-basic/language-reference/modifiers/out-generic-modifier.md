---
title: "Out (Generic Modifier) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.VarianceOut"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Out keyword [Visual Basic]"
  - "covariance, Out keyword [Visual Basic]"
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Out (Generic Modifier) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Für generische Typparameter gibt das `Out`\-Schlüsselwort an, dass der Typ kovariant ist.  
  
## Hinweise  
 Kovarianz ermöglicht es, einen stärker abgeleiteten Typ zu verwenden als durch den generischen Parameter angegeben.  Dies ermöglicht die implizite Konvertierung von Klassen, die abweichende Schnittstellen implementieren, und die implizite Konvertierung von Delegattypen.  
  
 Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Regeln  
 Sie können das `Out`\-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.  
  
 In einer generischen Schnittstelle kann ein Typparameter kovariant deklariert werden, wenn er die folgenden Bedingungen erfüllt:  
  
-   Der Typparameter wird nur als Rückgabetyp von Schnittstellenmethoden und nicht als Typ von Methodenargumenten verwendet.  
  
    > [!NOTE]
    >  Es gibt allerdings eine Ausnahme zu dieser Regel.  Wenn eine kovariante Schnittstelle einen kontravarianten generischen Delegaten als Methodenparameter enthält, können Sie den kovarianten Typ als generischen Typparameter für diesen Delegaten verwenden.  Weitere Informationen über kovariante und kontravariante generische Delegaten finden Sie unter [Varianz bei Delegaten](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md) und [Verwenden von Varianz für die generischen Delegaten Func und Action](../Topic/Using%20Variance%20for%20Func%20and%20Action%20Generic%20Delegates%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   Der Typparameter wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.  
  
 In einem generischen Delegaten kann ein Typparameter kovariant deklariert werden, wenn er nur als Methodenrückgabetyp und nicht für Methodenargumente verwendet wird.  
  
 Kovarianz und Kontravarianz werden für Verweistypen, aber nicht für Werttypen unterstützt.  
  
 In Visual Basic können Sie keine Ereignisse in kovarianten Schnittstellen deklarieren, ohne den Delegattyp anzugeben.  Kovariante Schnittstellen können außerdem zwar geschachtelte Schnittstellen, jedoch keine geschachtelten Klassen, Enumerationen oder Strukturen aufweisen.  
  
## Verhalten  
 Eine Schnittstelle, die über einen kovarianten Typparameter verfügt, ermöglicht es den zugehörigen Methoden, mehr abgeleitete Typen zurückzugeben als vom Typparameter angegeben.  Da in .NET Framework 4 beispielsweise Typ T in <xref:System.Collections.Generic.IEnumerable%601> kovariant ist, können Sie einem Objekt des Typs `IEnumerable(Of Object)` ein Objekt des Typs `IEnumerabe(Of String)` zuweisen, ohne besondere Konvertierungsmethoden zu verwenden.  
  
 Einem kovarianten Delegaten kann ein anderer Delegat desselben Typs zugewiesen werden, allerdings mit einem stärker abgeleiteten generischen Typparameter.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine kovariante generische Schnittstelle deklariert, erweitert und implementiert wird.  Außerdem wird gezeigt, wie die implizite Konvertierung für Klassen verwendet wird, die eine kovariante Schnittstelle implementieren.  
  
 [!code-vb[vbVarianceKeywords#3](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein kovarianter generischer Delegat deklariert, instanziiert und aufgerufen wird.  Außerdem wird gezeigt, wie Sie die implizite Konvertierung für Delegattypen verwenden können.  
  
 [!code-vb[vbVarianceKeywords#4](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/out-generic-modifier_2.vb)]  
  
## Siehe auch  
 [Abweichungen bei generischen Schnittstellen](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)