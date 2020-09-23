---
title: Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 8e2caa158c3874d216671979430a03b11bf60066
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095680"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen.

Diese Einzelinstanzanwendung konnte keine Verbindung zur ursprünglichen Instanz herstellen. Mögliche Ursachen für dieses Problem:  
  
- Die ursprüngliche Instanz reagiert nicht mehr.  
  
- Die Anwendung verfügt nicht über die Berechtigungen, Kernelobjekte zu erstellen. Weitere Informationen zu Kernel Objekten finden Sie unter [Mutexes](../../standard/threading/mutexes.md).  
  
     Der Basisname des Kernelobjekts wird gebildet, indem GUID, Hauptversionsnummer und Nebenversionsnummer der Assembly aneinander gehängt werden. Der Basisname könnte beispielsweise `3639f15d-9547-43da-8145-60da347829915.1`lauten.  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>So beheben Sie diesen Fehler beim Entwickeln der Anwendung  
  
1. Stellen Sie sicher, dass die Anwendung nicht in einen nicht reagierenden Zustand versetzt wird.  
  
2. Stellen Sie sicher, dass die Anwendung über ausreichende Berechtigungen verfügt, um Kernelobjekte zu erstellen.  
  
3. Starten Sie die ursprüngliche Instanz der Anwendung neu.  
  
4. Starten Sie den Computer neu, um alle Prozesse zu beenden, die möglicherweise die Ressource verwenden, die für eine Verbindung zur ursprünglichen Instanzanwendung erforderlich ist.  
  
5. Notieren Sie sich die Umstände, unter denen der Fehler aufgetreten ist, und wenden Sie sich an den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch

- [Debugger – Grundlagen](/visualstudio/debugger/debugger-feature-tour)
