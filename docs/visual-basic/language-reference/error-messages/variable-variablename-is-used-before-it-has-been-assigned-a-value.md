---
title: Variable &quot;&lt;Variablename&gt;&quot; wird verwendet, bevor ihr ein Wert zugewiesen wurde, hat | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
dev_langs:
- VB
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7ad1f392fae2f90e366277b7b531d96011648866
ms.lasthandoff: 03/13/2017

---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Variable "&lt;Variablename&gt;' wird verwendet, bevor ihr ein Wert zugewiesen wurde, hat
Variable "\<Variablename >" wird verwendet, bevor er einen Wert zugewiesen wurde. Zur Laufzeit kann eine NULL-Verweisausnahme auftreten.  
  
 Eine Anwendung muss über mindestens einen möglichen Codepfad auf, der eine Variable liest, bevor ein Wert zugewiesen wird.  
  
 Wenn einer Variablen nie ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp. Der Datentyp ein Verweistyp ist, Standardwert [nichts](../../../visual-basic/language-reference/nothing.md). Lesen einer Verweisvariablen mit dem Wert der `Nothing` kann dazu führen, dass ein <xref:System.NullReferenceException>unter bestimmten Umständen.</xref:System.NullReferenceException>  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zu Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42104  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie die Ablaufsteuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine Anweisung übergeben, die diese liest.  
  
-   Eine Möglichkeit, um sicherzustellen, dass die Variable immer einen gültigen Wert aufweist, ist als Teil der Deklaration initialisiert werden. Siehe "Initialisierung" in [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Problembehandlung bei Variablen](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
