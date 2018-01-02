---
title: Keine zugreifbare &#39; Main &#39; Methode mit einer entsprechenden Signatur wurde gefunden, &#39; &lt;Namen&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords: BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6a2d66c860b72bd3ef59c02f548ac563fab6b8c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Keine zugreifbare &#39; Main &#39; Methode mit einer entsprechenden Signatur wurde gefunden, &#39; &lt;Namen&gt;&#39;
Befehlszeilenanwendungen benötigen eine `Sub Main` definiert. `Main`muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.  
  
 **Fehler-ID:** BC30737  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Definieren einer `Public Sub Main` Verfahren für das Projekt. Deklarieren Sie es als `Shared` nur, wenn Sie innerhalb einer Klasse zu definieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Struktur eines Visual Basic-Programms](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
