---
title: Werttypen und Verweistypen | Microsoft-Dokumentation
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
- reference data types
- reference types
- value types
- value data types
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
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
ms.openlocfilehash: de8016b4b2a5550b32373a41c89a484fa996c596
ms.lasthandoff: 03/13/2017

---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
In Visual Basic werden die Datentypen entsprechend ihrer Klassifizierung implementiert. Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Datentypen können, ob eine Variable eines bestimmten Typs eigene Daten oder ein Zeiger auf die Daten speichert klassifiziert werden. Wenn seine eigenen Daten speichert, es ist ein *Werttyp*, wenn er einen Zeiger auf Daten an anderer Stelle im Speicher enthält, ist ein *Referenztyp*.  
  
## <a name="value-types"></a>Werttypen  
 Ein Datentyp ist ein *Werttyp* , wenn sie die Daten in eine eigene speicherbelegung enthält. Die folgenden: Werttypen  
  
-   Alle numerischen Datentypen  
  
-   `Boolean`, `Char` und `Date`  
  
-   Alle Strukturen, auch wenn ihre Member Verweistypen sind.  
  
-   Enumerationen, da der zugrunde liegende Typ immer ist `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, oder`ULong`  
  
 Jede Struktur ist ein Werttyp, auch wenn sie Verweistypmember enthält. Aus diesem Grund Werttypen wie `Char` und `Integer` vom .NET Framework-Strukturen implementiert werden.  
  
 Sie können einen Werttyp deklarieren, indem Sie mit dem reservierten Schlüsselwort, z. B. `Decimal`. Sie können auch die `New` -Schlüsselwort verwenden, um einen Werttyp zu initialisieren. Dies ist besonders nützlich, wenn der Typ einen Konstruktor verfügt, der Parameter akzeptiert. Ein Beispiel hierfür ist die <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>-Konstruktor, der ein neues erstellt `Decimal` Wert aus den bereitgestellten Teilen.</xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>  
  
## <a name="reference-types"></a>Verweistypen  
 Ein *Referenztyp* enthält einen Zeiger auf einen anderen Speicherort, der die Daten enthält. Verweistypen umfassen Folgendes:  
  
-   `String`  
  
-   Alle Arrays, auch wenn ihre Elemente Werttypen sind.  
  
-   Klassentypen Sie, z. B.<xref:System.Windows.Forms.Form></xref:System.Windows.Forms.Form>  
  
-   Delegaten  
  
 Eine Klasse ist ein *Referenztyp*. Aus diesem Grund Verweistypen wie `Object` und `String` wird von [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Klassen. Beachten Sie, dass jedes Array einen Verweistyp handelt, auch wenn seine Member Werttypen sind.  
  
 Da jeder Referenztyp eine zugrunde liegende .NET Framework-Klasse darstellt, müssen Sie verwenden die [Operator New](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort, die Sie bei der Initialisierung. Die folgende Anweisung initialisiert ein Array.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elemente, die keine Typen sind  
 Die folgenden Programmierelemente qualifizieren wie Typen, Sie nicht, da Sie diese nicht als Datentyp für ein deklariertes Element angeben können:  
  
-   Namespaces  
  
-   Module  
  
-   Ereignisse  
  
-   Eigenschaften und Prozeduren  
  
-   Variablen, Konstanten und Felder  
  
## <a name="working-with-the-object-data-type"></a>Arbeiten mit den Object-Datentyp  
 Sie können ein Referenztyp oder ein Werttyp zu einer Variablen zuweisen der `Object` -Datentyp. Ein `Object` -Variable enthält immer einen Zeiger auf die Daten, nie die Daten selbst. Jedoch wenn Sie einen Werttyp zum Zuweisen einer `Object` -Variable verhält sich als enthielte sie eigene Daten. Weitere Informationen finden Sie unter [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Können Sie ermitteln, ob ein `Object` Variablen fungiert als ein Referenztyp oder ein Werttyp durch Übergabe an die <xref:Microsoft.VisualBasic.Information.IsReference%2A>-Methode in der <xref:Microsoft.VisualBasic.Information>Klasse von der <xref:Microsoft.VisualBasic?displayProperty=fullName>Namespace.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.Information> </xref:Microsoft.VisualBasic.Information.IsReference%2A> <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>Gibt `True` Wenn der Inhalt der `Object` Variable einen Referenztyp darstellt.</xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>Siehe auch  
 [Auf NULL festlegbare Werttypen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
