---
title: "&#39; &lt;Typename&gt;&#39; kann nicht Vererben &lt;Typ&gt; &#39;&lt; Basistypname&gt;&#39; erweitert den Zugriff von Basis-und &lt;Typ&gt; außerhalb der Assembly"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords: BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d01981d3136968ae2534539b8eccab4c5c535fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39; &lt;Typename&gt;&#39; kann nicht Vererben &lt;Typ&gt; &#39;&lt; Basistypname&gt;&#39; erweitert den Zugriff von Basis-und &lt;Typ&gt; außerhalb der Assembly
Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle enthält jedoch eine weniger restriktive Zugriffsebene.  
  
 Z. B. eine `Public` Schnittstelle erbt von einer `Friend` -Schnittstelle, oder eine `Protected` Klasse erbt von einer `Private` Klasse. Dies stellt die Basisklasse oder-Schnittstelle außerhalb der vorgesehenen Ebene den Zugriff auf.  
  
 **Fehler-ID:** BC30910  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle, die mindestens so restriktiv wie, die von der Basisklasse oder Schnittstelle sein.  
  
     - oder -   
  
-   Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die `Inherits` Anweisung. Sie können nicht von einem eingeschränkteren Basisklasse oder Schnittstelle erben.  
  
## <a name="see-also"></a>Siehe auch  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
