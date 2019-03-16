---
title: Ungültige Musterzeichenfolge
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: bc2e91060ca1b0e21ea28b0f08febc3e0c54f4f1
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58027315"
---
# <a name="invalid-pattern-string"></a>Ungültige Musterzeichenfolge
Die angegebene Musterzeichenfolge in der `Like` -Operation einer Suche ist ungültig.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die zulässigen Zeichen für Listenausdrücke.  
  
2.  Stellen Sie im Musterbereich sicher, dass das Zeichen für den Startbereich kleiner als das Zeichen für den Endbereich ist, wie in `[a-z]`.  
  
3.  Stellen Sie im Musterbereich sicher, dass nicht mehrere Bindestriche nebeneinander verwendet werden, wie in `[a--z]`.  
  
4.  Beenden Sie die Musterbereiche mit einer schließenden eckigen Klammer.  
  
## <a name="see-also"></a>Siehe auch

- [Like-Operator](../../visual-basic/language-reference/operators/like-operator.md)
