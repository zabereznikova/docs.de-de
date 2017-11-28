---
title: 'Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 375cab76063e4c77515d6b05b42f2d97ff3efc44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierhandbuch)
In folgendem Beispiel werden Zeiger verwendet, um Bytes aus einem Array in ein anderes zu kopieren.  
  
 In diesem Beispiel wird das Schlüsselwort [unsafe](../../../csharp/language-reference/keywords/unsafe.md) verwendet, mit dem Sie Zeiger in der `Copy`-Methode verwenden können. Die Anweisung [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) wird verwendet, um Zeiger auf das Quell- und Zielarray zu deklarieren. Dadurch wird der Speicherort des Quell- und Zielarrays im Speicher *angeheftet*, damit diese bei der automatischen Speicherbereinigung nicht verschoben werden. Die Speicherblöcke der Arrays werden gelöst, wenn der `fixed`-Block abgeschlossen wird. Da die `Copy`-Methode in diesem Beispiel das Schlüsselwort `unsafe` verwendet, muss sie mit der Compileroption **/unsafe** kompiliert werden. Klicken Sie mit der rechten Maustaste auf den Projektnamen, und klicken Sie anschließend auf **Eigenschaften**, um die Option in Visual Studio festzulegen. Wählen Sie auf der Registerkarte **Build** die Option **Unsicheren Code zulassen**.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [-unsafe (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [Garbage Collection](../../../standard/garbage-collection/index.md)
