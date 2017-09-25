---
title: extern-Alias (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- alias_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66b399aaf6d4b3ba27957f3eadad3c1079ed2e90
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="extern-alias-c-reference"></a>extern-Alias (C#-Referenz)
Sie müssen möglicherweise auf zwei Versionen von Assemblys verweisen, die denselben vollqualifizierten Namen besitzen. Beispielsweise müssen Sie möglicherweise zwei oder mehr Versionen einer Assembly in derselben Anwendung verwenden. Indem Sie einen externen Assemblyalias verwenden, können die Namespaces jeder Assembly in Namespaces auf Stammebene, benannt durch den Alias, umschlossen werden, was es ihnen ermöglicht, von derselben Datei verwendet zu werden.  
  
> [!NOTE]
>  Das [extern](../../../csharp/language-reference/keywords/extern.md)-Schlüsselwort dient außerdem als Methodenmodifizierer, der eine Methode deklariert, die in nicht verwaltetem Code geschrieben wurde.  
  
 Um auf zwei Assemblys mit demselben vollqualifizierten Typnamen zu verweisen, muss ein Alias in einer Befehlszeile wie folgt angegeben werden:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 Dies erstellt die externen Aliase `GridV1` und `GridV2`. Um diese Aliase aus einem Programm heraus zu verwenden, verweisen Sie mithilfe des `extern`-Schlüsselworts auf sie. Zum Beispiel:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Jede externe Aliasdeklaration führt einen zusätzlichen Namespace auf Stammebene ein, parallel zum (aber nicht innerhalb des) globalen Namespace. Daher kann mithilfe des vollqualifizierten Namens, der als Stamm des entsprechenden Namespacealias dient, auf Typen jeder Assembly eindeutig verwiesen werden.  
  
 Im vorherigen Beispiel wäre `GridV1::Grid` das Steuerelement von `grid.dll`, und `GridV2::Grid` wäre das Steuerelement von `grid20.dll`.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Namespaceschlüsselwörter](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Operator ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [/reference (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)

