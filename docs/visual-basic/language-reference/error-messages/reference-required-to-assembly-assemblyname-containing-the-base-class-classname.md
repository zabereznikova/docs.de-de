---
title: Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyname&gt;&#39; mit der Basisklasse &#39;&lt; Klassenname&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39fa33a655b311ee39466c18cefdb0bf07a92720
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyname&gt;&#39; mit der Basisklasse &#39;&lt; Klassenname&gt;&#39;
Ein Verweis auf Assembly erforderlich "\<Assemblyname >' mit der Basisklasse\<Klassenname >'. Fügen Sie dem Projekt einen Verweis hinzu.  
  
 Die Klasse ist in einer Dynamic Link Library (DLL) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird. Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler benötigt einen Verweis, um Mehrdeutigkeiten zu vermeiden, falls die Klasse in mehreren DLLs oder Assemblys definiert ist.  
  
 **Fehler-ID:** BC30007  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.  
  
## <a name="see-also"></a>Siehe auch  
   
 [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)  
 [Problembehandlung bei fehlerhaften Verweisen](/visualstudio/ide/troubleshooting-broken-references)
