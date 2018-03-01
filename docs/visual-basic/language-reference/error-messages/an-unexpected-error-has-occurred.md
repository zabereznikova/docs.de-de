---
title: "Unerwarteter Fehler. Eine Betriebssystemressource, die für den Start einer einzelnen Instanz benötigt wird, ist nicht verfügbar."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8969303d66e946d5579c6cca592b5701c4ebd632
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a>Unerwarteter Fehler. Eine Betriebssystemressource, die für den Start einer einzelnen Instanz benötigt wird, ist nicht verfügbar.
Die Anwendung konnte eine erforderliche Betriebssystemressource nicht abrufen. Mögliche Ursachen für dieses Problem:  
  
-   Die Anwendung verfügt nicht über die Berechtigungen, benannte Betriebssystemobjekte zu erstellen.  
  
-   Die Common Language Runtime verfügt nicht über die Berechtigungen, speicherzugeordnete Dateien zu erstellen.  
  
-   Die Anwendung muss auf ein Betriebssystemobjekt zugreifen, das jedoch in einem anderen Prozess verwendet wird.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um benannte Betriebssystemobjekte zu erstellen.  
  
2.  Stellen Sie sicher, dass die Common Language Runtime über ausreichende Berechtigungen verfügt, um speicherzugeordnete Dateien zu erstellen.  
  
3.  Starten Sie den Computer neu, um alle Prozesse zu beenden, die erforderlich sind, um eine Verbindung zur ursprünglichen Instanzanwendung herzustellen.  
  
4.  Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch  
 [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Debugger – Grundlagen](/visualstudio/debugger/debugger-basics)  
 [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
