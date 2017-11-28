---
title: stackalloc (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords: stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad4453f889a344fcd44dfad44a30fef07380b6a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="stackalloc-c-reference"></a>stackalloc (C#-Referenz)
Das Schlüsselwort `stackalloc` wird in unsicherem Codekontext verwendet, um dem Stapel einen Speicherblock zuzuweisen.  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Schlüsselwort ist nur in lokalen Variableninitialisierern gültig. Folgender Code verursacht Compilerfehler.  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 Da Zeigertypen beteiligt sind, benötigt `stackalloc` einen [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Kontext. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 Genau wie [_alloca](/cpp/c-runtime-library/reference/alloca) befindet sich `stackalloc` in der C-Laufzeitbibliothek.  
  
 Im folgenden Beispiel werden die ersten 20 Zahlen der Fibonacci-Folge berechnet und angezeigt. Jede Zahl bildet die Summe der beiden vorherigen Zahlen. Im Code wird dem Stapel, nicht dem Heap, ein Speicherblock zugewiesen, der groß genug ist, um 20 Elemente vom Typ `int` zu enthalten. Die Adresse des Blocks wird im Zeiger `fib` gespeichert. Dieser Speicher unterliegt nicht der automatischen Speicherbereinigung und muss daher nicht (mithilfe von [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)) angeheftet werden. Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der definierenden Methode begrenzt. Sie können den Speicher nicht freigeben, bevor die Methode zurückgibt.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a>Sicherheit  
 Unsicherer Code ist unsicherer als sichere Alternativen. Allerdings werden mit der Verwendung von `stackalloc` automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert. Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
