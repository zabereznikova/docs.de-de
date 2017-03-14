---
title: "Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42104"
  - "BC42104"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42104"
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Die \<Variablenname\>\-Variable wird verwendet, bevor ihr ein Wert zugewiesen wird.Zur Laufzeit kann eine NULL\-Verweisausnahme auftreten  
  
 Eine Anwendung verfügt über mindestens einen möglichen Codepfad, der eine Variable liest, bevor ihr ein Wert zugewiesen wird.  
  
 Wenn einer Variablen niemals ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp.  Wenn der Datentyp ein Verweistyp ist, lautet dieser Standardwert [Nothing](../../../visual-basic/language-reference/nothing.md).  Das Lesen einer Verweisvariablen mit dem Wert `Nothing` kann unter bestimmten Umständen eine <xref:System.NullReferenceException> verursachen.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Weitere Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42104  
  
### So beheben Sie diesen Fehler  
  
-   Überprüfen Sie die Ablaufsteuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine Anweisung übergeben wird, die die Variable liest.  
  
-   Eine Möglichkeit, um sicherzustellen, dass die Variable immer einen gültigen Wert aufweist, besteht im Initialisieren der Variablen in ihrer Deklaration.  Siehe "Initialisierung" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## Siehe auch  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Problembehandlung bei Variablen](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)