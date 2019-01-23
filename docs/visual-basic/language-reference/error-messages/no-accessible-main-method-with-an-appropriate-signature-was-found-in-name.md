---
title: Keine zugreifbare &#39;Main&#39; Methode mit entsprechender Signatur wurde finden Sie unter &#39; &lt;Name&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 3398195ef9d503e47ab569ff85cb2a827c4270f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501489"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Keine zugreifbare &#39;Main&#39; Methode mit entsprechender Signatur wurde finden Sie unter &#39; &lt;Name&gt;&#39;
Befehlszeile-Anwendungen benötigen eine `Sub Main` definiert. `Main` muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.  
  
 **Fehler-ID:** BC30737  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Definieren einer `Public Sub Main` Verfahren für Ihr Projekt. Deklarieren Sie sie als `Shared` nur, wenn Sie sie innerhalb einer Klasse definieren.  
  
## <a name="see-also"></a>Siehe auch
- [Struktur der Visual Basic-Programmen](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
