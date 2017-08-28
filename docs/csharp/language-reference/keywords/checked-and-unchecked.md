---
title: Checked und Unchecked (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
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
ms.openlocfilehash: 744f59dbf7ee8370010ff76d4e9dde20490de403
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="checked-and-unchecked-c-reference"></a>Checked und Unchecked (C#-Referenz)
C#-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext (checked oder unchecked) ausgeführt werden. In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus. In einem nicht geprüften Kontext wird der arithmetische Überlauf ignoriert, und das Ergebnis wird abgeschnitten.  
  
-   [checked](../../../csharp/language-reference/keywords/checked.md) Gibt einen geprüften Kontext an.  
  
-   [unchecked](../../../csharp/language-reference/keywords/unchecked.md) Gibt einen ungeprüften Kontext an.  
  
 Wenn weder `checked` noch `unchecked` angegeben wird, ist der Standardkontext von externen Faktoren wie Compileroptionen abhängig.  
  
 Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:  
  
-   Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:  
  
     `++``--` - (unär)   `+` -   `*``/`  
  
-   Explizite numerische Konvertierungen zwischen ganzzahligen Typen.  
  
 Mit der Compileroption [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) können Sie einen geprüften oder nicht geprüften Kontext für alle ganzzahligen arithmetischen Anweisungen angeben, die nicht explizit im Umfang eines `checked`- oder `unchecked`-Schlüsselworts enthalten sind.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Anweisungsschlüsselwörter](../../../csharp/language-reference/keywords/statement-keywords.md)

