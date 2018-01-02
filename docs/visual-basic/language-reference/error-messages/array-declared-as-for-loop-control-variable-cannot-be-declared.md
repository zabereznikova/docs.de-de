---
title: "Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords: BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef36f14d5323a4592afe59573e249d8cfb218df9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.
Ein `For Each` Schleife verwendet ein Array als seine *Element* Iterationsvariable aber das Array initialisiert.  
  
 Die folgenden Anweisungen zeigen, wie dieser Fehler generiert werden kann.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Die erste `For Each` -Anweisung ist die richtige Methode zum Zugriff auf Elemente des `arrayList`. Die zweite `For Each` -Anweisung generiert diesen Fehler.  
  
 **Fehler-ID:** BC32039  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Initialisierung aus der Deklaration der *Element* Iterationsvariable.  
  
## <a name="see-also"></a>Siehe auch  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Sammlungen](../../../standard/collections/index.md)
