---
title: 'Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4032bbcbf9924eb5aad4e2cb1a6e74df9a472eca
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;
Visual Basic-Compiler Ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen. Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.  
  
 Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt. Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält. Um das Signieren einer Assembly zu verzögern, müssen Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren und eine gültige Schlüsseldatei angeben, die Informationen zum öffentlichen Schlüssel enthält. Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird. Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
 **Fehler-ID:** BC30140  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). für Fehler AL1019 Weitere erläuterungen und Hinweise zu erhalten  
  
2.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Seite „Signierung“, Projekt-Designer](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
