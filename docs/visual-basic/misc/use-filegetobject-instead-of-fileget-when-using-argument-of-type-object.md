---
title: Verwenden Sie "FileGetObject" statt "FileGet", wenn ein Argument des Typs "Object" verwendet wird
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: fdad64a4b35aa792c996d25a9fd72a9ce1126fbd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306923"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>Verwenden Sie "FileGetObject" statt "FileGet", wenn ein Argument des Typs "Object" verwendet wird
Die `FileGet` -Methode enthält ein Argument vom Typ `Object`. `FileGetObject` sollte anstelle von `FileGet` verwendet werden, um Mehrdeutigkeiten zu vermeiden.  
  
 Beachten Sie, dass die von `My.Computer.Filesystem` bereitgestellte Funktionalität benutzerfreundlicher und leistungsfähiger als `FileGet` oder `FileGetObject`ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Ersetzen Sie `FileGet` durch `FileGetObject`.  
  
2. Wandeln Sie das `Object` -Argument in einen spezifischeren Typ um.  
  
## <a name="see-also"></a>Siehe auch

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
