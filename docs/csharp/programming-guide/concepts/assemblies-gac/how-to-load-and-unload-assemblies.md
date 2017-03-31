---
title: 'Vorgehensweise: Laden und Entladen von Assemblys (C#) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 15905b2c23320b57e5797d6084ce48cfc526ed7d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a>Vorgehensweise: Laden und Entladen von Assemblys (C#)
Assemblys, auf die das Programm verweist, werden automatisch zur Buildzeit geladen. Es ist jedoch ebenfalls möglich, bestimmte Assemblys zur Laufzeit in die aktuelle Anwendungsdomäne zu laden. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
 Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten. Selbst wenn sich die Assembly außerhalb des gültigen Bereichs befindet, bleibt die entsprechende Assemblydatei geladen, bis alle Anwendungsdomänen entladen sind, in denen sie enthalten ist.  
  
 Wenn Sie nur einige Assemblys entladen möchten, können Sie eine neue Anwendungsdomäne erstellen, darin den Code ausführen und diese Anwendungsdomäne dann entladen. Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>So laden Sie eine Assembly in eine Anwendungsdomäne  
  
1.  Verwenden Sie eine der Load-Methoden, die in den Klassen <xref:System.AppDomain> und <xref:System.Reflection> enthalten sind. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).  
  
### <a name="to-unload-an-application-domain"></a>So entladen Sie eine Anwendungsdomäne  
  
1.  Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten. Verwenden Sie die `Unload`-Methode von <xref:System.AppDomain>, um die Anwendungsdomänen zu entladen. Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)   
 [Assemblys und der globale Assemblycache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)
