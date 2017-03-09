---
title: "Variablendeklaration in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Variablen [Visual Basic], Deklarieren"
  - "Membervariablen, Deklarationen"
  - "Dim-Anweisung, Variablendeklaration"
  - "Deklarieren von Variablen"
  - "Variablen [Visual Basic], Bereich"
  - "Variablen [Visual Basic], Datentypen"
  - "Datentypen [Visual Basic], Variablendeklarationen"
  - "Lebensdauer, Variablen"
  - "Variablen [Visual Basic], Lebensdauer"
  - "Zugriffsebenen, Variablen"
  - "Bereich, Deklarationsanweisungen"
  - "Variablen [Visual Basic], Zugriffsebene"
  - "Lokale Variablen, Deklarationen"
  - "Bereich, Variablen"
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 31
---
# Variablendeklaration in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Variablen werden deklariert, um ihren Namen und ihre Merkmale festzulegen.  Deklarationsanweisungen für Variablen werden mit der [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) durchgeführt.  Die Merkmale einer Variablen werden durch ihren Speicherort und ihren Inhalt bestimmt.  
  
 Informationen zu Regeln und Überlegungen hinsichtlich der Benennung von Variablen finden Sie unter [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Deklarationsebenen  
  
### Lokale Variablen und Membervariablen  
 *Lokale Variablen* sind Variablen, die innerhalb einer Prozedur deklariert wurden.  Eine *Membervariable* ist ein Member eines [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Typs. Sie wird auf Modulebene in einer Klasse, einer Struktur oder einem Modul deklariert, darf jedoch nicht innerhalb einer internen Prozedur der betreffenden Klasse oder Struktur oder des Moduls deklariert werden.  
  
### Freigegebene Variable und Instanzvariablen  
 In Klassen oder Strukturen ist bei der Kategorisierung einer Membervariablen entscheidend, ob sie freigegeben ist oder nicht.  Mit dem [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)\-Schlüsselwort deklarierte Variablen sind *freigegebene Variablen*, die als einzelnes, von allen Instanzen der Klasse oder Struktur gemeinsam genutztes Exemplar vorliegen.  
  
 Andernfalls handelt es sich um eine *Instanzvariable*, von der für jede Instanz der Klasse oder Struktur eine separate Kopie erstellt wird.  Eine solche Kopie einer Instanzvariablen ist nur für die Instanz der Klasse oder Struktur verfügbar, in denen sie erstellt wurde.  Sie ist unabhängig von Kopie der Instanzvariable in jeder anderen Instanz der Klasse oder Struktur.  
  
## Deklarieren des Datentyps  
 Mit der [As](../../../../visual-basic/language-reference/statements/as-clause.md)\-Klausel in der Deklarationsanweisung definieren Sie den Datentyp oder den Objekttyp der deklarierten Variablen.  Für Variablen kann einer der folgenden Typen angegeben werden:  
  
-   Ein elementarer Datentyp, z. B. `Boolean`, `Long` oder `Decimal`  
  
-   Ein zusammengesetzter Datentyp, z. B. ein Array oder eine Struktur  
  
-   Ein Objekttyp oder eine Klasse, der bzw. die in der vorliegenden oder einer anderen Anwendung definiert ist  
  
-   Eine [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klasse, wie beispielsweise <xref:System.Windows.Forms.Label> oder <xref:System.Windows.Forms.TextBox>  
  
-   Ein Schnittstellentyp, z. B. <xref:System.IComparable> oder <xref:System.IDisposable>  
  
 In einer Anweisung können mehrere Variablen deklariert werden, ohne dass der Datentyp dazu wiederholt werden muss.  In den folgenden Anweisungen werden die Variablen `i`, `j` und `k` mit dem Typ `Integer`, die Variablen `l` und `m` mit dem Typ `Long` und die Variablen `x` und `y` mit dem Typ `Single` deklariert:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Weitere Informationen zu Datentypen finden Sie unter [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md).  Weitere Informationen zu Objekten finden Sie unter [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) und [Programming with Components](../Topic/Programming%20with%20Components.md).  
  
## Lokaler Typrückschluss  
 *Typrückschlüsse* dienen zur Bestimmung der Datentypen von lokalen Variablen, die ohne eine `As`\-Klausel deklariert wurden.  Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab.  Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben.  Im folgenden Beispiel sind `num1` und `num2` stark typisiert als ganze Zahlen.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/variable-declaration_1.vb)]  
  
 Wenn Sie lokalen Typrückschluss verwenden möchten, müssen Sie `Option Infer` auf `On` festlegen.  Weitere Informationen finden Sie unter [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) und [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## Eigenschaften von deklarierten Variablen  
 Als *Lebensdauer* einer Variablen wird die Zeitspanne bezeichnet, in der sie genutzt werden kann.  Im Allgemeinen existiert eine Variable ebenso lange wie das Element \(z. B. eine Prozedur oder Klasse\), in der sie deklariert wurde.  Wenn die Variable nicht muss, um das vorhandene über die gesamte Lebensdauer des enthaltenden Elements hinaus fortzusetzen, müssen Sie, um nichts unternehmen, das in der Deklaration speziell ist.  Wenn die Variable länger als ihr enthaltendes Element bestehen bleiben muss, können Sie das `Static`\-Schlüsselwort oder das `Shared`\-Schlüsselwort in ihre `Dim`\-Anweisung einfügen.  Weitere Informationen finden Sie unter [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 Der *Gültigkeitsbereich* einer Variablen umfasst die gesamte Codemenge, die auf die Variable zugreifen kann, ohne ihren Namen zu qualifizieren.  Welchen Gültigkeitsbereich eine Variable hat, hängt davon ab, wo sie deklariert wurde.  In einem bestimmten Bereich positionierter Code kann auf die in diesem Bereich definierten Variablen zugreifen, ohne ihren Namen zu qualifizieren.  Weitere Informationen finden Sie unter [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Die *Zugriffsebene* einer Variablen bestimmt, in welchem Umfang Code zum Zugriff auf die Variable berechtigt ist.  Sie wird durch den in der `Dim`\-Anweisung verwendeten Zugriffsmodifizierer \(z. B. [Public](../../../../visual-basic/language-reference/modifiers/public.md) oder [Private](../../../../visual-basic/language-reference/modifiers/private.md)\) festgelegt.  Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Siehe auch  
 [How to: Create a New Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)   
 [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)