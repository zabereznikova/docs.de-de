---
title: "Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30424"
  - "bc30424"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30424"
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie haben versucht, eine Konstante als Klassen\-, Struktur\- oder Arraytyp zu deklarieren oder als Typparameter, der von einem enthaltenden generischen Typ definiert wird.  
  
 Konstanten müssen einen systeminternen Typ \(`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong` oder `UShort`\) aufweisen oder einen `Enum`\-Typ, der auf einem der ganzzahligen Typen basiert.  
  
 **Fehler\-ID:** BC30424  
  
### So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie die Konstante als systeminternen Typ oder als `Enum`\-Typ.  
  
2.  Eine Konstante kann auch einen Sonderwert aufweisen, z. B. `True`, `False` oder `Nothing`.  Der Compiler behandelt diese vordefinierten Werte als geeigneten systeminternen Typ.  
  
## Siehe auch  
 [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Datentypen](../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)