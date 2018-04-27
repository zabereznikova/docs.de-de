---
title: Wert- und Verweistypen
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cbab25e4af6b96ae22fe18d0b8a8fdbc7a7c7a7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="value-types-and-reference-types"></a>Wert- und Verweistypen
In Visual Basic werden Datentypen basierend auf deren Klassifizierung implementiert. Die Visual Basic-Datentypen können, ob eine Variable eines bestimmten Typs eigene Daten oder ein Zeiger auf die Daten gespeichert klassifiziert werden. Wenn sie einen eigenen Datenspeicher wird ein *Werttyp*; Wenn es einen Zeiger auf die Daten an anderer Stelle im Arbeitsspeicher enthält es ein *Verweistyp*.  
  
## <a name="value-types"></a>Werttypen  
 Ein Datentyp ist ein *Werttyp* , wenn sie die Daten in einem eigenen speicherbelegung enthält. Die folgenden: Werttypen  
  
-   Alle numerischen Datentypen  
  
-   `Boolean`, `Char` und `Date`  
  
-   Alle Strukturen, auch wenn ihre Member Verweistypen sind.  
  
-   Enumerationen, da der zugrunde liegende Typ, immer ist `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, oder `ULong`  
  
 Jede Struktur ist ein Werttyp ist, auch wenn sie Verweistypmember enthält. Aus diesem Grund Werttypen wie z. B. `Char` und `Integer` von .NET Framework-Strukturen implementiert werden.  
  
 Sie können einen Werttyp deklarieren, indem Sie dem reservierten Schlüsselwort, z. B. `Decimal`. Sie können auch die `New` Schlüsselwort, um einen Werttyp zu initialisieren. Dies ist besonders nützlich, wenn der Typ einen Konstruktor verfügt, der Parameter akzeptiert. Ein Beispiel hierfür ist die <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> Konstruktor, der eine neue erstellt `Decimal` Wert aus den angegebenen teilen.  
  
## <a name="reference-types"></a>Verweistypen  
 Ein *Verweistyp* enthält einen Zeiger auf einen anderen Speicherort, der die Daten enthält. Verweistypen umfassen Folgendes:  
  
-   `String`  
  
-   Alle Arrays, auch wenn ihre Elemente Werttypen sind.  
  
-   Klassentypen Sie, z. B. <xref:System.Windows.Forms.Form>  
  
-   Delegaten  
  
 Eine Klasse ist eine *Verweistyp*. Aus diesem Grund verweisen auf Typen wie z. B. `Object` und `String` werden von unterstützt [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Klassen. Beachten Sie, dass jedes Array ein Verweistyp ist, selbst wenn ihre Elemente Werttypen sind.  
  
 Da jede Verweistyp eine zugrunde liegenden .NET Framework-Klasse darstellt, verwenden Sie die [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort, die Sie bei der Initialisierung. Die folgende Anweisung wird ein Array initialisiert.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elemente, die keine Typen sind  
 Die folgenden Programmierelemente qualifizieren wie Typen, Sie nicht, da Sie diese nicht als Datentyp für eine deklarierte Element festlegen können:  
  
-   Namespaces  
  
-   Module  
  
-   Ereignisse  
  
-   Eigenschaften und Prozeduren  
  
-   Variablen, Konstanten und Felder  
  
## <a name="working-with-the-object-data-type"></a>Arbeiten mit dem Object-Datentyp  
 Sie können ein Verweistyp oder ein Werttyp zu einer Variablen zuweisen der `Object` -Datentyp. Ein `Object` Variable enthält immer einen Zeiger auf die Daten, die nie die Daten selbst. Jedoch, wenn Sie einen Werttyp an Zuweisen einer `Object` -Variable ist, verhält sich, als ob es eine eigene Daten enthält. Weitere Informationen finden Sie unter [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Können Sie herausfinden, ob ein `Object` Variable dient als ein Verweistyp oder ein Werttyp durch Übergabe an die <xref:Microsoft.VisualBasic.Information.IsReference%2A> Methode in der <xref:Microsoft.VisualBasic.Information> Klasse von der <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Gibt `True` Wenn der Inhalt der `Object` Variable steht für einen Referenztyp darstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Auf NULL festlegbare Werttypen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
