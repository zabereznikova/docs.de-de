---
title: "Verweis auf die Assembly erforderlich &quot;&lt;Assemblyname&gt;&quot;enthält die Basisklasse&quot;&lt;Classname&gt;&quot; | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
dev_langs:
- VB
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2692478864007c787eb19367109e6ce01882ffb1
ms.lasthandoff: 03/13/2017

---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Verweis auf die Assembly erforderlich '&lt;Assemblyname&gt;"enthält die Basisklasse"&lt;Classname&gt;'
Verweis auf die Assembly erforderlich '\<Assemblyname >', enthält der Basisklasse\<Classname >'. Fügen Sie dem Projekt einen Verweis hinzu.  
  
 Die Klasse ist in einer Dynamic Link Library (DLL) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird. Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler benötigt einen Verweis, um Mehrdeutigkeit zu vermeiden, falls die Klasse in mehr als einer DLL oder Assembly definiert ist.  
  
 **Fehler-ID:** BC30007  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.  
  
## <a name="see-also"></a>Siehe auch  
 [NIB: Vorgehensweise: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [Problembehandlung bei fehlerhaften Verweisen](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)
