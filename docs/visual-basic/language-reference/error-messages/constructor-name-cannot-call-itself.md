---
title: Konstruktor &#39; &lt;Namen&gt;&#39; kann nicht sich selbst aufrufen
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords: BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a>Konstruktor &#39; &lt;Namen&gt;&#39; kann nicht sich selbst aufrufen
Ein `Sub New` Prozeduraufrufe in einer Klasse oder Struktur selbst.  
  
 Der Zweck eines Konstruktors wird eine Instanz einer Klasse initialisiert werden, oder Struktur, die beim ersten erstellt. Eine Klasse oder Struktur kann mehrere Konstruktoren haben, sofern sie alle unterschiedlichen Parameterlisten aufweisen. Ein Konstruktor einen anderen Konstruktor, um seine Funktionen zusätzlich zu seiner eigenen auszuführen aufrufen darf. Jedoch ist dies bedeutungslos, nach einem Konstruktor selbst aufrufen, und in der Tat vielmehr ergibt der Aufruf in einer Endlosschleife, wenn zulässig.  
  
 **Fehler-ID:** BC30298  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Parameterliste des aufgerufenen Konstruktors. Sie sollten sich von dem des Konstruktors, die den Aufruf unterscheiden.  
  
2.  Wenn Sie nicht beabsichtigen, einen anderen Konstruktor aufrufen, entfernen Sie die `Sub New` vollständig aufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
