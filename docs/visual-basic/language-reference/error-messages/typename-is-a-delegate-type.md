---
title: <typename> ist ein Delegattyp
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c308805f5e73d740ff18a40d95b9cc2576ac95fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841255"
---
# <a name="typename-is-a-delegate-type"></a>"\<Typname >' ist ein Delegattyp
"\<Typname >' ist ein Delegattyp. Erstellen eines Delegaten kann nur einen einzelnen AddressOf-Ausdruck als Argument übergeben. Häufig kann ein AddressOf-Ausdruck anstelle einer Delegatkonstruktion verwendet werden.  
  
 Ein `New` -Klausel erstellt eine Instanz einer Delegatklasse gibt eine ungültige Argumentliste für den Delegatkonstruktor.  
  
 Sie können angeben, dass nur eine einzige `AddressOf` Ausdruck verwenden, wenn eine neue Delegatinstanz zu erstellen.  
  
 Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben, wenn Sie mehr als ein Argument übergeben, oder wenn Sie ein einzelnes Argument übergeben, keinen gültigen `AddressOf` Ausdruck.  
  
 **Fehler-ID:** BC32008  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie einen einzelnen `AddressOf` Ausdruck in der Argumentliste für die Delegate-Klasse in der `New` Klausel.  
  
## <a name="see-also"></a>Siehe auch

- [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md)
- [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Vorgehensweise: Aufrufen einer Delegatenmethode](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
