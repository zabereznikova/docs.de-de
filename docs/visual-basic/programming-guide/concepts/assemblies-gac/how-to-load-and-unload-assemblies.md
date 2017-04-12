---
title: 'Gewusst wie: Laden und Entladen von Assemblys (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 460d3a18fdee74c9b9c49ee465247b5b12d554d8
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>Gewusst wie: Laden und Entladen von Assemblys (Visual Basic)
Assemblys, auf die das Programm verweist, werden automatisch zur Buildzeit geladen. Es ist jedoch ebenfalls möglich, bestimmte Assemblys zur Laufzeit in die aktuelle Anwendungsdomäne zu laden. Weitere Informationen finden Sie unter [Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
 Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten. Selbst wenn sich die Assembly außerhalb des gültigen Bereichs befindet, bleibt die entsprechende Assemblydatei geladen, bis alle Anwendungsdomänen entladen sind, in denen sie enthalten ist.  
  
 Wenn Sie nur einige Assemblys entladen möchten, können Sie eine neue Anwendungsdomäne erstellen, darin den Code ausführen und diese Anwendungsdomäne dann entladen. Weitere Informationen finden Sie unter [Gewusst wie: Entladen einer Anwendungsdomäne](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>So laden Sie eine Assembly in eine Anwendungsdomäne  
  
1.  Verwenden Sie eine der Load-Methoden in den Klassen <xref:System.AppDomain>und <xref:System.Reflection>.</xref:System.Reflection> </xref:System.AppDomain> Weitere Informationen finden Sie unter [Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
### <a name="to-unload-an-application-domain"></a>So entladen Sie eine Anwendungsdomäne  
  
1.  Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten. Verwenden der `Unload` aus <xref:System.AppDomain>, die Anwendungsdomänen zu entladen.</xref:System.AppDomain> Weitere Informationen finden Sie unter [Gewusst wie: Entladen einer Anwendungsdomäne](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Gewusst wie: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)
