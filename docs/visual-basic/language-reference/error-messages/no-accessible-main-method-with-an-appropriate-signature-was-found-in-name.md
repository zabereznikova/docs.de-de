---
title: Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in "<name>" gefunden.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: b3aa66416f0cad6a6fb29a20aa0bca5e3486a18e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275430"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in gefunden "\<Name >'
Befehlszeile-Anwendungen benötigen eine `Sub Main` definiert. `Main` muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.  
  
 **Fehler-ID:** BC30737  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Definieren einer `Public Sub Main` Verfahren für Ihr Projekt. Deklarieren Sie sie als `Shared` nur, wenn Sie sie innerhalb einer Klasse definieren.  
  
## <a name="see-also"></a>Siehe auch
- [Struktur der Visual Basic-Programmen](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
