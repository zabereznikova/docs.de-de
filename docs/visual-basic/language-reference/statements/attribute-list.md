---
title: "Attribute List (Visual Basic) | Microsoft Docs"
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
  - "attribute list"
  - "attributes [Visual Basic], applying"
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Attribute List (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt die Attribute an, die auf ein deklariertes Programmierelement angewendet werden sollen.  Mehrere Attribute werden durch Komma voneinander getrennt.  Die folgenden Informationen zeigen die Syntax für ein Attribut.  
  
## Syntax  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## Teile  
 `attributemodifier`  
 Erforderlich für Attribute, die am Anfang einer Quelldatei angewendet werden.  Kann [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) oder [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md) sein.  
  
 `attributename`  
 Erforderlich.  Name des Attributs.  
  
 `attributearguments`  
 Optional.  Liste der Positionsargumente für dieses Attribut.  Mehrere Argumente werden durch Komma voneinander getrennt.  
  
 `attributeinitializer`  
 Optional.  Liste der Variablen\- oder Eigenschafteninitialisierer für dieses Attribut.  Mehrere Initialisierer werden durch Komma voneinander getrennt.  
  
## Hinweise  
 Sie können ein oder mehrere Attribute auf beinahe jedes Programmierelement \(Typen, Prozeduren, Eigenschaften usw.\) anwenden.  Attribute treten in den Metadaten der Assembly auf. Sie können sie verwenden, um Anmerkungen in Ihrem Code zu machen oder um anzugeben, wie ein bestimmtes Programmierelement verwendet werden soll.  Sie können von Visual Basic und .NET Framework definierte Attribute übernehmen und eigene Attribute definieren.  
  
 Weitere Informationen darüber, wann Attribute zu verwenden sind, finden Sie unter [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md).  Informationen über Attributnamen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Regeln  
  
-   **Platzierung.** Sie können Attribute auf die meisten deklarierten Programmierelemente anwenden.  Um ein oder mehrere Attribute anzuwenden, fügen Sie am Anfang der Elementdeklaration einen *Attributblock* ein.  Jeder Eintrag der Attributliste gibt ein anzuwendendes Attribut an sowie den Modifizierer und die Argumente, die für diesen Aufruf des Attributs verwendet werden.  
  
-   **Spitze Klammern.** Wenn Sie eine Attributliste angeben, müssen Sie diese in spitze Klammern \("`<`" und "`>`"\) einschließen.  
  
-   **Teil der Deklaration.** Das Attribut muss Teil der Elementdeklaration sein. Es darf keine separate Anweisung sein.  Sie können die Zeilenfortsetzungssequenz \(" `_`"\) verwenden, um die Deklarationsanweisung auf mehreren Quellcodezeilen zu erweitern.  
  
-   **Modifizierer.** Für jedes Attribut, das zu Beginn einer Quelldatei auf ein Programmierelement angewendet wird, ist ein Attributmodifizierer \(`Assembly` oder `Module`\) erforderlich.  Attributmodifizierer sind nicht zulässig für Attribute, die auf nicht am Anfang einer Quelldatei stehende Elemente angewendet werden.  
  
-   **Argumente.** Alle Positionsargumente für ein Attribut müssen vor Variablen\- oder Eigenschafteninitialisierungen stehen.  
  
## Beispiel  
 Im folgenden Beispiel wird das <xref:System.Runtime.InteropServices.DllImportAttribute>\-Attribut auf eine Skelettdefinition einer `Function`\-Prozedur angewendet.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> gibt an, dass die attributierte Prozedur einen Einstiegspunkt in einer nicht verwalteten Dynamic Link Library \(DLL\) darstellt.  Das Attribut gibt den DLL\-Namen als Positionsargument und die anderen Informationen als Variableninitialisierungen an.  
  
## Siehe auch  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Module \<keyword\>](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)