---
title: "Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fbc8458231c36f3af9ca4de524e01e19a162ee47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.
Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen. Mögliche Ursachen für dieses Problem:  
  
-   Die ursprüngliche Instanz reagiert nicht mehr.  
  
-   Die Anwendung verfügt nicht über die Berechtigungen, Kernelobjekte zu erstellen. Weitere Informationen zu Kernelobjekten finden Sie unter [Mutexe](../../standard/threading/mutexes.md).  
  
     Der Basisname des Kernelobjekts wird gebildet, indem GUID, Hauptversionsnummer und Nebenversionsnummer der Assembly aneinander gehängt werden. Der Basisname könnte beispielsweise `3639f15d-9547-43da-8145-60da347829915.1`lauten.  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>So beheben Sie diesen Fehler beim Entwickeln der Anwendung  
  
1.  Stellen Sie sicher, dass die Anwendung nicht in einen nicht reagierenden Zustand versetzt wird.  
  
2.  Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um Kernelobjekte zu erstellen.  
  
3.  Starten Sie die ursprüngliche Instanz der Anwendung neu.  
  
4.  Starten Sie den Computer neu, um alle Prozesse zu beenden, die möglicherweise die Ressource verwenden, die für eine Verbindung zur ursprünglichen Instanzanwendung erforderlich ist.  
  
5.  Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch  
 [NIB: Vorgehensweise: Angeben des Instanziierungsverhaltens für eine Anwendung (Visual Basic)](http://msdn.microsoft.com/en-us/48539ad8-d960-4210-beab-ee65f6c6dc6e)  
 [Debugger – Grundlagen](/visualstudio/debugger/debugger-basics)  
 [PAVEOVER Produktsupport und Barrierefreiheit](http://msdn.microsoft.com/en-us/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)
