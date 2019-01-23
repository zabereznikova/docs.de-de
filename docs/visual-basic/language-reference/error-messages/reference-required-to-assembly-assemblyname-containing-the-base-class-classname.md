---
title: Ein Verweis auf Assembly erforderlich &#39; &lt;Assemblyname&gt; &#39; mit der Basisklasse &#39; &lt;Klassenname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: f2aa8f1f05ce15bd25992b7f1851854952108813
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506268"
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Ein Verweis auf Assembly erforderlich &#39; &lt;Assemblyname&gt; &#39; mit der Basisklasse &#39; &lt;Klassenname&gt;&#39;
Ein Verweis auf Assembly erforderlich "\<Assemblyname >' mit der Basisklasse\<Klassenname >'. Fügen Sie dem Projekt einen Verweis hinzu.  
  
 Die Klasse ist in einer Dynamic Link Library (DLL) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird. Visual Basic-Compiler erfordert einen Verweis auf die Mehrdeutigkeit zu vermeiden, falls die Klasse in mehreren DLLs oder Assemblys definiert ist.  
  
 **Fehler-ID:** BC30007  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.  
  
## <a name="see-also"></a>Siehe auch

- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [Problembehandlung bei fehlerhaften Verweisen](/visualstudio/ide/troubleshooting-broken-references)
