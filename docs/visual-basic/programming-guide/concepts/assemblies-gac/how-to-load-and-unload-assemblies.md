---
title: 'Vorgehensweise: Laden und Entladen von Assemblys (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd52a1094dba16c7e1bcba5bface9e13747cd4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>Vorgehensweise: Laden und Entladen von Assemblys (Visual Basic)
Assemblys, auf die das Programm verweist, werden automatisch zur Buildzeit geladen. Es ist jedoch ebenfalls möglich, bestimmte Assemblys zur Laufzeit in die aktuelle Anwendungsdomäne zu laden. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
 Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten. Selbst wenn sich die Assembly außerhalb des gültigen Bereichs befindet, bleibt die entsprechende Assemblydatei geladen, bis alle Anwendungsdomänen entladen sind, in denen sie enthalten ist.  
  
 Wenn Sie nur einige Assemblys entladen möchten, können Sie eine neue Anwendungsdomäne erstellen, darin den Code ausführen und diese Anwendungsdomäne dann entladen. Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>So laden Sie eine Assembly in eine Anwendungsdomäne  
  
1.  Verwenden Sie eine der Load-Methoden in den <xref:System.AppDomain>-Klassen und in den <xref:System.Reflection>-Klassen. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).  
  
### <a name="to-unload-an-application-domain"></a>So entladen Sie eine Anwendungsdomäne  
  
1.  Es gibt keine Möglichkeit, eine einzelne Assembly zu entladen, ohne alle Anwendungsdomänen zu entladen, die diese Assembly enthalten. Verwenden Sie die `Unload`-Methode von <xref:System.AppDomain>, um die Anwendungsdomänen zu entladen. Weitere Informationen finden Sie unter [Vorgehensweise: Entladen einer Anwendungsdomäne](../../../../framework/app-domains/how-to-unload-an-application-domain.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)  
 [Assemblys und der globale Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
