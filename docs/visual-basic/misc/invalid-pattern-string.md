---
title: Ungültige Musterzeichenfolge
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 5ef12ac27e96205f9ef1c964293847f56b11cb78
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090689"
---
# <a name="invalid-pattern-string"></a>Ungültige Musterzeichenfolge

Die angegebene Musterzeichenfolge in der `Like` -Operation einer Suche ist ungültig.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die zulässigen Zeichen für Listenausdrücke.  
  
2. Stellen Sie im Musterbereich sicher, dass das Zeichen für den Startbereich kleiner als das Zeichen für den Endbereich ist, wie in `[a-z]`.  
  
3. Stellen Sie im Musterbereich sicher, dass nicht mehrere Bindestriche nebeneinander verwendet werden, wie in `[a--z]`.  
  
4. Beenden Sie die Musterbereiche mit einer schließenden eckigen Klammer.  
  
## <a name="see-also"></a>Siehe auch

- [Like-Operator](../language-reference/operators/like-operator.md)
