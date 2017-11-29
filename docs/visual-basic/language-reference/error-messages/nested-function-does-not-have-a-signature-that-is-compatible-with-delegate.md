---
title: "Geschachtelte Funktion verfügt über keine Signatur, die kompatibel mit Delegaten &#39; &lt;Delegatname&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords: BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60cf15343023110561da3e3fcf202bd00394127a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>Geschachtelte Funktion verfügt über keine Signatur, die kompatibel mit Delegaten &#39; &lt;Delegatname&gt;&#39;
Ein Lambda-Ausdruck wurde an einen Delegaten zugewiesen, die eine nicht kompatible Signatur verfügt. Im folgenden Code wird z. B. Delegieren `Del` verfügt über zwei Integer-Parameter.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Der Fehler wird ausgelöst, wenn ein Lambda-Ausdruck mit einem Argument als Typ deklariert wird `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Fehler-ID:** BC36532  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Passen Sie die Delegatdefinition oder den zugewiesenen Lambda-Ausdruck, damit die Signaturen kompatibel sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
