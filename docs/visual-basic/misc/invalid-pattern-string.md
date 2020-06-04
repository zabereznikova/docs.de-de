---
title: Ungültige Musterzeichenfolge
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: aa408f4cecc2a2774cb98cba96cd04a67afcc546
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402212"
---
# <a name="invalid-pattern-string"></a>Ungültige Musterzeichenfolge
Die angegebene Musterzeichenfolge in der `Like` -Operation einer Suche ist ungültig.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die zulässigen Zeichen für Listenausdrücke.  
  
2. Stellen Sie im Musterbereich sicher, dass das Zeichen für den Startbereich kleiner als das Zeichen für den Endbereich ist, wie in `[a-z]`.  
  
3. Stellen Sie im Musterbereich sicher, dass nicht mehrere Bindestriche nebeneinander verwendet werden, wie in `[a--z]`.  
  
4. Beenden Sie die Musterbereiche mit einer schließenden eckigen Klammer.  
  
## <a name="see-also"></a>Weitere Informationen

- [Like-Operator](../language-reference/operators/like-operator.md)
