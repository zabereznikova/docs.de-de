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
ms.openlocfilehash: 3f45dc17304c3c9d62b65760f2c1b5d461812a66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>Keine zugreifbare &#39; Main &#39; Methode mit einer entsprechenden Signatur wurde gefunden, &#39; &lt;Namen&gt;&#39;
Befehlszeilenanwendungen benötigen eine `Sub Main` definiert. `Main`muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.  
  
 Weitere Informationen zu `Main`, finden Sie unter [NIB: Visual Basic-Version von Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c).  
  
 **Fehler-ID:** BC30737  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Definieren einer `Public Sub Main` Verfahren für das Projekt. Deklarieren Sie es als `Shared` nur, wenn Sie innerhalb einer Klasse zu definieren.  
  
## <a name="see-also"></a>Siehe auch  
 [NIB: Visual Basic-Version von Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [Struktur eines Visual Basic-Programms](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
