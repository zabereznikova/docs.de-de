---
title: "Visual Basic Limitations | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "limits"
  - "limitations, Visual Basic"
  - "limitations"
  - "limits, Visual Basic code"
  - "Visual Basic code, limitations"
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Visual Basic Limitations
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In früheren Versionen von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] galten bestimmte Codebeschränkungen, z. B. im Hinblick auf die Länge von Variablennamen, die zulässige Anzahl der Variablen in Modulen und die Modulgröße.  In [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)] wurden diese Beschränkungen gelockert, sodass Code flexibler geschrieben und angeordnet werden kann.  
  
 Physikalische Grenzen hängen eher vom Speicher zur Laufzeit als von Aspekten der Kompilierzeit ab.  Mit kluger Programmiertechnik und der Unterteilung großer Anwendungen in mehrere Klassen und Module ist die Wahrscheinlichkeit gering, dass eine interne [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Begrenzung überschritten wird.  
  
 Im Folgenden werden einige Begrenzungen beschrieben, die in extremen Fällen möglicherweise überschritten werden:  
  
-   **Namenslänge.** Für den Namen jedes deklarierten Programmierelements ist eine maximale Anzahl von Zeichen festgelegt.  Dieser Maximalwert gilt für einen vollständigen Qualifzierungspfad, wenn der Elementname qualifiziert ist.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Zeilenlänge.** Für eine physikalische Zeile von Quellcode gilt eine maximale Länge von 65535 Zeichen.  Die logische Quellcodezeile kann länger sein, wenn Sie Zeilenfortsetzungszeichen verwenden.  Siehe [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Arraydimensionen.** Die Anzahl der Dimensionen, die Sie für ein Array deklarieren können, ist durch einen Maximalwert begrenzt.  Dieser begrenzt die Anzahl der Indizes, mit denen Sie ein Arrayelement angeben können.  Siehe [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Zeichenfolgenlänge.** Die Anzahl von Unicode\-Zeichen, die Sie in einer einzelnen Zeichenfolge speichern können, ist durch einen Maximalwert begrenzt.  Siehe [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Umgebungszeichenfolgenlänge.** Die maximale Länge von als Befehlszeilenargument verwendeten Umgebungszeichenfolgen beträgt 32768 Zeichen.  Diese Begrenzung gilt auf allen Plattformen.  
  
## Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)