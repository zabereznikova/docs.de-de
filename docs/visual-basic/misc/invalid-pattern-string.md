---
title: Ungültige Musterzeichenfolge
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 7390b9b32eea248969813b52f8d9799798718de0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790597"
---
# <a name="invalid-pattern-string"></a>Ungültige Musterzeichenfolge
Die angegebene Musterzeichenfolge in der `Like` -Operation einer Suche ist ungültig.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die zulässigen Zeichen für Listenausdrücke.  
  
2. Stellen Sie im Musterbereich sicher, dass das Zeichen für den Startbereich kleiner als das Zeichen für den Endbereich ist, wie in `[a-z]`.  
  
3. Stellen Sie im Musterbereich sicher, dass nicht mehrere Bindestriche nebeneinander verwendet werden, wie in `[a--z]`.  
  
4. Beenden Sie die Musterbereiche mit einer schließenden eckigen Klammer.  
  
## <a name="see-also"></a>Siehe auch

- [Like-Operator](../../visual-basic/language-reference/operators/like-operator.md)
