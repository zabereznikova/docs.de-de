---
title: '&quot;&lt;%InterfaceName&gt;.&lt; Membername&gt;&quot;ist bereits implementiert die Basisklasse&quot;&lt;Baseclassname&gt;&quot;. Die erneute Implementierung von &lt;Typ&gt; davon ausgegangen, dass | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
dev_langs:
- VB
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5ab2041826f74fdc5aceab7b1ceb26563d9b3f0a
ms.lasthandoff: 03/13/2017

---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>'&lt;%InterfaceName&gt;.&lt; Membername&gt;"ist bereits implementiert die Basisklasse"&lt;Baseclassname&gt;". Die erneute Implementierung von &lt;Typ&gt; davon ausgegangen, dass
Eine Eigenschaft, eine Prozedur oder ein Ereignis in einer abgeleiteten Klasse verwendet eine `Implements` -Klausel für einen Schnittstellenmember, der bereits in der Basisklasse implementiert wird.  
  
 Ein Schnittstellenmember, der von seiner Basisklasse implementiert wird, kann von einer abgeleiteten Klasse erneut implementiert werden. Dieser Vorgang ist nicht identisch mit dem Überschreiben der Basisklassenimplementierung. Weitere Informationen finden Sie unter [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42015  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn Sie beabsichtigen, den Schnittstellenmember erneut zu implementieren, müssen Sie keine Maßnahme ergreifen. Code in der abgeleiteten Klasse greift auf die reimplemented Member, es sei denn, Sie verwenden die `MyBase` -Schlüsselwort verwenden, um die Implementierung der Basisklasse zugreifen.  
  
-   Wenn Sie keine erneute Implementierung des Schnittstellenmembers beabsichtigen, entfernen Sie die `Implements` -Klausel aus der Deklaration der Eigenschaft, Prozedur oder des Ereignisses.  
  
## <a name="see-also"></a>Siehe auch  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
