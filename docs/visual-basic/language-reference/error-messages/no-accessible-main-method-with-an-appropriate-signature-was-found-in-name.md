---
title: Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in "<name>" gefunden.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: f5053bddf4b9ba791ad6d0733e1dd89c4ded91bd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818357"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in gefunden "\<Name >'
Befehlszeile-Anwendungen benötigen eine `Sub Main` definiert. `Main` muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.  
  
 **Fehler-ID:** BC30737  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Definieren einer `Public Sub Main` Verfahren für Ihr Projekt. Deklarieren Sie sie als `Shared` nur, wenn Sie sie innerhalb einer Klasse definieren.  
  
## <a name="see-also"></a>Siehe auch

- [Struktur der Visual Basic-Programmen](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
