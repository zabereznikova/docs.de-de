---
title: Struktur &#39; &lt;Strukturname&gt;&#39; muss mindestens eine Instanzmembervariable oder mindestens eine Instanzereignisdeklaration nicht gekennzeichnet &#39; enthalten Benutzerdefinierte &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords: BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b28dd59271bdaca52072710ea797fae6e9168eab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Struktur &#39; &lt;Strukturname&gt;&#39; muss mindestens eine Instanzmembervariable oder mindestens eine Instanzereignisdeklaration nicht gekennzeichnet &#39; enthalten Benutzerdefinierte &#39;
Eine Strukturdefinition umfasst keine nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse.  
  
 Jede Struktur benötigen, eine Variable oder ein Ereignis, das für jede spezifische Instanz (nicht freigegebene) anstelle von allen Instanzen gemeinsam gilt ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht. Darüber hinaus treten keine nicht freigegebenen Variablen und nur ein nicht freigegebenes Ereignis, das Ereignis nicht mit einem `Custom` Ereignis.  
  
 **Fehler-ID:** BC30941  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht `Shared`. Wenn Sie nur ein Ereignis definieren, muss es sowohl nicht benutzerdefinierte als auch nicht freigegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
