---
title: "Type parameters cannot be used as qualifiers | Microsoft Docs"
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
  - "vbc32098"
  - "bc32098"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32098"
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type parameters cannot be used as qualifiers
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Programmierelement wird mit einem Qualifizierungspfad qualifiziert, der einen Typparameter enthält.  
  
 Ein Typparameter stellt die Anforderung eines Typs dar, der beim Erstellen des generischen Typs bereitgestellt werden muss.  Er stellt keinen bestimmten definierten Typ dar.  Ein Qualifizierungspfad darf nur Elemente enthalten, die zur Kompilierzeit definiert werden.  
  
 Dieser Fehler kann durch die folgenden Anweisungen generiert werden.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **Fehler\-ID:** BC32098  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie den Typparameter aus dem Qualifizierungspfad, oder ersetzen Sie ihn durch einen definierten Typ.  
  
2.  Wenn Sie einen konstruierten Typ zum Ermitteln des zu qualifizierenden Programmierelements benötigen, müssen Sie zusätzliche Programmlogik verwenden.  
  
## Siehe auch  
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)