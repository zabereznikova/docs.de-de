---
title: "&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30909"
  - "vbc30909"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30909"
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# &#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine Variable, ein Prozedurparameter oder eine Funktionsrückgabe wird außerhalb des zugehörigen Containers verfügbar gemacht, ist jedoch als Typ deklariert, der nicht außerhalb des Containers verfügbar gemacht werden darf.  
  
 Im folgenden Codeskelett wird eine Situation veranschaulicht, die diesen Fehler generiert.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Ein als `Protected`, `Friend`, `Protected Friend` oder `Private` deklarierter Typ soll außerhalb des Deklarationskontexts eingeschränkten Zugriff aufweisen.  Dies ist nicht möglich, wenn er als Datentyp einer Variablen mit weniger eingeschränktem Zugriff verwendet wird.  Im vorhergehenden Skelettcode ist `exposedVar` `Public` und macht `privateClass` für Code verfügbar, der nicht darauf zugreifen soll.  
  
 **Fehler\-ID:** BC30909  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie die Zugriffsebene der Variablen, des Prozedurparameters oder der Funktionsrückgabe in eine Zugriffsebene, die mindestens so restriktiv wie die Zugriffsebene des zugehörigen Datentyps ist.  
  
## Siehe auch  
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)