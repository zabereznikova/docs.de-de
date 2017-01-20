---
title: "Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30369"
  - "bc30369"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Shared"
  - "BC30369"
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie haben versucht, aus einer freigegebenen Prozedur heraus auf einen nicht freigegebenen Member einer Klasse zu verweisen.  Im folgenden Beispiel wird eine solche Situation veranschaulicht.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 Im vorangehenden Beispiel generiert die Zuweisungsanweisung `x = 10` diese Fehlermeldung.  Der Grund dafür ist, dass eine freigegebene Prozedur auf eine Instanzvariable zuzugreifen versucht.  
  
 Die Variable `x` ist ein Instanzmember, da sie nicht als [Shared](../../../visual-basic/language-reference/modifiers/shared.md) deklariert wird.  Jede Instanz der Klasse `sample` enthält ihre eigene Variable `x`.  Wenn eine Instanz den Wert von `x` festlegt oder ändert, wirkt sich dies nicht auf den Wert von `x` in einer anderen Instanz aus.  
  
 Die Prozedur `setX` ist aber für alle Instanzen der `sample`\-Klasse als `Shared` deklariert.  Dies bedeutet, dass sie nicht einer bestimmten Instanz der Klasse zugeordnet ist, sondern unabhängig von einzelnen Instanzen angewendet wird.  Da `setX` nicht mit einer bestimmten Instanz verbunden ist, kann sie auf keine Instanzvariable zugreifen.  Sie darf nur mit `Shared`\-Variablen verwendet werden.  Wenn `setX` den Wert einer als Shared deklarierten Variablen festlegt oder ändert, ist der neue Wert für alle Instanzen der Klasse verfügbar.  
  
 **Fehler\-ID:** BC30369  
  
### So beheben Sie diesen Fehler  
  
1.  Entscheiden Sie, ob der Member von allen Instanzen der Klasse gemeinsam genutzt werden soll oder ob er in jeder Instanz unabhängig von den anderen Instanzen verwaltet werden soll.  
  
2.  Wenn ein Exemplar des Members von allen Instanzen gemeinsam genutzt werden soll, fügen Sie das `Shared`\-Schlüsselwort der Memberdeklaration hinzu.  Behalten Sie das `Shared`\-Schlüsselwort in der Prozedurdeklaration bei.  
  
3.  Wenn jede Instanz über ein eigenes Exemplar des Members verfügen soll, geben Sie das `Shared`\-Schlüsselwort in der Memberdeklaration nicht an.  Entfernen Sie das `Shared`\-Schlüsselwort aus der Prozedurdeklaration.  
  
## Siehe auch  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)