---
title: '&#39; &lt;Schnittstellenname&gt;.&lt; Membername&gt;&#39; wird bereits von der Basisklasse &#39; implementiert&lt; Basisklassenname&gt;&#39;. Die erneute Implementierung von &lt;Typ&gt; davon ausgegangen, dass'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords: BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69884ed567e0046da5cf5c51b3e83e57e890d49f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>&#39; &lt;Schnittstellenname&gt;.&lt; Membername&gt;&#39; wird bereits von der Basisklasse &#39; implementiert&lt; Basisklassenname&gt;&#39;. Die erneute Implementierung von &lt;Typ&gt; davon ausgegangen, dass
Eine Eigenschaft, eine Prozedur oder ein Ereignis in einer abgeleiteten Klasse verwendet eine `Implements` -Klausel eines Schnittstellenmembers, die bereits in der Basisklasse implementiert wird.  
  
 Ein Schnittstellenmember, der von seiner Basisklasse implementiert wird, kann von einer abgeleiteten Klasse erneut implementiert werden. Dieser Vorgang ist nicht identisch mit dem Überschreiben der Basisklassenimplementierung. Weitere Informationen finden Sie unter [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42015  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie beabsichtigen, den Schnittstellenmember erneut zu implementieren, müssen Sie keine Maßnahme ergreifen. Code in der abgeleiteten Klasse greift auf die neu Member, es sei denn, Sie verwenden die `MyBase` Schlüsselwort, um die Implementierung der Basisklasse zuzugreifen.  
  
-   Wenn Sie keine erneute Implementierung des Schnittstellenmembers beabsichtigen, entfernen Sie die `Implements` -Klausel aus der Deklaration der Eigenschaft, Prozedur oder des Ereignisses.  
  
## <a name="see-also"></a>Siehe auch  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
