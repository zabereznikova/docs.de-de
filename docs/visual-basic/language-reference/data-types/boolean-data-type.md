---
title: "Boolean Data Type (Visual Basic) | Microsoft Docs"
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
  - "vb.FALSE"
  - "vb.TRUE"
  - "vb.Boolean"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean data type"
  - "Boolean values, False keyword"
  - "False keyword [Visual Basic]"
  - "True keyword [Visual Basic]"
  - "Boolean values, True keyword"
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Boolean Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Speichert Werte, die nur `True` oder `False` sein können.  Die Schlüsselwörter `True` und `False` entsprechen den zwei Zuständen von `Boolean`\-Variablen.  
  
## Hinweise  
 Verwenden Sie den [Boolean Data Type \(Visual Basic\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md), um Werte mit zwei möglichen Zuständen zu speichern, z. B. Wahr\/Falsch, Ja\/Nein oder Ein\/Aus.  
  
 Der Standardwert von `Boolean` lautet `False`.  
  
 `Boolean`\-Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sollen nicht mit Zahlen gleichwertig sein.  Sie sollten nie Code schreiben, der von entsprechenden numerischen Werten für `True` und `False` abhängt.  Beschränken Sie den Einsatz von `Boolean`\-Variablen auf die logischen Werte, für die sie entworfen wurden.  
  
## Typkonvertierung  
 Wenn Visual Basic numerische Datentypwerte in `Boolean` konvertiert, wird 0 \(null\) in `False` und alle anderen Werte werden in `True` konvertiert.  Wenn Visual Basic `Boolean`\-Werte in numerische Typen konvertiert, wird `False` zu 0, und `True` wird –1.  
  
 Bei der Konvertierung von `Boolean`\-Werten in numerische Datentypen und umgekehrt ist zu beachten, dass die Konvertierungsmethoden von .NET Framework nicht immer dieselben Ergebnisse erzeugen wie die Konvertierungsmethoden von Visual Basic.  Das liegt daran, dass die Visual Basic\-Konvertierung ein Verhalten beibehält, das mit vorherigen Versionen kompatibel ist.  Weitere Informationen finden Sie im Abschnitt "Boolescher Typ wird nicht präzise in den numerischen Typ konvertiert" unter [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Programmiertipps  
  
-   **Negative Zahlen.** `Boolean` ist kein numerischer Typ und kann keinen negativen Wert darstellen.  In keinem Fall sollten Sie `Boolean` zum Speichern numerischer Werte verwenden.  
  
-   **Typzeichen.** Für `Boolean` ist kein Literaltypzeichen oder Typkennzeichen definiert.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Boolean?displayProperty=fullName>\-Struktur.  
  
## Beispiel  
 Im folgenden Beispiel ist `runningVB` eine `Boolean`\-Variable, die eine einfache Ja\-\/Nein\-Einstellung speichert.  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## Siehe auch  
 <xref:System.Boolean?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)