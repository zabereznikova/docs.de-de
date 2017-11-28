---
title: Checked und Unchecked (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b7b18b39dbfa7ed0818d9ea6e9e62ef79a9f5b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
