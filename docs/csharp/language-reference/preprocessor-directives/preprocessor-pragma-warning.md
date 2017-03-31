---
title: '#pragma-Warnung (C#-Referenz) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma warning'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 820b6de93a2a739d97084250601e41a5eb4a89f8
ms.lasthandoff: 03/13/2017

---
# <a name="pragma-warning-c-reference"></a>#pragma-Warnung (C#-Referenz)
`#pragma warning` kann bestimmte Warnungen aktivieren oder deaktivieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a>Parameter  
 `warning-list`  
 Eine durch Trennzeichen getrennte Liste mit Warnzahlen. Das Präfix „CS“ ist optional.  
  
 Wenn keine Warnzahlen angegeben werden, deaktiviert `disable` alle Warnungen und `restore` aktiviert sie.  
  
> [!NOTE]
>  Um Warnzahlen in Visual Studio zu suchen, erstellen Sie Ihr Projekt und suchen Sie nach den Warnzahlen im Fenster **Ausgabe**.  
  
## <a name="example"></a>Beispiel  
  
```  
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [C#-Compilerfehler](../../../csharp/language-reference/compiler-messages/index.md)
