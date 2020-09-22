---
title: <typename> ist ein Delegattyp
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4cc0a1221dcf65aa2a16fd7d82568c8544f27fdb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875089"
---
# <a name="typename-is-a-delegate-type"></a>\<typename> ist ein Delegattyp

" \<typename> " ist ein Delegattyp. Bei der Delegatkonstruktion ist nur ein einzelner AddressOf-Ausdruck als Argumentliste zulässig. Häufig kann ein AddressOf-Ausdruck anstelle einer Delegaterstellung verwendet werden.  
  
 Eine- `New` Klausel, die eine Instanz einer Delegatklasse erstellt, stellt eine ungültige Argumentliste für den Delegatkonstruktor bereit.  
  
 Sie können nur einen einzelnen Ausdruck angeben, `AddressOf` Wenn Sie eine neue Delegatinstanz erstellen.  
  
 Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben, wenn Sie mehr als ein Argument übergeben oder wenn Sie ein einzelnes Argument übergeben, das kein gültiger Ausdruck ist `AddressOf` .  
  
 **Fehler-ID:** BC32008  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie einen einzelnen `AddressOf` Ausdruck in der Argumentliste für die Delegatklasse in der- `New` Klausel.  
  
## <a name="see-also"></a>Weitere Informationen

- [New-Operator](../operators/new-operator.md)
- [AddressOf-Operator](../operators/addressof-operator.md)
- [Delegaten](../../programming-guide/language-features/delegates/index.md)
- [Vorgehensweise: Aufrufen einer Delegatenmethode](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
