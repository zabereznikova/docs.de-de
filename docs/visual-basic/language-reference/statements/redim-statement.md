---
title: "ReDim Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ReDim"
  - "vb.Preserve"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "fixed-length strings, declaring"
  - "ReDim statement, syntax"
  - "dynamic arrays, ReDim statement"
  - "arrays [Visual Basic], reallocating"
  - "arrays [Visual Basic], reinitializing"
  - "arrays [Visual Basic], dimensions"
  - "scalars, and arrays"
  - "scalars"
  - "declarations, dynamic arrays"
  - "variables [Visual Basic], scalar"
  - "ReDim statement"
  - "data types [Visual Basic], assigning"
  - "As keyword, in ReDim statement"
  - "To keyword, ReDim statement"
  - "arrays [Visual Basic], declaring"
  - "Preserve keyword, ReDim statement"
  - "storage, allocating"
  - "arrays [Visual Basic], and scalars"
  - "declaration statements"
  - "scalar variables"
ms.assetid: ad1c5e07-dcd7-4ae1-a79e-ad3f2dcc2083
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# ReDim Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Reserviert Speicherplatz für eine Arrayvariable neu.  
  
## Syntax  
  
```  
ReDim [ Preserve ] name(boundlist) [ ,  name(boundlist) [, ... ] ]  
```  
  
## Teile  
  
|Begriff|Definition|  
|-------------|----------------|  
|`Preserve`|Dies ist optional.  Modifizierer zum Beibehalten der Daten im vorhandenen Array, wenn lediglich die Größe der letzten Dimension geändert wird.|  
|`name`|Erforderlich.  Name der Arrayvariablen.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`boundlist`|Erforderlich.  Liste der Grenzen jeder Dimension des neu definierten Arrays.|  
  
## Hinweise  
 Sie können die `ReDim`\-Anweisung verwenden, um die Größe einer oder mehrerer Dimensionen eines Arrays zu ändern, das bereits deklariert wurde.  Wenn Sie ein großes Array verwenden und einige Elemente nicht mehr benötigen, kann `ReDim` durch das Reduzieren der Arraygröße Arbeitsspeicher freigeben.  Falls Ihr Array mehr Elemente benötigt, kann `ReDim` diese auch hinzufügen.  
  
 Die `ReDim`\-Anweisung ist nur für Arrays bestimmt.  Sie gilt nicht für Skalare \(Variablen, die nur einen einzelnen Wert enthalten\), Auflistungen oder Strukturen.  Beachten Sie Folgendes: Wenn Sie für eine Variable den Typ `Array` deklarieren, verfügt die `ReDim`\-Anweisung nicht über genügend Typinformationen zum Erstellen des neuen Arrays.  
  
 Sie können `ReDim` nur auf Prozedurebene verwenden.  Aus diesem Grund muss der Deklarationskontext für die Variable eine Prozedur sein. Folgende Kontexte sind nicht möglich: Quelldatei, Namespace, Schnittstelle, Klasse, Struktur, Modul oder Block.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
## Regeln  
  
-   **Mehrere Variablen:** Sie können die Größe mehrerer Arrayvariablen in derselben Deklarationsanweisung ändern und die Teile `name` und `boundlist` für jede Variable angeben.  Mehrere Variablen werden durch Kommas voneinander getrennt.  
  
-   **Arraygrenzen:** Für jeden Eintrag in `boundlist` können die unteren und oberen Grenzen der Dimension angegeben werden.  Die untere Grenze ist immer 0 \(null\).  Die Obergrenze ist der größtmögliche Indexwert für diese Dimension, nicht die Länge der Dimension \(dies ist die obere Grenze plus 1\).  Der Index für jede Dimension kann zwischen 0 und dem Wert der oberen Grenze variieren.  
  
     Die Anzahl der Dimensionen in `boundlist` muss mit der ursprünglichen Anzahl von Dimensionen \(Rang\) des Arrays übereinstimmen.  
  
-   **Datentypen:** Mit der `ReDim`\-Anweisung kann der Datentyp einer Arrayvariablen oder ihrer Elemente nicht geändert werden.  
  
-   **Initialisierung:** Mit der `ReDim`\-Anweisung können keine neuen Initialisierungswerte für die Arrayelemente bereitgestellt werden.  
  
-   **Rang:** Mit der `ReDim`\-Anweisung kann der Rang \(Anzahl von Dimensionen\) des Arrays nicht geändert werden.  
  
-   **Ändern der Größe mit Beibehaltung \(Preserve\):** Bei Verwendung von `Preserve` können Sie nur die Größe der letzten Dimension des Arrays ändern.  Für alle anderen Dimensionen müssen Sie die Grenze des vorhandenen Arrays angeben.  
  
     Wenn das Array nur eine Dimension hat, können Sie beispielsweise die Größe dieser Dimension ändern und trotzdem den gesamten Inhalt des Arrays beibehalten. Dies liegt daran, dass Sie die letzte und einzige Dimension ändern.  Wenn das Array aber über zwei oder mehr Dimensionen verfügt, können Sie bei Verwendung von `Preserve` nur die Größe der letzten Dimension ändern.  
  
-   **Eigenschaften:** Sie können `ReDim` für eine Eigenschaft verwenden, die ein Array von Werten enthält.  
  
## Verhalten  
  
-   **Arrayersatz:** `ReDim`Gibt das vorhandene Array frei und erstellt ein neues Array mit demselben Rang.  Das neue Array ersetzt das freigegebene Array in der Arrayvariablen.  
  
-   **Initialisierung ohne Beibehaltung \(Preserve\):** Wenn Sie kein `Preserve`\-Element angeben, werden die Elemente des neuen Arrays von `ReDim` mit dem Standardwert für ihren Datentyp initialisiert.  
  
-   **Initialisierung mit Beibehaltung \(Preserve\):** Wenn Sie `Preserve` angeben, kopiert Visual Basic die Elemente aus dem vorhandenen Array in das neue Array.  
  
## Beispiel  
 Im folgenden Beispiel wird die Größe der letzten Dimension eines dynamischen Arrays erhöht, ohne dass vorhandene Daten im Array verloren gehen. Anschließend wird die Größe mit einem Teilverlust der Daten reduziert.  Zuletzt wird die Größe zurück auf den Originalwert reduziert, und alle Arrayelemente werden neu initialisiert.  
  
 [!code-vb[VbVbalrStatements#52](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/redim-statement_1.vb)]  
  
 Mit der `Dim`\-Anweisung wird ein neues Array mit drei Dimensionen erstellt.  Jede Dimension wird mit einer Grenze von 10 deklariert, sodass der Arrayindex für jede Dimension von 0 bis 10 reichen kann.  Im folgenden Text werden die drei Dimensionen als Ebene \(Layer\), Zeile \(Row\) und Spalte \(Column\) bezeichnet.  
  
 Das erste `ReDim`\-Element erstellt ein neues Array, mit dem das vorhandene Array in der Variablen `intArray` ersetzt wird.  `ReDim` kopiert alle Elemente aus dem vorhandenen Array in das neue Array.  Außerdem werden auf jeder Ebene am Ende jeder Zeile zehn weitere Spalten hinzugefügt, und die Elemente in diesen neuen Spalten werden mit dem Wert 0 initialisiert \(Standardwert von `Integer`, dem Elementtyp des Arrays\).  
  
 Das zweite `ReDim`\-Element erstellt ein neues Array und kopiert alle passenden Elemente.  Am Ende jeder Zeile auf jeder Ebene gehen aber fünf Spalten verloren.  Dies ist kein Problem, wenn Sie mit der Verwendung dieser Spalten fertig sind.  Durch das Reduzieren der Größe eines großen Arrays kann Speicher freigegeben werden, den Sie nicht mehr benötigen.  
  
 Das dritte `ReDim`\-Element erstellt ein weiteres neues Array und entfernt auf jeder Ebene weitere fünf Spalten vom Ende jeder Zeile.  Dieses Mal werden keine vorhandenen Elemente kopiert.  Mit dieser Anweisung wird das Array auf seine ursprüngliche Größe zurückgesetzt.  Da die Anweisung den `Preserve`\-Modifizierer nicht enthält, werden alle Arrayelemente auf ihre ursprünglichen Standardwerte festgelegt.  
  
 Weitere Beispiele finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Siehe auch  
 <xref:System.IndexOutOfRangeException>   
 [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Erase Statement](../../../visual-basic/language-reference/statements/erase-statement.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)   
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)