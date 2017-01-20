---
title: "GetType Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.GetType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetType operator"
  - "GetType keyword"
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# GetType Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt für den angegebenen Typ ein <xref:System.Type>\-Objekt zurück.  Das <xref:System.Type>\-Objekt stellt Informationen über den Typ bereit, z. B. seine Eigenschaften, Methoden und Ereignisse.  
  
## Syntax  
  
```  
GetType(typename)  
```  
  
#### Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`typename`|Der Name des Typs, über den Informationen benötigt werden.|  
  
## Hinweise  
 Der Operator `GetType` gibt das <xref:System.Type>\-Objekt für den angegebenen `typename` zurück.  Sie können den Namen eines beliebigen Typs übergeben, der in `typename` definiert ist.  Hierzu gehören folgende Elemente:  
  
-   Ein beliebiger Visual Basic\-Datentyp, z. B. `Boolean` oder `Date`.  
  
-   Eine beliebige Klasse, Struktur, Schnittstelle bzw. ein beliebiges Modul von .NET Framework, z. B. <xref:System.ArgumentException?displayProperty=fullName> oder <xref:System.Double?displayProperty=fullName>.  
  
-   Eine beliebige Klasse, Struktur, Schnittstelle bzw. ein beliebiges Modul, die von der Anwendung definiert werden.  
  
-   Ein beliebiges von der Anwendung definiertes Array.  
  
-   Ein beliebiger von der Anwendung definierter Delegat.  
  
-   Eine beliebige von Visual Basic, .NET Framework oder der Anwendung definierte Enumeration.  
  
 Wenn Sie das Typobjekt einer Objektvariablen abrufen möchten, müssen Sie die <xref:System.Type.GetType%2A?displayProperty=fullName>\-Methode verwenden.  
  
 Der Operator `GetType` kann unter folgenden Umständen hilfreich sein:  
  
-   Sie müssen zur Laufzeit auf die Metadaten für einen Typ zugreifen.  Das <xref:System.Type>\-Objekt gibt Metadaten an, z. B. Typmember und Bereitstellungsinformationen.  Sie benötigen diese Angaben z. B., um über einer Assembly eine Reflektion auszuführen.  Weitere Informationen finden Sie unter <xref:System.Reflection?displayProperty=fullName>.  
  
-   Sie möchten zwei Objektverweise vergleichen, um festzustellen, ob sie auf Instanzen des gleichen Typs verweisen.  Ist dies der Fall, gibt `GetType` Verweise auf das gleiche <xref:System.Type>\-Objekt zurück.  
  
## Beispiel  
 In den folgenden Beispielen wird die Verwendung des Operators `GetType` demonstriert.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## Siehe auch  
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)