---
title: Keine zugreifbare &#39;Main&#39; Methode mit einer entsprechenden Signatur gefunden &#39; &lt;Name&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6a60e26a2bd0e31c0f92dbbfb2518c75f304d9f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Keine zugreifbare &#39;Main&#39; Methode mit einer entsprechenden Signatur gefunden &#39; &lt;Name&gt;&#39;
Befehlszeilenanwendungen benötigen eine `Sub Main` definiert. `Main` muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.  
  
 **Fehler-ID:** BC30737  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Definieren einer `Public Sub Main` Verfahren für das Projekt. Deklarieren Sie es als `Shared` nur, wenn Sie innerhalb einer Klasse zu definieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Struktur eines Visual Basic-Programms](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
