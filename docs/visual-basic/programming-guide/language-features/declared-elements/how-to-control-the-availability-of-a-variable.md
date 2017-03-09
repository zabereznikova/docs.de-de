---
title: "How to: Control the Availability of a Variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "access levels, declared elements"
  - "Private keyword, accessing variables"
  - "access levels, variables"
  - "Public keyword, accessing variables"
  - "Friend keyword, accessing variables"
  - "variables [Visual Basic], access level"
  - "declared elements, access level"
  - "Protected keyword, accessing variables"
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Control the Availability of a Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Die Verfügbarkeit einer Variablen, wird durch das Angeben ihrer *Zugriffsebene* gesteuert.  Die Zugriffsebene bestimmt, welcher Code berechtigt ist, die Variable zu lesen oder in die Variable zu schreiben.  
  
-   Für *Membervariablen* \(definiert auf Modulebene und außerhalb von Prozeduren\) gilt standardmäßig der öffentliche Zugriff, d. h., Code, der sie erkennen kann, kann auf sie zugreifen.  Sie können dieses Verhalten ändern, indem Sie einen Zugriffsmodifizierer angeben.  
  
-   Für *lokale Variablen* \(definiert innerhalb einer Prozedur\) gilt nominell der öffentliche Zugriff, allerdings kann nur Code innerhalb der Prozedur auf sie zugreifen.  Sie können zwar nicht die Zugriffsebene einer lokalen Variablen ändern, aber die Zugriffsebene der Prozedur, in der sie enthalten ist.  
  
 Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Privater und öffentlicher Zugriff  
  
#### So beschränken Sie den Zugriff auf eine Variable auf ihr Modul, ihre Klasse oder ihre Struktur  
  
1.  Fügen Sie die [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable in das Modul, die Klasse oder die Struktur, aber außerhalb einer Prozedur ein.  
  
2.  Fügen Sie das [Private](../../../../visual-basic/language-reference/modifiers/private.md)\-Schlüsselwort in die `Dim`\-Anweisung ein.  
  
     Sie können die Variable von einer beliebigen Position in dem Modul, der Klasse oder Struktur lesen oder Daten in die Variable schreiben, jedoch nicht von einer Position außerhalb dieser Elemente.  
  
#### So öffnen Sie eine Variable dem Zugriff durch jeden Code, der die Variable erkennen kann  
  
1.  Fügen Sie bei einer Membervariablen die `Dim`\-Anweisung für die Variable in ein Modul, eine Klasse oder eine Struktur, aber außerhalb einer Prozedur ein.  
  
2.  Fügen Sie das [Public](../../../../visual-basic/language-reference/modifiers/public.md)\-Schlüsselwort in die `Dim`\-Anweisung ein.  
  
     Von sämtlichem Code aus, der mit der Assembly interagiert, können Sie die Variable lesen oder Daten in die Variable schreiben.  
  
 \- oder \-  
  
1.  Fügen Sie bei einer lokalen Variablen die `Dim`\-Anweisung für die Variable in eine Prozedur ein.  
  
2.  Fügen Sie nicht das `Public`\-Schlüsselwort in die `Dim`\-Anweisung ein.  
  
     Sie können die Variable von einer beliebigen Position innerhalb der Prozedur lesen oder Daten in die Variable schreiben, jedoch nicht von außerhalb der Prozedur.  
  
## Protected\- und Friend\-Zugriff  
 Sie können die Zugriffsebene einer Variablen auf ihre Klasse und davon abgeleitete Klassen oder auf ihre Assembly begrenzen.  Es ist auch möglich, die Union dieser Begrenzungen festzulegen, sodass ein Zugriff von Code in abgeleiteten Klassen oder von anderen Positionen in derselben Assembly aus möglich ist.  Sie geben diese Union an, indem Sie die Schlüsselwörter `Protected` und `Friend` in der gleichen Deklaration kombinieren.  
  
#### So beschränken Sie den Zugriff auf eine Variable auf ihre Klasse und davon abgeleitete Klassen  
  
1.  Platzieren Sie die `Dim`\-Anweisung für die Variable in einer Klasse, aber außerhalb von Prozeduren.  
  
2.  Fügen Sie das [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)\-Schlüsselwort in die `Dim`\-Anweisung ein.  
  
     Sie können die Variable von einer beliebigen Position innerhalb der Klasse sowie innerhalb davon abgeleiteter Klassen lesen oder Daten in die Variable schreiben, jedoch nicht von einer Position außerhalb einer Klasse in der Ableitungskette.  
  
#### So beschränken Sie den Zugriff auf eine Variable auf die gleiche Assembly  
  
1.  Fügen Sie die `Dim`\-Anweisung für die Variable in ein Modul, eine Klasse oder eine Struktur, aber außerhalb einer Prozedur ein.  
  
2.  Fügen Sie das [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)\-Schlüsselwort in die `Dim`\-Anweisung ein.  
  
     Sie können die Variable von einer beliebigen Position in dem Modul, der Klasse oder Struktur sowie von Code in derselben Assembly aus lesen oder Daten in die Variable schreiben, jedoch nicht von einer Position außerhalb der Assembly.  
  
## Beispiel  
 Das folgende Beispiel zeigt Deklarationen von Variablen mit den Zugriffsebenen `Public`, `Protected`, `Friend`, `Protected Friend` und `Private`.  Wenn in der `Dim`\-Anweisung eine Zugriffsebene angegeben wird, müssen Sie das `Dim`\-Schlüsselwort nicht einfügen.  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## .NET Framework-Sicherheit  
 Je stärker die Zugriffsebene einer Variablen eingeschränkt ist, desto geringer ist die Wahrscheinlichkeit, dass sie von schädlichem Code in unzulässiger Weise verwendet werden kann.  
  
## Siehe auch  
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../../visual-basic/language-reference/modifiers/private.md)