---
title: "CType-Funktion (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.CType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Ausdruckskonvertierungsergebnisse"
  - "Explizite Konvertierung von Datentypen"
  - "CType-Funktion"
  - "Konvertierungen, Ausdrücke"
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CType-Funktion (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt das Ergebnis einer expliziten Konvertierung eines Ausdrucks in einen angegebenen Datentyp, ein Objekt, eine Struktur, Klasse oder Schnittstelle zurück.  
  
## Syntax  
  
```  
CType(expression, typename)  
```  
  
## Teile  
 `expression`  
 Jeder gültige Ausdruck.  Wenn der Wert von `expression` außerhalb des von `typename` definierten Bereichs liegt, wird von Visual Basic eine Ausnahme ausgelöst.  
  
 `typename`  
 Ein beliebiger Ausdruck, der innerhalb einer `As`\-Klausel in einer `Dim`\-Anweisung zulässig ist, d. h., der Name eines beliebigen Datentyps, eines Objekts, einer Struktur, einer Klasse oder einer Schnittstelle.  
  
## Hinweise  
  
> [!TIP]
>  Sie können die folgenden Funktionen auch zum Ausführen einer Typkonvertierung verwenden:  
>   
>  -   Typkonvertierungsfunktionen, wie `CByte`, `CDbl` und `CInt`, mit denen eine Konvertierung in einen bestimmten Datentyp ausgeführt werden kann.  Weitere Informationen finden Sie unter [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
> -   [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).  Diese Operatoren erfordern, dass ein Typ von dem Anderen erbt oder diesen implementiert.  Sie können etwas bessere Leistung beim Konvertieren in und aus dem `Object`\-Datentyp bieten, als `CType`.  
  
 `CType` wird inline kompiliert. Das bedeutet, dass der Konvertierungscode Bestandteil des Codes für die Auswertung des Ausdrucks ist.  In einigen Fällen wird der Code schneller ausgeführt, da keine Prozeduren zum Ausführen der Konvertierung aufgerufen werden.  
  
 Wenn keine Konvertierung von `expression` in `typename` \(zum Beispiel von `Integer` in `Date`\) definiert ist, wird von Visual Basic zur Kompilierungszeit eine Fehlermeldung angezeigt.  
  
 Falls eine Konvertierung zur Laufzeit fehlschlägt, wird die entsprechende Ausnahme ausgelöst.  Ist eine einschränkende Konvertierung fehlerhaft, wird meist ein <xref:System.OverflowException>\-Fehler verursacht.  Wenn die Konvertierung nicht definiert ist, wird eine <xref:System.InvalidCastException> ausgelöst.  Dies kann z. B. der Fall sein, wenn `expression` vom Typ `Object` ist und für seinen Laufzeittyp keine Konvertierung in `typename` definiert ist.  
  
 Handelt es sich beim Datentyp von `expression` oder `typename` um eine von Ihnen definierte Klasse oder Struktur, können Sie `CType` für diese Klasse oder Struktur als Konvertierungsoperator definieren.  Dadurch verhält sich `CType` wie ein *überladener Operator*.  Wenn Sie einen Konvertierungsoperator definieren, können Sie nicht nur das Verhalten von Konvertierungen in und aus der Klasse oder Struktur steuern, sondern auch die ausgelösten Ausnahmen bestimmen.  
  
## Überladen  
 Der Operator `CType` kann auch für eine Klasse oder Struktur überladen werden, die außerhalb des Codes definiert ist.  Wenn in dem Code Konvertierungen in eine solche Klasse oder Struktur oder in umgekehrter Richtung durchführt werden, müssen Sie sicherstellen, dass Sie das Verhalten des betreffenden `CType`\-Operators verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Konvertieren von dynamischen Objekten  
 Typkonvertierungen für dynamische Objekte werden durch benutzerdefinierte dynamische Konvertierungen ausgeführt, bei denen die <xref:System.Dynamic.DynamicObject.TryConvert%2A>\-Methode oder die <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>\-Methode verwendet werden.  Wenn Sie mit dynamischen Objekten arbeiten, verwenden Sie zum Konvertieren des dynamischen Objekts die <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A>\-Methode.  
  
## Beispiel  
 In diesem Beispiel wird die `CType`\-Funktion zum Konvertieren eines Ausdrucks in den `Single`\-Datentyp verwendet.  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 Weitere Beispiele finden Sie unter [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## Siehe auch  
 <xref:System.OverflowException>   
 <xref:System.InvalidCastException>   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Conversion Functions](../../../visual-basic/language-reference/functions/conversion-functions.md)   
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Typkonvertierung in .NET Framework](../Topic/Type%20Conversion%20in%20the%20.NET%20Framework.md)