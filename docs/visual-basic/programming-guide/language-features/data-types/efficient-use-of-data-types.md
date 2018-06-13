---
title: Effiziente Verwendung von Datentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 6e71c4e2225bbcde3bb2bd20ae098f5600990051
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647760"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Effiziente Verwendung von Datentypen (Visual Basic)
Nicht deklarierte Variablen und Variablen, die ohne ein Datentyp zugewiesen sind die `Object` -Datentyp. Dies erleichtert es schnell Programme zu schreiben, aber es kann dazu führen, dass sie langsamer ausgeführt.  
  
## <a name="strong-typing"></a>Starke Typisierung  
 Das Festlegen von Datentypen für alle Variablen wird bezeichnet als *starke Typisierung*. Mit starker Typisierung hat mehrere Vorteile:  
  
-   Dadurch werden IntelliSense-Unterstützung für Variablen. Dadurch können Sie ihre Eigenschaften und andere Elemente anzeigen, während der Eingabe im Code.  
  
-   Es nutzt die Vorteile der typüberprüfung Compiler. Anweisungen, die zur Laufzeit aufgrund von Fehlern, z. B. Überlauf fehlschlagen können abzufangen. Auch fängt Sie Aufrufe von Methoden für Objekte, die sie unterstützen.  
  
-   Es führt zu einer schnelleren Ausführung des Codes.  
  
## <a name="most-efficient-data-types"></a>Die effizienteste-Datentypen  
 Für Variablen, die nie Addieren von Brüchen enthalten, sind die ganzzahlige Datentypen effizienter als die nicht ganzzahligen Typen. In Visual Basic `Integer` und `UInteger` sind die effizientesten numerischen Typen.  
  
 Bei Bruchzahlen `Double` ist der effizienteste Datentyp aus, da die Prozessoren auf den aktuellen Plattformen Operationen mit Gleitkommazahlen mit doppelter Genauigkeit ausführen. Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.  
  
## <a name="specifying-data-type"></a>Angeben eines Datentyps  
 Verwenden der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) zum Deklarieren einer Variablen eines bestimmten Typs. Gleichzeitig können Sie ihre Zugriffsebene angeben, mit der [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md), ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselworts, wie in der folgende.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Zeichen-Konvertierung  
 Die `AscW` und `ChrW` Funktionen, die im Unicode-Format ausgeführt werden. Verwenden Sie diese vorzuziehen, `Asc` und `Chr`, müssen die in und aus Unicode übersetzen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Numerische Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense)
