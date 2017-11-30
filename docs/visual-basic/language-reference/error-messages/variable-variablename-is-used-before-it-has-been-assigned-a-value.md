---
title: Variable &#39; &lt;Variablename&gt;&#39; wird verwendet, bevor ihr einen Wert zugewiesen wurde
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords: BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 201667c250e15bb9af73e64e2d8c924c1952d1be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Variable &#39; &lt;Variablename&gt;&#39; wird verwendet, bevor ihr einen Wert zugewiesen wurde
Variable "\<Variablename >' wird verwendet, bevor ihr einen Wert zugewiesen wurde. Zur Laufzeit kann eine NULL-Verweisausnahme auftreten.  
  
 Eine Anwendung muss über mindestens einen möglichen Pfad durch ihren Code, der eine Variable liest, bevor ein Wert zugewiesen wird.  
  
 Wenn einer Variablen nie ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp. Für eine Verweisdatentypen ist dieser Standardwert [nichts](../../../visual-basic/language-reference/nothing.md). Das Lesen einer Verweisvariablen, die den Wert `Nothing` aufweist, kann unter bestimmten Umständen zu einer <xref:System.NullReferenceException> führen.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42104  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine beliebige Anweisung übergeben, die gelesen.  
  
-   Eine Möglichkeit, um sicherzustellen, dass die Variable hat immer einen gültigen Wert wird als Teil der Deklaration initialisiert werden. Siehe "Initialisierung" in [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Problembehandlung bei Variablen](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
