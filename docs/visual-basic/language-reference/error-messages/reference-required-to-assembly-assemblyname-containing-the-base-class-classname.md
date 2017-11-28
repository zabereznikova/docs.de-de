---
title: Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyname&gt;&#39; mit der Basisklasse &#39;&lt; Klassenname&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords: BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7413c82a9c61d13e7ca6fa18f27a4769a0937f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a>Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyname&gt;&#39; mit der Basisklasse &#39;&lt; Klassenname&gt;&#39;
Ein Verweis auf Assembly erforderlich "\<Assemblyname >' mit der Basisklasse\<Klassenname >'. Fügen Sie dem Projekt einen Verweis hinzu.  
  
 Die Klasse ist in einer Dynamic Link Library (DLL) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird. Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler benötigt einen Verweis, um Mehrdeutigkeiten zu vermeiden, falls die Klasse in mehreren DLLs oder Assemblys definiert ist.  
  
 **Fehler-ID:** BC30007  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.  
  
## <a name="see-also"></a>Siehe auch  
 [NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)  
 [Problembehandlung bei fehlerhaften Verweisen](/visualstudio/ide/troubleshooting-broken-references)
