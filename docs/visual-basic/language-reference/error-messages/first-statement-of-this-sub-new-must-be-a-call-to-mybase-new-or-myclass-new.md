---
title: Die erste Anweisung dieser &#39; Sub New &#39; Hierbei muss es sich um einen Aufruf von &#39;sein. MyBase.New &#39; oder &#39; MyClass.New &#39; (Kein zugreifbarer Konstruktor ohne Parameter)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1065643e1f6c868092fbad839af0dbbd33afaf01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>Die erste Anweisung dieser &#39; Sub New &#39; Hierbei muss es sich um einen Aufruf von &#39;sein. MyBase.New &#39; oder &#39; MyClass.New &#39; (Kein zugreifbarer Konstruktor ohne Parameter)
Die erste Anweisung dieser "Sub New" muss ein Aufruf von "MyBase.New" oder "MyClass.New" sein, da Basisklasse\<Basename >' von '\<Derivedname >' besitzt keine zugegriffen werden kann "Sub New" hat, die ohne Argumente aufgerufen werden kann.  
  
 Jeder Konstruktor muss in einer abgeleiteten Klasse einen Basisklassenkonstruktor aufrufen (`MyBase.New`). Wenn die Basisklasse der Klasse einen Konstruktor ohne Parameter verfügt, die für den abgeleiteten Klassen zugänglich ist `MyBase.New` automatisch aufgerufen werden kann. Wenn dies nicht der Fall ist, muss ein Basisklassenkonstruktor mit Parametern aufgerufen werden, und dies kann nicht automatisch durchgeführt werden. In diesem Fall muss die erste Anweisung jeder abgeleiteten Klassenkonstruktor einen parametrisierten Konstruktor der Basisklasse aufrufen, oder rufen Sie einen anderen Konstruktor in der abgeleiteten Klasse, mit der ein Konstruktor der Basisklasse aufrufen.  
  
 **Fehler-ID:** BC30148  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entweder Aufruf `MyBase.New` Geben Sie die erforderlichen Parameter, oder rufen Sie einen Peerkonstruktor, der solch einen Aufruf macht.  
  
     Angenommen, wenn die Basisklasse der Klasse einen Konstruktor verfügt, die als deklariert ist `Public Sub New(ByVal index as Integer)`, die erste Anweisung in der abgeleiteten Klassenkonstruktor möglicherweise `MyBase.New(100)`.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
