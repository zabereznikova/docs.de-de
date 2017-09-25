---
title: "new-Einschränkung (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
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
ms.openlocfilehash: 762941794184605f90443ed8f36c88ecfa50aa84
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="new-constraint-c-reference"></a>new-Einschränkung (C#-Referenz)
Die `new`-Einschränkung gibt an, dass jedes Typargument in einer generischen Klassendeklaration über einen öffentlichen parameterlosen Konstruktor verfügen muss. Der Typ kann nicht abstrakt sein, um die neue Einschränkung zu verwenden.  
  
## <a name="example"></a>Beispiel  
 Wenden Sie die `new`-Einschränkung auf einen Typparameter an, wenn Ihre generische Klasse neue Instanzen desselben Typs erstellt, wie im folgenden Beispiel gezeigt wird:  
  
 [!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Beim Verwenden der `new()`-Einschränkung mit anderen Einschränkungen muss sie zuletzt angegeben werden:  
  
 [!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)

