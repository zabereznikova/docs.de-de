---
title: "Efficient Use of Data Types (Visual Basic) | Microsoft Docs"
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
  - "performance, data type efficiency"
  - "data types [Visual Basic], weak typing"
  - "AscW function, preferred to Asc"
  - "data types [Visual Basic], using efficiently"
  - "optimization, data types"
  - "data types [Visual Basic], strong typing"
  - "strong typing"
  - "typing, strong"
  - "data types [Visual Basic], optimizing"
  - "ChrW function, preferred to Chr"
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Efficient Use of Data Types (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Nicht deklarierten Variablen und Variablen, die ohne Datentyp deklariert sind, wird der Datentyp `Object` zugewiesen.  Programme lassen sich dadurch schneller programmieren, werden jedoch auch langsamer ausgeführt.  
  
## Starke Typisierung  
 Die Angabe von Datentypen für alle Variablen wird als *starke Typisierung* bezeichnet.  Die Verwendung der starken Typisierung bietet einige Vorteile:  
  
-   Dadurch wird die IntelliSense\-Unterstützung für die Variablen.  Sie können die Eigenschaften und andere Member der Variablen bei der Eingabe in den Code anzeigen.  
  
-   Die Compilertypüberprüfung wird genutzt.  Anweisungen, die zur Laufzeit beispielsweise aufgrund eines Überlaufs oder anderer Fehler fehlschlagen können, können abgefangen werden.  Außerdem werden Aufrufe von Methoden für Objekte, die diese nicht unterstützen, abgefangen.  
  
-   Sie ermöglicht die schnellere Ausführung des Codes.  
  
## Die effizientesten Datentypen  
 Für Variablen, die generell keine Nachkommastellen enthalten, sind Ganzzahldatentypen effizienter als Nicht\-Ganzzahltypen.  In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sind `Integer` und `UInteger` die effizientesten numerischen Typen.  
  
 Bei Bruchzahlen ist `Double` der effizienteste Datentyp, weil die Prozessoren der aktuellen Plattformen Gleitkommaoperationen mit doppelter Genauigkeit ausführen.  Operationen mit `Double` werden jedoch langsamer ausgeführt als solche mit ganzzahligen Typen wie `Integer`.  
  
## Angeben eines Datentyps  
 Deklarieren Sie eine Variable eines bestimmten Typs mittels der [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).  Sie können gleichzeitig, wie im folgenden Beispiel gezeigt, ihre Zugriffsebene angeben. Verwenden Sie dazu das Schlüsselwort [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) oder [Private](../../../../visual-basic/language-reference/modifiers/private.md).  
  
```  
Private x As Double  
Protected s As String  
```  
  
## Zeichenkonvertierung  
 Die `AscW`\-Funktion und die `ChrW`\-Funktion werden in Unicode verwendet.  Sie sind `Asc` und `Chr` vorzuziehen, da letztere in und aus Unicode konvertiert werden müssen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Verwenden von IntelliSense](/visual-studio/ide/using-intellisense)