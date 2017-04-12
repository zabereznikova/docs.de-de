---
title: Effiziente Verwendung von Datentypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b81a1c81d970beee32925c3f2fe6ca3bcad79151
ms.lasthandoff: 03/13/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a>Effiziente Verwendung von Datentypen (Visual Basic)
Nicht deklarierte Variablen und Variablen, die ohne einen Datentyp zugewiesen sind die `Object` -Datentyp. Ganz einfach, schnell Programme zu schreiben, aber es kann dazu führen, dass sie langsamer ausgeführt.  
  
## <a name="strong-typing"></a>Starke Typisierung  
 Die Angabe von Datentypen für alle Variablen wird als bezeichnet *starke Typisierung*. Mit starker Typisierung hat mehrere Vorteile:  
  
-   Sie können IntelliSense-Unterstützung für Variablen. Dadurch können Sie die Eigenschaften und andere Member finden Sie unter während der Eingabe im Code.  
  
-   Nutzt die Vorteile der Compiler Typ überprüft. Anweisungen, die zur Laufzeit aufgrund von Fehlern, z. B. Überlauf fehlschlagen können abzufangen. Es fängt auch Aufrufe von Methoden für Objekte, die diese nicht unterstützen.  
  
-   Schnellere Ausführung des Codes führt.  
  
## <a name="most-efficient-data-types"></a>Die effizientesten Datentypen  
 Für Variablen, die generell keine Nachkommastellen enthalten, sind Ganzzahldatentypen effizienter als die Ganzzahltypen. In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` und `UInteger` sind die effizientesten numerischen Typen.  
  
 Bei Bruchzahlen `Double` ist der effizienteste Datentyp, da die Prozessoren auf den aktuellen Plattformen Gleitkommaoperationen mit doppelter Genauigkeit ausführen. Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.  
  
## <a name="specifying-data-type"></a>Angeben eines Datentyps  
 Verwenden der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) zum Deklarieren einer Variablen eines bestimmten Typs. Sie können die Zugriffsebene gleichzeitig angeben, mit der [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md), [geschützt](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort, wie im folgenden Beispiel.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Zeichen-Konvertierung  
 Die `AscW` und `ChrW` Funktionen werden in Unicode. Verwenden Sie diese den Vorzug `Asc` und `Chr`, die in und aus Unicode übersetzen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Numerische Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Verwenden von IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)
