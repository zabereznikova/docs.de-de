---
title: "Value Types and Reference Types | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
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
  - "reference data types"
  - "reference types"
  - "value types"
  - "value data types"
  - "types [Visual Basic]"
  - "data types [Visual Basic], value types"
  - "data types [Visual Basic], reference types"
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Value Types and Reference Types
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In Visual Basic werden Datentypen auf Grundlage ihrer Klassifizierung implementiert.  Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Datentypen können in Abhängigkeit davon klassifiziert werden, ob von einer Variablen eines bestimmten Typs eigene Daten oder ein Zeiger auf die Daten gespeichert werden.  Wenn der Datentyp eigene Daten speichert, ist es ein *Werttyp*. Wenn er einen Zeiger auf die Daten an einer anderen Stelle im Speicher enthält, ist es ein *Verweistyp*.  
  
## Werttypen  
 Ein Datentyp ist dann ein *Werttyp*, wenn die Daten in der eigenen Speicherbelegung enthalten sind.  Werttypen umfassen Folgendes:  
  
-   Alle numerischen Datentypen  
  
-   `Boolean`, `Char` und `Date`  
  
-   Alle Strukturen, auch wenn ihre Member Verweistypen sind  
  
-   Enumerationen, da der zugrunde liegende Typ immer `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` oder `ULong` ist  
  
 Jede Struktur ist ein Werttyp, auch wenn sie Verweistyp Member enthält.  Aus diesem Grund werden Werttypen wie `Char` und `Integer` von .NET Framework\-Strukturen implementiert.  
  
 Werttypen können mit dem reservierten Schlüsselwort deklariert werden, z. B. mit `Decimal`.  Sie können das `New`\-Schlüsselwort auch verwenden, um einen Werttyp zu initialisieren.  Dies ist besonders nützlich, wenn der Typ einen Konstruktor besitzt, der Parameter verwendet.  Ein Beispiel dafür ist der <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>\-Konstruktor, der einen neuen `Decimal`\-Wert aus den bereitgestellten Teilen erstellt.  
  
## Verweistypen  
 Ein *Verweistyp* enthält einen Zeiger auf einen anderen Speicherort, der die Daten enthält.  Verweistypen umfassen Folgendes:  
  
-   `String`  
  
-   Alle Arrays, auch wenn ihre Elemente Werttypen sind  
  
-   Klassentypen, z. B. <xref:System.Windows.Forms.Form>  
  
-   Delegaten  
  
 Eine Klasse ist ein *Verweistyp*.  Daher werden Verweistypen wie `Object` und `String` von [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klassen unterstützt.  Beachten Sie, dass jedes Array einen Referenztyp darstellt, auch wenn seine Member Werttypen sind.  
  
 Da jeder Referenztyp ein zugrunde liegendes .NET Framework\-Klasse dargestellt wird, müssen Sie das [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)\-Schlüsselwort verwenden, wenn Sie initialisieren.  Mit der folgenden Anweisung wird ein Array initialisiert.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## Elemente, die keine Typen sind  
 Die folgenden Programmierelemente sind keine Typen, weil Sie keines dieser Elemente als Datentyp für ein deklariertes Element angeben können:  
  
-   Namespaces  
  
-   Module  
  
-   Ereignisse  
  
-   Eigenschaften und Prozeduren  
  
-   Variablen, Konstanten und Felder  
  
## Arbeiten mit dem Object\-Datentyp  
 Sie können einer Variablen vom Datentyp `Object` entweder einen Verweistyp oder einen Werttyp zuweisen.  Eine `Object`\-Variable enthält immer einen Zeiger auf die Daten, nie die Daten an sich.  Wenn Sie jedoch einer `Object`\-Variablen einen Werttyp zuweisen, verhält sie sich so, als enthielte sie eigene Daten.  Weitere Informationen finden Sie unter [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Sie können ermitteln, ob eine `Object`\-Variable als Verweistyp oder Werttyp nach dem Übergeben dieser der <xref:Microsoft.VisualBasic.Information.IsReference%2A>\-Methode in der <xref:Microsoft.VisualBasic.Information>\-Klasse des <xref:Microsoft.VisualBasic?displayProperty=fullName>\-Namespace verfährt.  <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName> gibt `True` zurück, wenn der Inhalt der `Object`\-Variablen einen Verweistyp darstellt.  
  
## Siehe auch  
 [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)