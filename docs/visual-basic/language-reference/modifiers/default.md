---
title: "Default (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Default"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "defaults, properties"
  - "properties [Visual Basic], default"
  - "default properties, in Visual Basic"
  - "Default keyword [Visual Basic]"
  - "default properties"
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Default (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Identifiziert eine Eigenschaft als die Standardeigenschaft ihrer Klasse, Struktur oder Schnittstelle.  
  
## Hinweise  
 Bei einer Klasse, Struktur oder Schnittstelle kann höchstens eine Eigenschaft als *Standardeigenschaft* festgelegt werden, vorausgesetzt, diese Eigenschaft nimmt mindestens einen Parameter an.  Wenn der Code auf eine Klasse oder Struktur verweist, ohne dass ein Member angegeben wird, löst Visual Basic diesen Verweis in die Standardeigenschaft auf.  
  
 Durch Standardeigenschaften wird zwar die Anzahl der Quellcodezeichen geringfügig verringert, der Code wird durch sie jedoch unter Umständen schlechter lesbar.  Wenn dem Aufrufcode die Klasse oder die Struktur, auf die verwiesen wird, nicht bekannt sind, ist unsicher, ob durch diesen Verweis auf die Klasse bzw. die Struktur selbst oder auf eine Standardeigenschaft zugegriffen wird.  Dies kann zu Compilerfehlern oder kleineren Laufzeitlogikfehlern führen.  
  
 Die Möglichkeit von Eigenschaftenfehlern lässt sich ein wenig reduzieren, wenn Sie stets die [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) verwenden, um die Compilertypüberprüfung auf `On` zu setzen.  
  
 Wenn Sie im Code eine vordefinierte Klasse oder Struktur verwenden möchten, müssen Sie festlegen, ob sie eine Standardeigenschaft besitzt. Ist dies der Fall, müssen Sie auch einen Namen für die Eigenschaft festlegen.  
  
 Aufgrund dieser Nachteile sollten Sie keine Standardeigenschaften definieren.  Zur besseren Lesbarkeit des Codes sollten Sie zudem stets explizit auf alle Eigenschaften verweisen, auch auf Standardeigenschaften.  
  
 Der `Default`\-Modifizierer kann im folgenden Kontext verwendet werden:  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Siehe auch  
 [How to: Declare and Call a Default Property in Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)