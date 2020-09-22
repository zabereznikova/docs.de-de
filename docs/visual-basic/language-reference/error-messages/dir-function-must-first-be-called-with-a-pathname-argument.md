---
title: Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 1064a44f7c266b9dcce05dfddedef6bb1e919999
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874458"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.

Ein anfänglicher-Rückruf für die- `Dir` Funktion schließt das-Argument nicht ein `PathName` . Der erste Aufruf von `Dir` muss einen enthalten `PathName` , aber nachfolgende Aufrufe von `Dir` müssen keine Parameter enthalten, um das nächste Element abzurufen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Geben Sie `PathName` im Funktions aufrufein Argument an.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
