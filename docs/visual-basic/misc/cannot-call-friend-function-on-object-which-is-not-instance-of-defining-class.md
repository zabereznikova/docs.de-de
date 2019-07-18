---
title: Die Friend-Funktion eines Objekts, das keine Instanz der definierenden Klasse ist, kann nicht aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: a227e5761bacc36c0682844a833e70c34582a5d3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622604"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a>Die Friend-Funktion eines Objekts, das keine Instanz der definierenden Klasse ist, kann nicht aufgerufen werden.
Entweder haben Sie versucht, die `Friend` -Prozedur einer Klasse aufzurufen, oder prozess- bzw. threadübergreifend auf eine `Friend` -Eigenschaft oder -Methode zuzugreifen. Eine `Friend` -Prozedur kann über ein Modul außerhalb der Klasse aufgerufen werden, ist jedoch Teil des Projekts, in dem die Klasse definiert ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Stellen Sie sicher, dass Sie die Prozedur über ein Modul aufrufen bzw. auf sie zugreifen, das Teil des Projekts ist, in dem die Klasse definiert ist.  
  
## <a name="see-also"></a>Siehe auch

- [Friend](../../visual-basic/language-reference/modifiers/friend.md)
