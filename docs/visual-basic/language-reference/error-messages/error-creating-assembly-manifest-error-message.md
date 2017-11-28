---
title: 'Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d846ef88f0c36b49e79b9d11252fcef419dfa0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;
Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen. Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.  
  
 Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt. Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält. Um das Signieren einer Assembly zu verzögern, müssen Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren und eine gültige Schlüsseldatei angeben, die Informationen zum öffentlichen Schlüssel enthält. Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird. Weitere Informationen finden Sie unter [wie: Signieren einer Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).  
  
 **Fehler-ID:** BC30140  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) für Fehler AL1019 Weitere erläuterungen und Hinweise  
  
2.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch  
 [How to: Sign an Assembly (Visual Studio) (Vorgehensweise: Signieren einer Assembly (Visual Studio))](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)  
 [Seite „Signierung“, Projekt-Designer](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe (Assembly Linker-Tool)](https://msdn.microsoft.com/library/c405shex)  
 [Fehler und Warnungen Al.exe-Tools](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
